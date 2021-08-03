---
title: My Homelab
date: 2021-05-24 17:51:42
---
![Example image](/static/image.png)
# My Homelab
## Why on Earth would I even bother to build one?

Because I really love playing around with various devices, testing out configurations and learning new stuff along the way. The thought of building my own “playground”/homelab occurred to me some years ago, but I’ve only just now got motivated enough to actually go ahead & build it (Thanks COVID-19!).

Since I live in a relatively small 2-bedroom apartment with extremely curious little boys, space constraints are a given (so are child safety “gadgets”, here and there). Hence my discreet living room setup. The weird diagram is an attempt at illustrating how everything is configured at the moment.

Over the last year, I went through three “incarnations” of this homelab. The first one was the most complex, but gradually moved towards simpler setups for various reasons (datailed below), as I began to define clear goals for myself.

## Purpose of a homelab
+ Have FUN!
+ Learn/Re-learn/Consolidate some networking knowledge (from a Systems Admin’s standpoint)
+ Learn Ansible, Kubernetes, Docker, Terraform & other similar "beauties"
+ Play with & Learn NetBSD’s ATF (Automated Testing Framework)/Kyua(ATF 2.0), which is also available on FreeBSD
+ Revisit & Update knowledge on LDAP (AD & OpenLDAP)
+ Deploy virtual network environments in order to prepare & learn for future certification exams
+ Experiment a lot
+ Have MORE FUN!

I've mainly worked as a Software Test Engineer (and have been for 15 years), but I also occasionally take care of test labs/environments and I plan on picking a different career path (oriented on DevOps & Cybersecurity). I do have an itch for embedded systems, a bit of programming, obscure operating systems & BSDs. Therefore this setup is quite useful for learning (especially for my future certification exams).

## Current setup
image


This one is “stable” at the moment, in the sense that I don’t feel a need to expand it even further. You could say I’m turning into some sort of a minimalist.
Hardware checklist

+ 1 x Dell OptiPlex 3050 Mini (8 GB RAM, Intel(R) Core(TM) i5-7500T CPU @ 2.70GHz, 1 nVME SSD & 1 480 GB SATA III SSD) - runs Linux Mint, used as a home fileserver, NextCloud server & media center (it’s connected to the TV, which is useful for YouTube and Netflix when needed)
+ 2 x Seagate 4TB USB3 HDD - these are connected to the OptiPlex in a RAID1 configuration (soft RAID using mdadm) and these hold our photos, movie clips, the photos uploaded by our phones when we get home and some other stuff
+ 1 x TP-Link Archer C80 - wireless router handling our home traffic
+ 1 x Brother HL-1222WE monochrome laser printer (networked)
+ 1 x HP ProBook 650 G4 laptop (Intel(R) Core(TM) i7-8850H CPU @ 2.60GHz with 6 cores and 9MB L3 cache, 32 GB DDR4 memory and a 500 GB nVME SSD) - my daily driver and powerhorse. Runs Ubuntu Linux and libvirt/qemu for virtualizing stuff needed for GNS3 labs (networking, infrastructure tests, etc.), also used for casual & office activities, but also serves as a little workstation for editing photos, clips & audio tracks I sometimes record.

### Additional hardware
+ 1 x Raspberry Pi Zero W
+ 1 x Texas Instruments Launchpad MSP-EXP430F5529LP (because I’m into some embedded C programming and learning a few things in this area)

## Previous incarnations
### The Third
![Example image](/images/homelab/third.jpg)

Mainly replaced the Dell Wyse stations & the Atrust Thin client with a Lenovo ThinkCentre MS720, which ran VMWare ESXi 7. This is also when I purchased my current laptop, the HP ProBook 650 G4. Still had the two RPi v2 boards for FreeBSD & NetBSD tests.

###The second “incarnation”
![Example image](/images/homelab/second.jpg)

I decided to make my life a bit easier, so I got rid of the RPi cluster (except for two older RPi v2s) and purchased two used Dell Wyse mini-PCs.

#### Hardware Checklist
+ 1 x Dell OptiPlex 3050 Mini (8 GB RAM, Intel(R) Core(TM) i5-7500T CPU @ 2.70GHz, 1 nVME SSD & 1 480 GB SATA III SSD)
+ 2 x Dell Wyse mini-PCs (running Proxmox VE and RHEL 8.3)
+ 1 x Atrust Thin Client (running Ubuntu Server)

### The very FIRST “incarnation”
![Example image](/images/homelab/ansamblu.jpg)
A discreet homelab, hidden away from curious toddlers' hands

image
#### Network diagram

This was also the largest one, of course. I was overly-enthusiastic and didn’t really have any precise goals. A Raspberry Pi cluster was also included, because I found the idea to be very fascinating and cool.

