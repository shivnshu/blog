---
layout: post
title:  "Journey from Windows to Arch Linux"
comments: true
categories: programming os
---

Windows, the most popular operating system, works well for the day-to-day activities but is of little help when it comes to programming and development.

Inspired by seniors, I took my first step towards using Ubuntu, the most popular linux, as my host operating system about a year ago. It felt very uncomfortable at first to use this not-so-good-looking OS. But overtime, the simplicity and the ease of use overshadowed the unsightly UI. Various open-source tools and extensions helped me further to get rid of so-seemed unattractive look(_which I later discovered was the real beauty_).

As my voyage of exploring computers continued, I fell in love with Ubuntu(_which really was the love for linux_). Motivated by my interest in Security, I tried installing some pentesting tools, but it failed miserably and I was many a time left with broken packages. Consequently, I decided to use Kali Linux, the most popular Linux for pentesters.

The Kali Linux installation became my first messy and time-consuming one. At that point in time, it had some problems with its Grub bootloader. Nevertheless, my never-say-die attitude motivated me to try again and again but all my efforts proved futile. It was then that I realised that triple booting could fix the issue. I installed Ubuntu in a partition and Kali in another without any bootloader, updated Grub using Ubuntu, thus got all the three entries like a charm.

I used Kali as my host OS for the next 2 months, playing with its awesome set of tools. Then, I heard of [LFS](http://www.linuxfromscratch.org/lfs/), Arch and Gentoo. At first, I was too scared to try them on my host system, and so I used Virtual Box. But I was bold enough to try LFS. Installing LFS boosted my confidence and not long after, I was accustomed to installing various OS.

Finally, I decided to install Arch on my host system. I deleted all the partitions on my hard disk including EFI, and created them afresh. After more or less 4 hours of keeping up with the installation process tackling problems alongside, I had it installed and then furnished it with a awesome Desktop Environment(GNOME). Later, I had to deal with the great Windows bootloader overwriting skills after installing Windows in another partition (_Again Office Stuff_).

#### Why Arch Linux?
Why not [Gentoo](https://www.gentoo.org/)? I have used Gentoo for some time, and was impressed by its documentation. The concept of compiling packages in whichever customised way you wish using [USE flags](https://wiki.gentoo.org/wiki/USE_flag), felt exciting. But, the process is tedious and time-consuming( _my laptop is not that fast_ ). It took me 5 hours just to install it. Considering the amount of time and risk associated with this process, I find Arch Linux apt for a host OS at present.
