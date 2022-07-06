---
layout: page
title: 
permalink: /about/
---


[comment]: <> ([Email]&#40;kamalgupta308@gmail.com&#41; &nbsp;&nbsp;/&nbsp;&nbsp;)

[comment]: <> ([Google Scholar]&#40;https://scholar.google.com/citations?user=tC3td8cAAAAJ&hl=en&#41; &nbsp;&nbsp;/&nbsp;&nbsp;)

[comment]: <> ([Github]&#40;https://github.com/kampta&#41; &nbsp;&nbsp;/&nbsp;&nbsp;)

[comment]: <> ([Twitter]&#40;https://twitter.com/kamalgupta09&#41; &nbsp;&nbsp;/&nbsp;&nbsp;)

[comment]: <> ([LinkedIn]&#40;https://www.linkedin.com/in/kamalgupta09/&#41;)

[comment]: <> (I am a Ph.D. candidate in the Department of [Computer Science]&#40;https://www.cs.umd.edu&#41; at [University of Maryland College Park]&#40;https://www.umd.edu&#41;. I am working with [Larry Davis]&#40;http://users.umiacs.umd.edu/~lsd/&#41; and [Abhinav Shrivastava]&#40;http://abhinavsh.info&#41;.)

[comment]: <> (In the past, I had fun building large-scale, commercial robotics and AI products in both industry and academia, specifically)

[comment]: <> (* Amazon [AWS Rekognition]&#40;https://aws.amazon.com/rekognition/&#41; in Pasadena, CA)

[comment]: <> (* A self-driving startup [Netradyne]&#40;http://netradyne.com/&#41; in Bengaluru, India)

[comment]: <> (* American Express Big Data Labs &#40;Now [Amex AI Labs]&#40;https://www.americanexpress.com/in/careers/ai-labs.html&#41;&#41; in Bengaluru, India)

[comment]: <> (* National ICT Australia &#40;or NICTA, now [Data 61]&#40;https://data61.csiro.au/&#41;&#41; in Sydney, Australia)

[comment]: <> (* [Robotics Institute]&#40;https://frc.ri.cmu.edu&#41;, CMU &#40;with [S. Singh]&#40;https://frc.ri.cmu.edu/~ssingh/Sanjiv_Singh/home.html&#41;, [S. Narasimhan]&#40;http://www.cs.cmu.edu/~srinivas/&#41;, [S. Nuske]&#40;https://www.linkedin.com/in/stephen-nuske-7ab4842/&#41;&#41; in Pittsburgh, PA)

[comment]: <> (* [Industrial Technology Research Institute]&#40;https://www.itri.org.tw/english/&#41; in Taiwan)

[comment]: <> (* [IIT Delhi]&#40;https://home.iitd.ac.in/&#41; &#40;with [M. Varma]&#40;https://www.microsoft.com/en-us/research/people/manik/&#41;, [SVN Vishwanathan]&#40;https://www.stat.purdue.edu/~vishy/&#41;, [S. Chaudhury]&#40;http://web.iitd.ac.in/~santanuc/&#41;&#41; in New Delhi, India)

[comment]: <> (I also briefly co-founded a startup helping users design their wardrobe by bringing fast fashion recommendations from social networks.)

I am a Ph.D. candidate in the Department of <a href="https://www.cs.umd.edu/">Computer Science</a> at 
<a href="https://www.umd.edu/">University of Maryland College Park</a> where I work with 
<a href="http://users.umiacs.umd.edu/~lsd">Larry Davis</a> 
and <a href="https://www.cs.umd.edu/~abhinav">Abhinav Shrivastava</a>. 

My research interests lie at the intersection of Computer Vision, Graphics, and Machine Learning. 
My long term goal is to enable storytellers to create intricate 3D visual content seamlessly.

[comment]: <> (I am a recipient of the Kulkarni fellowship and Dean's fellowship at the University of Maryland.)
In the past, I had fun building large-scale, commercial robotics and AI products in industries 
(<a href="https://github.com/NVlabs">NVIDIA</a>, 
<a href="https://www.amazon.science/">Amazon</a>, 
<a href="http://netradyne.com/">Netradyne</a>, 
<a href="https://www.americanexpress.com/in/careers/ai-labs.html">American Express</a>), 
research labs (<a href="https://data61.csiro.au">NICTA</a>, 
<a href="https://www.itri.org.tw/english">ITRI</a>) and academia (<a href="https://frc.ri.cmu.edu/">Carnegie Mellon</a>, 
<a href="https://home.iitd.ac.in">IIT Delhi</a>).
I also co-founded a startup helping users design their outfits by bringing the latest fashion recommendations from social networks.

## Recent News
* May 2022: Started an internship with Google AR and Google Research
* Apr. 2022: Outstanding Reviewer [Award](https://cvpr2022.thecvf.com/outstanding-reviewers) at CVPR 2022
* Jan. 2022: Outstanding Graduate Assistant [Award](https://www.gradschool.umd.edu/funding/student-fellowships-awards/outstanding-graduate-assistant-awards) by the Graduate School, UMD
* Sep. 2021: [PatchGame](https://kampta.github.io/pubs/NeurIPS2021_PatchGame.pdf) accepted to NeurIPS 2021
* July 2021: [LayoutTransformer](https://arxiv.org/abs/2006.14615) accepted to ICCV 2021
* May 2021: Started an internship at NVIDIA AI
* Feb. 2021: [LTH for Object Recognition](https://openaccess.thecvf.com/content/CVPR2021/html/Girish_The_Lottery_Ticket_Hypothesis_for_Object_Recognition_CVPR_2021_paper.html) accepted to CVPR 2021
* Oct. 2020: [Multiview Shapes](https://ieeexplore.ieee.org/abstract/document/9320100) accepted to 3DV 2020
* May 2020: Awarded [Kulkarni Fellowship](https://gradschool.umd.edu/funding/student-fellowships-awards/kulkarni-foundation-summer-research-fellowship)
* Feb. 2020: [PatchVAE](https://arxiv.org/abs/2004.03623) accepted to CVPR 2020

## Research Projects

[comment]: <> (I primarily work in Machine Learning and its applications in Vision, Graphics, Language and Robotics. I am also interested in building products with real-world impact in health-care, finance, sports and transportation.)

[comment]: <> (Some of my published works are)

<div class="posts">
  {% for post in site.posts %}
    {% if post.layout == "project" %}
    <article class="post">

      <img src="/images/{{ post.gif }}" alt="HTML5 Icon" style="width:180px;height:180px;float:left;margin-right:2em;">

      <p><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }} </a> ({{ post.conference}}) </p>
      <auth>{{ post.authors }} </auth>

      <div class="entry">
        {{ post.excerpt }}
      </div>

      <a href="{{ site.baseurl }}{{ post.url }}" class="read-more">Web</a> &nbsp;/&nbsp;
      <a href="{{ post.code }}" class="read-more">Code</a> &nbsp;/&nbsp;&nbsp;
      <a href="{{ post.paper }}" class="read-more">Paper</a>
    </article>
    {% endif %}
  {% endfor %}
</div>

# Blog
**Y**et **A**nother **M**achine **L**earning blog written with an intention of

* learning more by coding and writing. I strongly believe that the best way to learn a concept is to either code it myself or write a tutorial about it. This helps in both understanding various nuances associated with the concept as well as retain the concept for a longer time.
* keeping notes of various lectures/articles/papers/books/ideas I (have) come across. 

Check out the [blog page](http://kampta.github.io/blog) for more.

## Lernen durch Codierung
is german for Learning by Coding. It's a play on [Learning by Teaching](https://en.wikipedia.org/wiki/Learning_by_teaching), a strategy for students to learn by teaching their peers popular in Germany.

## Disclaimer
Contents of this blog are inference of a biological neural network, trained over a very tiny dataset for a very long time. Any statistically significant correlation to existing literature is not coincidental but an outcome of overfitting.

## Website
Finally moving from [old page](https://sites.google.com/site/kamalgupta308/) to Jekyll, hoping to do some justice to the new website cum blog. Promising myself to be more regular and more meticulous.

