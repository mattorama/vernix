---
layout: post
title:  "git"
date:   2016-06-20
categories: setup
---
Following on from [cleaning shop]({{ site.baseurl }}{% post_url 2016-06-18-cleaning-shop %}), let's install the missing package manager.

## setting up ssh-key with github
mkdir ~/.ssh
cd ./.ssh
* generate a new ssh key
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
* enter a filename for the private key
github_mattorama
* enter a passphrase
St4...

Your identification has been saved in github_mattorama.
Your public key has been saved in github_mattorama.pub.
The key fingerprint is:
SHA256:RYn9+2QNPTAAb5zIbqmgCvvEP0DDSQY+uzo68ZQgh3g matthew.percival@gmail.com
The key's randomart image is:
+---[RSA 4096]----+
|..       +oo.    |
|. o     o.* .o   |
|.B .     o.*  o. |
|= E     ..o . ...|
|.* o .  S+   . o.|
|..= . . o   . o .|
|.=oo   .     +   |
|=oo..         .  |
|==. ..           |
+----[SHA256]-----+
* enable ssh-agent
eval "$(ssh-agent -s)"
* add the key and passphrase to the ssh agent
ssh-add ~/.ssh/id_rsa
* add the public key to github
pbcopy < ~/.ssh/id_rsa.pub
* add the ssh key in github personal settings
* test the ssh key
ssh -T git@github.com
* check the key fingerprint with that on github
ssh-add -l -E md5


## set up git
brew install git
git config --global user.name "mattorama"
git config --global user.email "mattorama@users.noreply.github.com"
* setup GitHub directory
mkdir ~/GitHub

* create a repo on github with a readme
* copy the remote ssh path
* go to terminal
```
cd ~/GitHub
git clone git@github.com:mattorama/test_0.git
cd ./test_0
git pull --rebase origin master
git push origin master
```
