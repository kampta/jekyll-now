---
layout: project
title: Layout Generation and Completion with Self-attention
excerpt: A simple robust generative model for layouts; results on diverse real world datasets (3D objects, image, document layouts, mobile app wireframes)
code: https://github.com/kampta/DeepLayout
paper: https://arxiv.org/abs/2006.14615
gif: layout/layout_teasor.jpg
conference: ICCV 2021
---

  <div class="container">
  <nav_justify>
  <a href="https://kampta.github.io">Kamal Gupta<span class="sup">1</span></a>
  <a href="">Justin Lazarow<span class="sup">2</span></a>
  <a href="">Alessandro Achille<span class="sup">2</span></a>
  </nav_justify>
  </div>
  
  <div class="container" align="justify">
  <nav_justify>
  <a href="">Larry Davis<span class="sup">1,2</span></a>
  <a href="">Vijay Mahadevan<span class="sup">2</span></a>
  <a href="">Abhinav Shrivastava<span class="sup">1</span></a>
  </nav_justify>
  </div>
  
  <div class="container" align="center">
  <p><span class="sup">1</span>University of Maryland, College Park</p>
  <p><span class="sup">2</span>Amazon AWS</p>
  </div>
  
  <div class="container">
  <nav_justify>
  <a href="{{ page.code }}">[Code]</a>
  <a href="{{ page.paper }}">[arXiv]</a>
  <a href="https://www.youtube.com/watch?v=">[Video]</a>
  </nav_justify>
  </div>

  <br/>

  <img src="/images/{{ page.gif }}" alt="HTML5 Icon" style="float:left;margin-right:2em;margin-bottom:2em;">

  <div align="center">
    <h1>Abstract</h1>
  </div>

  <div align="justify">
    We address the problem of layout generation for diverse domains such as images, documents, and mobile applications.
    A layout is a set of graphical elements, belonging to one or more categories, placed together in a meaningful way.
    Generating a new layout or extending an existing layout requires understanding the relationships between these graphical elements.
    To do this, we propose a novel framework, LayoutTransformer, that leverages a self-attention based approach to learn contextual relationships between layout elements and generate layouts in a given domain.
    The proposed model improves upon the state-of-the-art approaches in layout generation in four ways.
    First, our model can generate a new layout either from an empty set or add more elements to a partial layout starting from an initial set of elements.
    Second, as the approach is attention-based, we can visualize which previous elements the model is attending to predict the next element, thereby providing an interpretable sequence of layout elements.
    Third, our model can easily scale to support both a large number of element categories and a large number of elements per layout. 
    Finally, the model also produces an embedding for various element categories, which can be used to explore the relationships between the categories.
    We demonstrate with experiments that our model can produce meaningful layouts in diverse settings such as object bounding boxes in scenes (COCO bounding boxes), documents (PubLayNet), and mobile applications (RICO dataset).
  </div>

  
   <div align="center">
    <h1>Cite</h1>
  </div>
  
```
@inproceedings{gupta2020improved,
  title={Layout Generation and Completion with Self-attention},
  author={Gupta, Kamal and Achille, Alessandro and Lazarow, Justin and Davis, Larry and Mahadevan, Vijay and Shrivastava, Abhinav},
  journal={arXiv preprint arXiv:2006.14615},
  year={2020}
}
```
