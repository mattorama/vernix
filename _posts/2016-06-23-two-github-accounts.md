---
layout: post
categories: git
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
* add the public key to github

```
pbcopy < ~/.ssh/github_workname.pub
```

* add the ssh key in github personal settings

* enable ssh-agent

```
eval "$(ssh-agent -s)"
```

* add the key and passphrase to the ssh agent

```
ssh-add ~/.ssh/github_workname
```

* test the ssh keys for both accounts:

```
ssh -T git@github.com
ssh -T git@work.github.com
```


* create a config file at ```~/.ssh/config```:

```
# Normal account
Host github.com
  HostName github.com
  PreferredAuthentications publickey
  IdentityFile ~/.ssh/github_mattorama

# Other account
Host work.github.com
  HostName github.com
  PreferredAuthentications publickey
  IdentityFile ~/.ssh/github_workname
```
* the "normal" identity will remain as the "default"

* from GitHub, copy the url for cloning a repo to the clipboard and try to clone it
* modify the url host to match the host for the work account in the config file:

```
cd ~/GitHub
git clone git@work.github.com:workname/work_repo.git
```
* use git config for each work repository to override the global settings:

```
cd ./work_repo
git config user.name "workname"
git config user.email "workname@work.com"
```

* verify using ```git remove -v``` in a personal and work repository