#### Hardware checklist
+ 2 x Raspberry Pi 2 v1.1
+ 3 x Raspberry Pi 4 4GB
+ 1 x Raspberry Pi 4 8GB (for running VMWare ESXi Fling for ARM)
+ 1 x Anker PowerPort 60W Desktop USB power source (with 6 ports, each getting 2.4 Amps)
+ 2 x GeekPi Acrylic cluster cases for Raspberry Pi (needed two sets for building a larger stack)
+ 1 x Western Digital 250 GB SSD USB3.1 (used as a datastore for VMWare ESXi, on the Pi)
+ 1 x Atrust Intel-based thin client (an older, refurbished and fanless machine)
+ 1 x SuperMicro A1SAi mini-server based on the A1SRi-2358F motherboard, running VMWare ESXi (hosting an instance of pfSense that takes care of routing and LAN segments)
+ 1 x Proxmox VE Server (this is my former desktop that got converted to a server), based on an AMD Ryzen 5 CPU with 32 GB DDR4 & almost 1 TB SSD storage
+ 1 x Dell OptiPlex 3050 Micro (7th gen i5, 8 GB DDR4, Windows 10 Pro) acting as a media & file server (it’s linked to the TV and it also runs a Syncthing server to which our mobile phones upload photos - instead of relying on Google Photos, OneDrive, etc.)
+ 1 x TP-Link TL-WR841N/ND v7 (my 10-year old WiFi router, now running OpenWRT and taking care of the wireless network associated with the lab)
+ 1 x 8-port Netgear GS308E Gigabit managed switch
+ 2 x UK-to-EU power plug adapters
+ 1 x Zyxel 5-port Gigabit managed switch
+ Cables

Building the first lab

I first took the Supermicro server, cleaned it up and placed it in the bottom drawer of a simple IKEA living room organizer. I actually dismantled the back of the drawer (made of pretty solid plastic) in order to have access to all ports and help with ventilation.
image 	image 	image

I placed the power sockets on top of it in a manner that doesn’t cover the server’s fans. I use two separate multiple socket thingies, each with an ON/OFF button. One of them is for the Raspberry Pi cluster, because I want to be able to shut that thing off when I’m not actively working with it.
image 	image
Assembling the Raspberry Pi cluster

I did this in two consecutive evenings, with children-induced chaos & stress. Just kidding, I just used a few small chunks of spare time to put it together. The GeekPi cluster case is built to house 4 boards. Since I wanted to have 7, I had to purchase two sets. No biggie, they’re quite cheap. Nothing much to say here, just playing around with minuscule screws and pins. The GeekPi comes with a lot of heatsinks and one fan for each of the devices you want to add to it.
image 	image 	image
image 	image 	image
Putting it all together

Now, on to the top drawer, which will host the Atrust thin client, Netgear switch, Raspberry Pi cluster along with the Anker power supply and the good ol’ TP-Link WiFi router. In order to keep things a bit spaced, I’ve used a “Variera” kitchen cupboard organizer. Naturally, all equipment has “rubber feet”. First, place the USB power source, the thin client and the router, along with their cables. Then, fit in the organizer and insert the Netgear switch and the RPi cluster on top of it (again, using some glued rubber pads just to keep things safe).
image 	image 	image
image 	image 	image

Time to get down on my knees and make the cable mess less messy.
image

Insert all cables and give it a go. Boy, that does sound good!
image 	image 	image

The ex-desktop (now server) running Proxmox VE can be seen in the third photo

#### What did I use it for?

Well, the Supermicro server had VMWare ESXi installed on it. pfSense ran in a VM and was binded to three physical NICs on the server (named WAN, LAB & CLUSTER). This VM handled Internet traffic coming through from the crappy router provided by my ISP. I also ran a few other lightweight VMs on this server, like Pi-hole & Alpine Linux.

The Raspberry Pis were used for learning Kubernetes, Docker, Ansible, k3s/Rancher and toying around with NetBSD’s Kyua/ATF (an automated testing framework for Net & FreeBSD - this was done on the RPi 2s). One of the RPis ran VMWare ESXi for ARM, for testing & more (lighter) virtualization. The Atrust thin client was linked to the cluster and it was mainly used as a machine for coordinating the boards (Ansible & the like).

Dell OptiPlex 3050 Micro is a great mini-PC that’s used as a media center (on Windows 10 Pro) for streaming services. It also ran Syncthing (which we used at the time, before moving to NextCloud).

Finally, the Proxmox VE server was used for more hardcore virtualization, mainly for studying/re-learning Windows & UNIX servers at a more “business-like” level (Directory Services in mixed environments, unattended Windows deployments, Hyper-V administration, etc.).
Why did I move on?

Well, the Raspberry Pi cluster was too much of a mess for my taste. The RPi 4 gets WAY too hot so coolers were on almost 24/7 and I quickly noticed that, for my needs, the same computing power could be achieved with computers that did not require such complexity. After this, I replaced the cluster with two Dell Wyse mini-PCs.