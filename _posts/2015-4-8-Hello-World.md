---
layout: post
title: You're up and running!
excerpt: Moved to Jekyll and its sweet! Just need to update a markdown file per blog post and voilà!
---

## How to
For instructions refer [https://github.com/barryclark/jekyll-now](https://github.com/barryclark/jekyll-now). This will help you link your github account to the blog. No need of Jekyll on your local machine, as github takes care of it all. However, if you want to develop blog locally there are few gotchas.

## Gotchas

### Ruby on OS X
After spending an hour with my pre-installed, root owned version of Ruby and Gems, I moved to [rvm](https://rvm.io).

* Install gpg2 with Homebrew - 
```
brew install gnupg gnupg2
```

* Install rvm - [https://rvm.io/](https://rvm.io/)

### Ruby on Ubuntu

Same instructions should work fine.

```
gpg --keyserver hkp://keys.gnupg.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3
\curl -sSL https://get.rvm.io | bash -s stable --ruby
```

If you see an error:

```
curl: (77) error setting certificate verify locations:
  CAfile: /etc/pki/tls/certs/ca-bundle.crt
  CApath: none
```

do following:

```
sudo apt-get install ca-certificates
sudo mkdir -p /etc/pki/tls/certs
sudo ln -s /etc/ssl/certs/ca-certificates.crt /etc/pki/tls/certs/ca-bundle.crt
```

### Jekyll
You might need to install following gems

```
gem install jekyll
gem install jekyll-sitemap
gem install jekyll-feed
```

---
That's it. Add ``` source ~/.rvm/scripts/rvm``` to your .bashrc file and hopefully you'd be able to use jekyll on your local machine seamlessly.

