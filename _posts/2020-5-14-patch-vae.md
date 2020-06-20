---
layout: post
type: project
title: PatchVAE
excerpt: A patch-based VAE formulation to learn interesting parts of image, instead of the entire image. Our bottleneck formulation learns representation better for visual recognition tasks
code: https://github.com/kampta/PatchVAE
paper: https://arxiv.org/abs/2004.03623
gif: patchvae/teaser.gif
---

[**Code**](https://github.com/kampta/PatchVAE) &nbsp;&nbsp;&nbsp;
[**arXiv**](https://arxiv.org/abs/2004.03623) &nbsp;&nbsp;&nbsp;
[**Video**](https://www.youtube.com/watch?v=nshuuEzc3kc)

We propose a patch-based VAE formulation to learn interesting parts of image, instead of the entire image. Our bottleneck formulation learns representation better for visual recognition tasks.

![Teaser](/images/patchvae/teaser.png)

## Abstract

Unsupervised representation learning holds the promise of exploiting large amounts of unlabeled data to learn general representations. A promising technique for unsupervised learning is the framework of Variational Auto-encoders (VAEs). However, unsupervised representations learned by VAEs are significantly outperformed by those learned by supervised learning for recognition. Our hypothesis is that to learn useful representations for recognition the model needs to be encouraged to learn about repeating and consistent patterns in data. Drawing inspiration from the mid-level representation discovery work, we propose PatchVAE, that reasons about images at patch level. Our key contribution is a bottleneck formulation that encourages mid-level style representations in the VAE framework. Our experiments demonstrate that representations learned by our method perform much better on the recognition tasks compared to those learned by vanilla VAEs.

## Video

[![PatchVAE](http://img.youtube.com/vi/nshuuEzc3kc/0.jpg)](https://www.youtube.com/watch?v=nshuuEzc3kc "PatchVAE")

## Cite

```
@inproceedings{
    gupta2020patchvae,
    title={PatchVAE: Learning Local Latent Codes for Recognition},
    author={Kamal Gupta and Saurabh Singh and Abhinav Shrivastava},
    booktitle={Conference on Computer Vision and Pattern Recognition},
    year={2020},
    url={},
}
```