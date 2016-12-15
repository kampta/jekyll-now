---
layout: post
title: Getting starting with GPU based Virtual Machines on Microsoft Azure!
excerpt: Microsot recently (August 4, 2016) announced their Azure N-Series Virtual Machines. I was at the time evaluating options to serve deep learning models on GPUs and decided to give it a try. It was actually pretty straightforward.
---

Microsoft [announced](https://azure.microsoft.com/en-in/blog/azure-n-series-preview-availability/) has started providing GPU based Virtual Machines as Azure N-Series. There are two categories:

1. NC-Series (compute-focused GPUs), powered by Tesla K80 GPUs
2. NV-Series (focused on visualization), using Tesla M60 GPUs and NVIDIA GRID for desktop accelerated applications

I needed GPU based servers for serving few deep learning models, so NC-Series was the obvious choice.

## Creating a new VM

I am not big Microsoft buff, and I use [`docker-machine`](https://docs.docker.com/machine/) to manage all my VMs. It makes getting started/switching over to any cloud server, be it Azure/AWS/DigitalOcean very seemless. If you haven't already, I'll recommend [installing](https://docs.docker.com/machine/) it right away.

```
docker-machine create --driver azure \
	--azure-subscription-id ############################### \
	--azure-location southcentralus \
	--azure-image canonical:UbuntuServer:16.04.0-LTS:latest \
	--azure-size Standard_NC6 \
	--azure-open-port 80 --azure-open-port 8000 --azure-open-port 8888 \
	my-awesome-machine
```

Note that NC-Series is available only in `southcentralus` at the time of writing the post.

If you get an error like this

```
Error creating machine: Error in driver during machine creation: compute.VirtualMachinesClient#CreateOrUpdate: Failure sending request: StatusCode=409 -- Original Error: Long running operation terminated with status 'Failed': Code='OperationNotAllowed' Message='Operation results in exceeding quota limits of Core. Maximum allowed: 0, Current in use: 0, Additional requested: 6.'
```

That might mean, you need to [apply here](http://gpu.azure.com) to get approval for N-Series.

## Install nvidia drivers

That's straightforward too
```
docker-machine ssh my-awesome-machine
sudo apt-get purge nvidia-*
sudo add-apt-repository ppa:graphics-drivers/ppa
sudo apt-get update.
sudo apt-get install nvidia-370
```

Logout of the machine, restart it and test if the drivers were installed properly

```
docker-machine restart my-awesome-machine
docker-machine ssh my-awesome-machine
nvidia-smi
```

## Install `docker`

Cool, now we just have to install docker on the server. I'll just write down the instructions from the [documentation](https://docs.docker.com/engine/installation/linux/ubuntulinux/):

```
sudo apt-get install linux-image-extra-$(uname -r) linux-image-extra-virtual
sudo apt-get install docker-engine
```

## Install `nvidia-docker`

Almost there, copying instructions from nvidia's github page for sake of completion. More information on [why NVIDIA docker](https://github.com/NVIDIA/nvidia-docker/wiki/Why%20NVIDIA%20Docker), and other details refer [https://github.com/NVIDIA/nvidia-docker](https://github.com/NVIDIA/nvidia-docker).

```
wget -P /tmp https://github.com/NVIDIA/nvidia-docker/releases/download/v1.0.0-rc.3/nvidia-docker_1.0.0.rc.3-1_amd64.deb
sudo dpkg -i /tmp/nvidia-docker*.deb && rm /tmp/nvidia-docker*.deb

# Test nvidia-smi
sudo nvidia-docker run --rm nvidia/cuda nvidia-smi
```

## Testing GPU with `tensorflow`

`tensorflow` provides docker images having all dependencies for running tensorflow with CUDA. Run a container in detached mode like this

```
sudo nvidia-docker run -itd -p 8888:8888 -e "PASSWORD=password" --name=tf_container gcr.io/tensorflow/tensorflow:latest-gpu
```

In this command, we are

* Exposing ports 8888, so that you can browse to [http://IP_OF_MY_AWESOME_MACHINE:8888](http://IP_OF_MY_AWESOME_MACHINE:8888) and go to the `jupyter` server
* Setting PASSWORD=password, which you will need to enter `jupyter` server
* Running in a detached mode, so docker can keep running in the background

Finally, login to the container and test it out. You should see some output like this

```
# Note that we named container as `tf_container` in the last command
sudo docker exec -it tf_container bash

ipython
In [1]: import tensorflow as tf
I tensorflow/stream_executor/dso_loader.cc:128] successfully opened CUDA library libcublas.so locally
I tensorflow/stream_executor/dso_loader.cc:128] successfully opened CUDA library libcudnn.so locally
I tensorflow/stream_executor/dso_loader.cc:128] successfully opened CUDA library libcufft.so locally
I tensorflow/stream_executor/dso_loader.cc:128] successfully opened CUDA library libcuda.so.1 locally
I tensorflow/stream_executor/dso_loader.cc:128] successfully opened CUDA library libcurand.so locally

In [2]: sess = tf.Session(config=tf.ConfigProto(log_device_placement=True))
I tensorflow/core/common_runtime/gpu/gpu_device.cc:885] Found device 0 with properties:
name: Tesla K80
major: 3 minor: 7 memoryClockRate (GHz) 0.8235
pciBusID 9540:00:00.0
Total memory: 11.17GiB
Free memory: 11.11GiB
I tensorflow/core/common_runtime/gpu/gpu_device.cc:906] DMA: 0
I tensorflow/core/common_runtime/gpu/gpu_device.cc:916] 0:   Y
I tensorflow/core/common_runtime/gpu/gpu_device.cc:975] Creating TensorFlow device (/gpu:0) -> (device: 0, name: Tesla K80, pci bus id: 9540:00:00.0)
Device mapping:
/job:localhost/replica:0/task:0/gpu:0 -> device: 0, name: Tesla K80, pci bus id: 9540:00:00.0
I tensorflow/core/common_runtime/direct_session.cc:255] Device mapping:
/job:localhost/replica:0/task:0/gpu:0 -> device: 0, name: Tesla K80, pci bus id: 9540:00:00.0
```

That's all for today. Have fun with docker and tensorflow.