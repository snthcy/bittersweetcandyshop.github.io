---
layout: post
type: normal
title: The Switch Project
excerpt: A Nintendo Switch that is both a media server and a client
tags: ['switch', 'torrent', 'project']
---

# SwitchRoot Is Cool
When I was like 11 I wanted to watch movies for free on my Nintendo DS, it was lightweight, had a good screen, and was nice to carry. So when the Nintendo Switch came out, I was rather excited, only to learn if you plug in a SD card you can't play videos from it! I eventually remembered the project again late last year as I was starting to mess around with modding consoles like the Sony PSP. I stumbled across a project called SwitchRoot, which made it possible to install __Ubuntu on a Nintendo Switch__.

WOAH, Linux on a switch? How? what?
> In short, SwitchRoot found out that with enough firmware and accessing the recovery boot on a Switch, you can inject a payload due to a hardware issue it suffers from.

## The Backend
First, we need to create the backend, known as a seedbox. Since I want this to be easy to use for others, I'm just going to install [swizzin](https://swizzin.ltd) to manage the actual seedbox portion of this project. I am also far too lazy to make my own set of scripts for this stuff, when a totally good project already exists.

### Seedbox
I'll make a shell script to install Swizzin. The great thing about the apps on Swizzin is that they all run a local web server, so any advanced configuration beyond the defaults I make for the end-users can be done via the built-in web portal. Thank you, Radarr/Sonarr devs.

Since I don't want to make a long series of prompts for the user for what torrent client and such, I'll make a bunch of pre-made configuration files and let the user decide from among those options. For context, Swizzin has a feature where you can make a configuration file and when passed onto Swizzin, Swizzin will install all the apps and configurations as specified. That way, I can make a singular prompt for what “style” seedbox they want, and tell Swizzin to load the corresponding configuration file.

### Removing Packages
SwitchRoot's Ubuntu ships with a full desktop environment, which I don't want since I'll be making my own using [XMonad](https://xmonad.org/). First, I'll strip out most of the default packages except for touchscreen managers and the joycon controller support, which should be easy enough… hopefully.

### The New Home Screen
I'm unsure of the default configuration yet, but I'll utilize [Elkowar's Wacky Widgets](https://github.com/elkowar/eww) to manage the lock/power off, volume sliders, but to also act as the main launch center [example](https://github.com/adi1090x/widgets/blob/main/previews/dashboard.png). I will use XMonad for the actual launching of windows and managing keybinds.

## What About Gaming?
Emulation Station and all the other emulators will be an option, though I'll have to figure out how to make a pretty display to install the emulators.

EWW is very easy to learn and customize, so by offering EWW as the launch center, I hope to see people making their own complete setups and looks beyond the defaults I give provide for them.

## VPN??
I'll be sure to include a prompt as to what VPN you can install. I'll likely offer Wireguard, NordVPN, or Mullvad as default options, otherwise SSH or connect a keyboard and configure yourself.

## But Why a Switch?
- I find it hilarious to use a Switch to perform mass piracy, since Nintendo hates that shit. Wouldn't their device be sooo good for it, no?

- It supports 4K resolution when docked, so this allows it to be both portable but also your home player. Make sure to grab a terabyte drive! If you're only ever going to use it mobile-wise, then just have all your content filters be in 720p.

- Its internals aren't amazing, but it's absolutely more than enough for media playback, and maybe, you can leave it off to the side for a bit and preform transcodes to help save space!

- Yes, I could use a Steam Deck, but allegedly, this project would work on any Ubuntu distro, since it's just a pre-configuring a piracy setup for handhelds. You'll just have to configure the controls yourself.