---
layout: post
type: guide
title: Intro to BitTorrent
excerpt: Learn about the etiquette and basic knowledge of the most popular means of piracy.
tags: ['p2p', 'torrent', 'trackers']
---

## Introduction
The BitTorrent protocol is a lot different from just downloading, and it comes with a community and standards. This guide will slowly teach you a basic understanding of it.


## Preface
- **P2P**: shorthand for “Peer to Peer.”
- **Broadband**: The download/upload speeds in essence.
- `hellow.txt`: Our example file with a size of *120 megabytes*
- **Shemp**: The server/user that'll have the original `hello.txt` file.
- **BitTorrent Client**: A app/client that can run peer to peer (p2p) connections/protocols.

> IMPORTANT: Use a VPN that supports p2p connections. If you do not use a VPN and live in a country that has copyright laws, you will be caught eventually for doing illegal activity, and charged a large fine.

## The Difference Between Direct Downloading And BitTorrent
> Note: Direct Downloading is like just downloading a normal file online, the acronym being DDL.

When you download something online there is one connection, from your computer to the server that has the file you want, in our case this file is going to be `hellow.txt`.

Now, you may be aware, you're not alone on the internet, other people may also want to download that file. BitTorrent makes the most efficient way to download the server by using your broadband to it's fullest.

## The Explanation
> Note: Everyone has 3 megabytes upload and download speed in this example.

**Shemp** has `hellow.txt`, and three people want to download this file. The picture below demonstrates this.

![download](https://qph.cf2.quoracdn.net/main-qimg-91d8480d1c1c619a9d158056633f57e6)

As we see, **Shemp** Is going full throttle to give everyone `hellow.txt`, and each person is getting 1Mb/min since Shemp can only handle giving everyone 1Mb/min. We can do much better than this.

Here we make `hellow.txt` into four 30Mb parts and **Shemp** gives one of the four parts part to each person, since **Shemp** has the original, we can discard the 4th part:

![download_parts](https://qph.cf2.quoracdn.net/main-qimg-f22031ad809256211de349c52b224ec4)

Now that Moe, Larry, and Curly each have 1/4 of `hellow.txt` and **Shemp** still has the full original, we can start the p2p connections.
> Note: No one has to have the full original, as long as all the data exists among everyone, it's possible to make a full copy.

![p2p_sharing](https://qph.cf2.quoracdn.net/main-qimg-2f904762ab9ef67ef605f75d65f33cc9-pjlq)


We connect everyone together and have them share the missing parts of the file with each other. This method of splitting and then connecting everyone together took a total of 1 hour. That's half the time it would take to Direct Download (DDL)!

Since Shemp, Moe, Larry, and Curly all have a copy of `hellow.txt`, they're referred to as a **swarm**. Now, when more people want `hellow.txt`, they can all contribute to giving any newcomers the `hellow.txt` file.

## Labels In a Swarm
Depending on how much you contribute, you can be classified as a **leech** and **seeder**. Theses labels depend on your **share ratio**. As you can imagine, a share ratio is a marker for the amount of data you've uploaded; below zero is leech, above zero is seeder.

A share ratio of 1 would mean you've downloaded all of `hellow.txt` and have uploaded `hellow.txt`. Having a share ratio of at least `0.5` is standard to being a good person in the BitTorrent community.

### What Is a Leecher?
A leecher is somebody that has a share ratio below zero. This means that they have not given/contributed at all after initially downloading the file. This is the common scenario for most people that run a BitTorrent client on a laptop or only to download files.

These people are frowned upon for not giving back and being utterly useless.

### What Is a Seeder?
A seeder is a person that is giving back to the community (the swarm). These people are awesome since that means they are running a BitTorrent client, contributing data to newer people in the swarm.

Usually these people have something called a **seedbox**, a computer that's on 24/7 that does BitTorrent things. They likely don't have a server/pc in their house, but instead pay for a service to run it for them in a country that has less strict piracy laws.

## How Do I Start Downloading Media?
There are two ways, a `.torrent` file and a `magnet` link. You should be able to find an input area easily, depending on what BitTorrent client you're using.

They both have the same effect and tell your BitTorrent client what **trackers** to use, and to start a P2P connection.

### What Is a Tracker?
A tracker is a very simple concept, it keeps track of other peers that have the data. It can't see anything at all, just a big list of people that are willing to share data.

So for example, we upload `hellow.txt` to a tracker, and it will let anyone know that starts to download `hellow.txt`, where it can find users willing to share data.

> Note: A tracker cannot see what you download or know what you have. It doesn't transfer data either. It's like looking at a phone book (tracker) and then using the phone (BitTorrent client).

### What Is An Indexer?
An indexer is a database that has a list of links to data to initiate a download and BitTorrent connection. These often ship with their own tracker, which is great for improving download speeds.

### Credits
- [Costya Preepelitsa on Quora](https://www.quora.com/How-does-BitTorrent-work?share=1) for the images. This is also the post I used 3 years ago to start my journey.