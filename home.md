---
layout: page
title: 
permalink: /about/
---

I am a Ph.D. candidate in the Department of [Computer Science](https://www.cs.umd.edu) at [University of Maryland College Park](https://www.umd.edu). I am working with [Larry Davis](http://users.umiacs.umd.edu/~lsd/) and [Abhinav Shrivastava](http://abhinavsh.info).
In the past, I had fun building large-scale, commercial robotics and AI products in both industry and academia, specifically

* Amazon [AWS Rekognition](https://aws.amazon.com/rekognition/) in Pasadena, CA
* A self-driving startup [Netradyne](http://netradyne.com/) in Bengaluru, India
* American Express Big Data Labs (Now [Amex AI Labs](https://www.americanexpress.com/in/careers/ai-labs.html)) in Bengaluru, India
* National ICT Australia (or NICTA, now [Data 61](https://data61.csiro.au/)) in Sydney, Australia
* [Robotics Institute](https://frc.ri.cmu.edu), CMU (with [S. Singh](https://frc.ri.cmu.edu/~ssingh/Sanjiv_Singh/home.html), [S. Narasimhan](http://www.cs.cmu.edu/~srinivas/), [S. Nuske](https://www.linkedin.com/in/stephen-nuske-7ab4842/)) in Pittsburgh, PA
* [Industrial Technology Research Institute](https://www.itri.org.tw/english/) in Taiwan
* [IIT Delhi](https://home.iitd.ac.in/) (with [M. Varma](https://www.microsoft.com/en-us/research/people/manik/), [SVN Vishwanathan](https://www.stat.purdue.edu/~vishy/), [S. Chaudhury](http://web.iitd.ac.in/~santanuc/)) in New Delhi, India

I also briefly co-founded a startup helping users design their wardrobe by bringing fast fashion recommendations from social networks.

[Email](kamalgupta308@gmail.com) &nbsp;&nbsp;/&nbsp;&nbsp;
[Google Scholar](https://scholar.google.com/citations?user=tC3td8cAAAAJ&hl=en) &nbsp;&nbsp;/&nbsp;&nbsp;
[Github](https://github.com/kampta) &nbsp;&nbsp;/&nbsp;&nbsp;
[Twitter](https://twitter.com/kamalgupta09) &nbsp;&nbsp;/&nbsp;&nbsp;
[LinkedIn](https://www.linkedin.com/in/kamalgupta09/)

# Research
I primarily work in Machine Learning and its applications in Vision, Graphics, Language and Robotics. I am also interested in building products with real-world impact in health-care, finance, sports and transportation.
Some of my published works are

<div class="posts">
  {% for post in site.posts %}
    {% if post.layout == "project" %}
    <article class="post">

      <img src="/images/{{ post.gif }}" alt="HTML5 Icon" style="width:180px;height:180px;float:left;margin-right:2em;">

      <h3><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a> </h3>
      <i>{{ post.conference}}</i>

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
This is **Y**et **A**nother **M**achine **L**earning blog written with an intention of

* learning more by coding and writing. I strongly believe that the best way to learn a concept is to either code it myself or write a tutorial about it. This helps in both understanding various nuances associated with the concept as well as retain the concept for a longer time.
* keeping notes of various lectures/articles/papers/books/ideas I (have) come across. 

Check out the [blog page](http://kampta.github.io/blog) for more.

## Lernen durch Codierung
is german for Learning by Coding. It's a play on [Learning by Teaching](https://en.wikipedia.org/wiki/Learning_by_teaching), a strategy for students to learn by teaching their peers popular in Germany.

## Disclaimer
Contents of this blog are inference of a biological neural network, trained over a very tiny dataset for a very long time. Any statistically significant correlation to existing literature is not coincidental but an outcome of overfitting.

## Website
Finally moving from [old page](https://sites.google.com/site/kamalgupta308/) to Jekyll, hoping to do some justice to the new website cum blog. Promising myself to be more regular and more meticulous.

