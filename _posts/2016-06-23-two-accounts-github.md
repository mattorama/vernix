---
layout: post
title:  "two account github"
date:   2016-06-23
categories: setup
---
Following on from [git]({{ site.baseurl }}{% post_url 2016-06-20-git %}), let's configure things so that you can work with two github accounts over ssh from one terminal.

### create a second ssh key and add to the second github account

* create a second ssh key:

```
cd ~/.ssh
ssh-keygen -t rsa -C "other_username@other.com"
```

* enter a new filename, e.g., ```github_other```
* enter a passphrase
* add this other ssh key to your other GitHub account using the browser

* enable ssh-agent

```
eval "$(ssh-agent -s)"
```

* add the key and passphrase to the ssh agent

```
ssh-add ~/.ssh/github_other
```

* add the public key to github

```
pbcopy < ~/.ssh/github_other.pub
```

* add the ssh key in github personal settings
* test the ssh keys for both accounts

```

```

* create a config file at ```~/.ssh/config```:

```
# Normal account
Host github.com
  HostName github.com
  PreferredAuthentications publickey
  IdentityFile ~/.ssh/id_rsa

# Other account
Host other.github.com
  HostName github.com
  PreferredAuthentications publickey
  IdentityFile ~/.ssh/id_rsa_other
```

* check both accounts can connect to GitHub

```
 ssh -T git@github.com
 ssh -T git@other.github.com
```
