---
layout: post
type: normal
title: The Switch Project
excerpt: A Switch that is both a media server and a client
tags: ['switch', 'torrent', 'project']
---

# Switchroot is cool
When I was like 11 I wanted to watch movies for free on my nintendo DS, it was light weight, had a good screen and was nice to carry. So when the Nintendo Switch came out I was rather excited, only to learn if you plug in a SD card you can't play videos from it! I eventually rembered the project again late last year as I was starting to mess around with modding consoles like the PSP. I stumbled across a project called Switchroot which made it possible to install __Ubuntu on a Nintendo Switch__.

WOAH Linux on a switch? How? what?
> In short SwitchRoot found out that with enough firmware and accessing the recovery boot on a switch you can inject a payload due to a hardware issue.

## The Backend
First we need to create the backend, a seedbox. Since I want this to be easy to use for others, I'm just going to install [swizzin](https://swizzin.ltd) to manage the acctual seedbox portion of this project. I am also far to lazy to make my own set of scripts for this stuff when a totally good project already exists.

### Seedbox
I'll make a shell script to install Swizzin. The great thing about the apps on sizzin all run a local webserver so any advanced configuration beyond the defaults I make for the end-users can be done via a local web portal. Thank you radarr/sonarr devs.

Since I don't want to make a long series of prompts for the user for what torrent client and such, I'll make a bunch of pre-made configuration files and let the user decide from among those options. For context, Swizzin has a feature where you can make a configuration file and when passed onto Swizzin, Swizzin will intsall all the apps and configurations as specified. That way I can make a singular prompt for what "Style" seedbox they want and tell Swizzin to load the corsponding configuration file.

### Removing Packages
Switchroot's Ubuntu ships with a full desktop enviroment, which I don't want since I'll be making my own uzing [XMonad](https://xmonad.org/). First I'll strip out most of the default packages except for touchscreen managers and the joycon controller support, which should be easy enough... hopefully.

### The New Home Screen
I'm unsure of the default configuration yet but I'll utilize [Elkowar's Wacky Widgets](https://github.com/elkowar/eww) to manage the lock/poweroff, volume sliders, BUT to also act as the main launch center [example](https://github.com/adi1090x/widgets/blob/main/previews/dashboard.png). I will use XMonad for the actual launching of windows and managing keybinds.

## What about gaming
Emulation Station and all will be an option, I'll have to figure out how to make a pretty display to install the emulators though.

EWW is really easy to learn and customize, so by offering EWW as the launch center I hope to see people making their own complete settups and looks beyond the defaults I give them.

## VPN??
I'll be sure to include a prompt as to what vpn to install. Likely will offer Wireguard, Nord, or Mullvad as default options, otherwise ssh or connecct a keyboard and configure yourself.

## But why a Switch?
- I find it hilarious that having a Switch preform mass piracy since Nintendo hates that shit, but thier device would be sooooo good for it no??

- It supports 4k when docked, so this allows it to be both portable but also your home player, make sure to grab a terrabyte drive! If you're only ever going to use it mobile-wise then just have all your content filters be 720p.

- It's internals aren't amazing but absolutlely more then enough for media playback and maybe you can leave it off to the side for a bit and preform transcodes to help save space!

- Yes I could use a steamdeck, but allegedy this project would work on any ubuntu distro since it's just a pre-configuring a piracy settup for hand-helds. You'll just have to configure the controls yourself.