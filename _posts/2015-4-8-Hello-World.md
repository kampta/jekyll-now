---
layout: post
title: You're up and running!
---

Moved to Jekyll and its sweet! Just need to update a markdown file per blog post and voilà!

## How to
For instructions refer [https://github.com/barryclark/jekyll-now](https://github.com/barryclark/jekyll-now). This will help you link your github account to the blog. No need of Jekyll on your local machine, as github takes care of it all. However, if you want to develop blog locally there are few gotchas.

## Gotchas
* Ruby (Version Control!?) - After spending an hour with my pre-installed, root owned version of Ruby and Gems, I moved to [rvm](https://rvm.io).
	* Install gpg2 with Homebrew - 
```
		brew install gnupg gnupg2
```
	* Install rvm - [https://rvm.io/](https://rvm.io/)
* Install jekyll - [https://help.github.com/articles/using-jekyll-with-pages/](https://help.github.com/articles/using-jekyll-with-pages/).

 That's it. Add ``` source ~/.rvm/scripts/rvm``` to your .bashrc file and hopefully you'd be able to use jekyll on your local machine seamlessly.
