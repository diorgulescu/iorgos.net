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