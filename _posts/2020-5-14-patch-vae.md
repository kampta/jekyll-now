---
layout: project
title: PatchVAE - Learning Local Latent Codes for Recognition
excerpt: A patch-based VAE formulation to learn interesting parts of image, instead of the entire image. Our bottleneck formulation learns representation better for visual recognition tasks
code: https://github.com/kampta/PatchVAE
paper: https://arxiv.org/abs/2004.03623
gif: patchvae/teaser.gif
png: patchvae/teaser.png
---

  <div class="container">
  <nav_justify>
  <a href="https://kampta.github.io">Kamal Gupta<span class="sup">1</span></a>
  <a href="https://research.google/people/SaurabhSingh">Saurabh Singh<span class="sup">2</span></a>
  <a href="http://abhinavsh.info">Abhinav Shrivastava<span class="sup">1</span></a>
  </nav_justify>
  </div>
  
  <div class="container" align="center">
  <p><span class="sup">1</span>University of Maryland, College Park</p>
  <p><span class="sup">2</span>Google Research</p>
  </div>
  
  <div class="container">
  <nav_justify>
  <a href="{{ page.code }}">[Code]</a>
  <a href="{{ page.paper }}">[arXiv]</a>
  <a href="https://www.youtube.com/watch?v={{ page.video }}">[Video]</a>
  </nav_justify>
  </div>

  <br/>

  <div align="justify">
    We propose a patch-based VAE formulation to learn interesting parts of image, instead of the entire image. 
    Our bottleneck formulation learns representation better for visual recognition tasks.
  </div>

  <img src="/images/{{ page.png }}" alt="HTML5 Icon" style="float:left;margin-right:2em;margin-bottom:2em;">

  <div align="center">
    <h1>Abstract</h1>
  </div>

  <div align="justify">
    Unsupervised representation learning holds the promise of exploiting large amounts of unlabeled data to learn general representations.
    A promising technique for unsupervised learning is the framework of Variational Auto-encoders (VAEs).
    However, unsupervised representations learned by VAEs are significantly outperformed by those learned by supervised learning for recognition.
    Our hypothesis is that to learn useful representations for recognition the model needs to be encouraged to learn about repeating and consistent patterns in data.
    Drawing inspiration from the mid-level representation discovery work, we propose PatchVAE, that reasons about images at patch level.
    Our key contribution is a bottleneck formulation that encourages mid-level style representations in the VAE framework.
    Our experiments demonstrate that representations learned by our method perform much better on the recognition tasks compared to those learned by vanilla VAEs.
  </div>

  <div align="center">
    <h1>Video</h1>
  </div>
  
  <div class="entry" align="center">
  {% include youtube.html id="nshuuEzc3kc" %}
  </div>
      
   <div align="center">
    <h1>Cite</h1>
  </div>
  
```
@inproceedings{
    gupta2020patchvae,
    title={PatchVAE: Learning Local Latent Codes for Recognition},
    author={Kamal Gupta and Saurabh Singh and Abhinav Shrivastava},
    booktitle={Conference on Computer Vision and Pattern Recognition},
    year={2020},
    url={http://patchvae.umiacs.io},
}
```
