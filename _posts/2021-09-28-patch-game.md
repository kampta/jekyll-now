---
layout: project
title: PatchGame - Learning to Signal Mid-level Patches in Referential Games
excerpt: Emergent communication via mid-level patches in a referential game played on a large-scale image dataset
code: https://github.com/kampta/PatchGame
paper: https://arxiv.org/abs/2111.01785
gif: patch_game.jpg
conference: NeurIPS 2021
authors: K. Gupta, G. Somepalli, A. Gupta, V. Jayasundara, M. Zwicker, A. Shrivastava
---

  <div class="container">
  <nav_justify>
  <a href="https://kampta.github.io">Kamal Gupta</a>
  <a href="https://somepago.github.io">Gowthami Somepalli</a>
  <a href="">Anubhav Gupta</a>
  </nav_justify>
  </div>
  
  <div class="container" align="justify">
  <nav_justify>
  <a href="https://vinojjayasundara.github.io/">Vinoj Jayasundara</a>
  <a href="http://www.cs.umd.edu/~zwicker/">Matthias Zwicker</a>
  <a href="https://www.cs.umd.edu/~abhinav">Abhinav Shrivastava</a>
  </nav_justify>
  </div>
  
  <div class="container" align="center">
  <p>University of Maryland, College Park</p>
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
    We study a referential game (a type of signaling game) where two agents communicate with each other via a discrete bottleneck to achieve a common goal. 
    In our referential game, the goal of the speaker is to compose a message or a symbolic representation of “important” image patches,
    while the task for the listener is to match the speaker’s message to a different view of the same image. 
    We show that it is indeed possible for the two agents to develop a communication protocol without explicit supervision.
    We further investigate the developed protocol and show the applications in speeding up recent Vision Transformers by 
    using only important patches, and as pre-training for downstream recognition tasks (e.g., classification).
  </div>

  
   <div align="center">
    <h1>Cite</h1>
  </div>
  
```
@inproceedings{gupta2021patchgame,
  title={PatchGame: Learning to Signal Mid-level Patches in Referential Games},
  author={Gupta, Kamal and Somepalli, Gowthami and Gupta, Anubhav and Jayasundara, Vinoj and Zwicker, Matthias and Shrivastava, Abhinav},
  journal={Advances in Neural Information Processing Systems},
  year={2021}
}
```
