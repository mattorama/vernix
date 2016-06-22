---
layout: post
title:  "git"
date:   2016-06-20
categories: setup
---
Following on from [cleaning shop]({{ site.baseurl }}{% post_url 2016-06-18-cleaning-shop %}), let's install the missing package manager.


brew tap caskroom/cask
brew install brew-cask

brew install Caskroom/cask/xquartz
brew cask install java

# brew tap is where different kinds of things are stored together
brew tap homebrew/science
brew install R

brew install Caskroom/cask/rstudio

# For latex:
brew cask install mactex

brew install libsvg curl libxml2 gdal geos boost

R CMD javareconf JAVA_CPPFLAGS=-I/System/Library/Frameworks/JavaVM.framework/Headers
