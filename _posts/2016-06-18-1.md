---
layout: post
title:  "cleaning shop"
date:   2016-06-18 17:54:55 -0700
categories: setup
---
It's time for a clean start on my MacBook Pro. This post wipes the slate clean and restores a few essentials.

Create a backup of all assets:

* store assets on cloud services, such as Google Drive
* backup hard drive with Time Machine
* clone hard drive with SuperDuper!

Get a bootable copy of the OS:

* download El Capitan OS X from App Store
* create bootable USB on my thumb drive called peredor

```
sudo /Applications/Install\ OS\ X\ Mavericks.app/Contents/Resources/createinstallmedia -–volume /Volumes/peredor -–applicationpath /Applications/Install\ OS\ X\ Mavericks.app -–nointeraction
```

Erase everything on the hard drive:

* restart while holding CMD-R
* use Disk Utility to erase the hard drive

Install the OS:

* restart while holding Option
* select the app Install OS X Mavericks

Futz with System Preferences.

* update the OS

Restore all assets:

* install cloud services, such as Google Drive
* sync cloud services
* setup Time Machine

Ignore Google's complaint until it stops occurring:

* Google Drive asks where is findersyncapiextension
* it is located at
/Applications/Google Drive.app/Contents/PlugIns/FinderSyncAPIExtension.appex/Contents/MacOS/FinderSyncAPIExtension
* but this will go away after a restart

Install Command Line Developer Tools without installing XCode:

* initiate the download and install in Terminal

```
xcode-select --install
```

Some more general references for developer/data science setup are:

* <http://sourabhbajaj.com/mac-setup/>
* <https://github.com/nicolashery/mac-dev-setup#elasticsearch>
* <http://zmjones.com/mac-setup/>
