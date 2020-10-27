---
layout: project
title: Improved Modeling of 3D Shapes with Multi-view Depth Maps
excerpt: A novel encoder-decoder generative model for 3D shapes using multi-view depth maps; SOTA results on single view reconstruction and generation
code: https://github.com/kampta/multiview-shapes
gif: multiview-shapes/teaser.gif
png: multiview-shapes/teaser.png
paper: https://arxiv.org/abs/2009.03298
conference: 3DV 2020
---

  <div class="container">
  <nav_justify>
  <a href="https://kampta.github.io">Kamal Gupta<span class="sup">1</span></a>
  <a href="https://www.cs.umd.edu/people/jsreddy">Susmija Jabbireddy<span class="sup">1</span></a>
  <a href="">Ketul Shah<span class="sup">2</span></a>
  </nav_justify>
  </div>
  
  <div class="container" align="justify">
  <nav_justify>
  <a href="http://abhinavsh.info">Abhinav Shrivastava<span class="sup">1</span></a>
  <a href="http://www.cs.umd.edu/~zwicker/">Matthias Zwicker<span class="sup">1</span></a>
  </nav_justify>
  </div>
  
  <div class="container" align="center">
  <p><span class="sup">1</span>University of Maryland, College Park</p>
  <p><span class="sup">2</span>John Hopkins University</p>
  </div>
  
  <div class="container">
  <nav_justify>
  <a href="{{ page.code }}">[Code]</a>
  <a href="{{ page.paper }}">[arXiv]</a>
  <a href="https://www.youtube.com/watch?v=dxZfornP_OY">[Video]</a>
  </nav_justify>
  </div>

  <br/>

  <div align="justify">
    A novel encoder-decoder generative model for 3D shapes using multi-view depth maps; SOTA results on single view reconstruction and generation.
  </div>

  <img src="/images/{{ page.png }}" alt="HTML5 Icon" style="float:left;margin-left:2em;margin-right:2em;margin-bottom:2em;">  

  <div align="center">
    <h1>Abstract</h1>
  </div>

  <div align="justify">
    We present a simple yet effective general-purpose framework for modeling 3D shapes by leveraging recent advances in 2D image generation using CNNs.
    Using just a single depth image of the object, we can output a dense multi-view depth map representation of 3D objects.
    Our simple encoder-decoder framework, comprised of a novel identity encoder and class-conditional viewpoint generator, generates 3D consistent depth maps.
    Our experimental results demonstrate the two-fold advantage of our approach.
    First, we can directly borrow architectures that work well in the 2D image domain to 3D.
    Second, we can effectively generate high-resolution 3D shapes with low computational memory.
    Our quantitative evaluations show that our method is superior to existing depth map methods for reconstructing and synthesizing 3D objects and is competitive with other representations, such as point clouds, voxel grids, and implicit functions.
  </div>

  <div align="center">
    <h1>Video</h1>
  </div>
  
  <div class="entry" align="center">
  {% include youtube.html id="dxZfornP_OY" %}
  </div>
  
   <div align="center">
    <h1>Cite</h1>
  </div>
  
```
@inproceedings{gupta2020improved,
  title={Improved Modeling of 3D Shapes with Multi-view Depth Maps},
  author={Gupta, Kamal and Jabbireddy, Susmija and Shah, Ketul and Shrivastava, Abhinav and Zwicker, Matthias},
  booktitle={International Conference on 3D Vision},
  year={2020},
  url={http://shapes.umiacs.io},
}
```
