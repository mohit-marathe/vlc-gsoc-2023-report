# My GSoC 2023 Report

**Student:** Mohit Marathe([@mohit-marathe](https://code.videolan.org/mohit-marathe))

**Organization:** [VideoLAN](https://www.videolan.org/)

**Project:** [VLC Qt Interface Redesign](https://summerofcode.withgoogle.com/programs/2023/projects/z26bcE5j)

**Mentor:** Pierre Lamot

---

## Overview

VLC is a free and open source cross-platform multimedia player and framework that plays most multimedia files as well as DVDs, Audio CDs, VCDs, and various streaming protocols. Check out the [official site](https://www.videolan.org/vlc/) for more information. 

## Project 

The goal of this project is to contribute to the development of VLC 4.0.0, an upcoming version that showcases a redesigned interface. The project focuses on enhancing user experience and introducing a more intuitive "media center" feel. 

Within this context, the project entails integrating the new interface with the existing media library and current interface. By incorporating various features, the aim is to enhance usability and enrich the software with additional functionalities. These improvements will empower users with a more intuitive and feature-rich media playback experience. 

VLC uses QML(Qt Modeling Language) as front-end and C++ as the back-end.

## Work

### Community Bonding Period

In this period, I mostly focused on gaining solid grasp on QML and Qt framework in general. For this I followed [Qt/QML Tutorial Playlist](https://www.youtube.com/playlist?list=PL6CJYn40gN6hdNC1IGQZfVI707dh9DPRc) by KDAB. I also read some of the chapters of the book [Qt5 Cadaques](http://qmlbook.github.io/).

Apart from these I tried to work on some issues as it is the best way to learn about the codebase.

### Some Merge Requests before the official coding period

### [Fix alignment issues when qt-safe-area is enabled](https://code.videolan.org/videolan/vlc/-/merge_requests/3446)

VLC 4 provide the ability to run on TV (on a set top box, or a raspberry pi for example), TV have constraints regarding where you're allowed to put graphical elements,  see https://en.wikipedia.org/wiki/Safe_area_(television). There were some alignment issues in this setup. 
I didn't even know QML when I started working on this issue 😅. But with the help of my mentor, I got my first patch merged to VLC.

### [Add option for opening parent folder in MLContextMenu](https://code.videolan.org/videolan/vlc/-/merge_requests/3437)

![Screenshot_20230714_182851](https://github.com/mohit-marathe/vlc-gsoc-2023-report/assets/96789026/3bc7fc1c-1c89-4488-9646-139740f0af25)

This was supposed to be a _good first issue_ but it was turned out to be a bit difficult (atleast for beginners). I learned a lot about VLC's codebase while working on this issue as I had to understand how each components connects with each other. 






