---
layout: project
title: A Compression Scheme for Handwritten Patterns Based on Curve Fitting
excerpt: A method to compress hand-written patterns recorded as strokes in order of their temporal occurrence using B-Spline Curves 
code: 
paper: http://www.iapr-tc11.org/archive/icdar2011/fileup/PDF/4520b115.pdf
gif: compression.jpg
png: compression.jpg
conference: ICDAR 2011
authors: K. Gupta, M. Bansal, S. Chaudhury
---

  <div class="container">
  <nav_justify>
  <a href="https://kampta.github.io">Kamal Gupta<span class="sup">1</span></a>
  <a href="">Manish Bansal</a>
  <a href="">Santanu Chaudhury</a>
  </nav_justify>
  </div>
  
  <div class="container" align="center">
  <p>Indian Institute of Technology Delhi</p>
  </div>
  
  <div class="container">
  <nav_justify>
  <a href="{{ page.code }}">[Code]</a>
  <a href="{{ page.paper }}">[arXiv]</a>
  <a href="https://www.youtube.com/watch?v=dtIt2eA2NrQ">[Video]</a>
  </nav_justify>
  </div>

  <br/>

  <div align="justify">
    A method to compress hand-written patterns recorded as strokes in order of their temporal occurrence using B-Spline Curves.
  </div>


  <img src="/images/{{ page.png }}" alt="HTML5 Icon" style="float:left;margin-right:2em;margin-bottom:2em;">


  <div align="center">
    <h1>Abstract</h1>
  </div>

  <div align="justify">
    We present here an idea of compression of user fed data from a touch screen input interface for storage and transmission over relatively lower bandwidth.
    The input is taken in the form of hand-written text, graphics, symbols or patterns and recorded as strokes in order of their temporal occurrence.
    The patterns are segmented into primitive forms each of which is then modeled with third order B-Spline Curves.
    The number of control points driving the Spline Curve is determined beforehand by recognizing the dominant points in the pattern.
    The significant reduction of redundancy in data can be exploited in wide application base including low-cost handheld device communication.
    This algorithm hence proposes a language independent tool for recording the handwriting of user in its original essence.
     Results obtained from preliminary testing on MATLAB and Android platform show significant improvement in compression ratio over the traditional storage and compression schemes
  </div>

  <div align="center">
    <h1>Video</h1>
  </div>
  
  <div class="entry" align="center">
  {% include youtube.html id="dtIt2eA2NrQ" %}
  </div>
  
   <div align="center">
    <h1>Cite</h1>
  </div>
  
```
@inproceedings{gupta2011compression,
  title={A compression scheme for handwritten patterns based on curve fitting},
  author={Gupta, Kamal and Bansal, Manish and Chaudhury, Santanu},
  booktitle={2011 International Conference on Document Analysis and Recognition},
  pages={1115--1119},
  year={2011},
  organization={IEEE}
}
```
