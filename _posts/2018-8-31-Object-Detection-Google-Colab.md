---
layout: post
title: Running object detection on Colab
excerpt: Colaboratory is a Google research project created to help disseminate machine learning education and research
---


## Colab what?
Although it has been a while (~1 year) since Google released ([one of its internal tools](https://twitter.com/ch402/status/923948575469461505)) called Google Colaboratory or just "colab", I started using it very recently. Colab provides you with a jupyter notebook like environment where you can do quick experimentation on a very powerful nvidia Tesla K80 GPU for free.

**Pros**
* Free
* Access to a powerful GPU machine
* Jupyter notebook like environment which is fairly easy to use

**Cons**
* 12 hours of continuous workspace access after which your virtual machine (VM) will be wiped clean (you'll have to continuously move data back and forth from google drive if you want to work for a longer duration)
* Limited GPU memory - although advertised that you get K80 GPU, this GPU is shared across multiple VMs and you don't get full 24 GB memory of a standard K80
* No `ssh`, so transferring files back and forth, writing scripts etc. is a bit of pain
* Installing non-standard libraries although feasible but is also non-trivial. I tried installing pytorch, caffe2 etc. on colab and it takes (read wastes) fair bit of time

## Getting started

I wrote a  quick colab notebook to do object detection using [SSD](https://arxiv.org/abs/1512.02325). It just does inference - nothing fancy but something to get started with.

[Link to the notebook](https://colab.research.google.com/drive/1NouuLFs-DwkvpJSbMoIrbTzkhR1iaaiP)

Some result from the notebook
![_config.yml](/images/colab/ssd1.png)

![_config.yml](/images/colab/ssd2.png)