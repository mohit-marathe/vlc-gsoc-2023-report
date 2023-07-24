# My GSoC 2023 Report

**Student:** Mohit Marathe([@mohit-marathe](https://code.videolan.org/mohit-marathe))

**Organization:** [VideoLAN](https://www.videolan.org/)

**Project:** [VLC Qt Interface Redesign](https://summerofcode.withgoogle.com/programs/2023/projects/z26bcE5j)

**Mentor:** Pierre Lamot

---

## Overview

VLC is a free and open-source cross-platform multimedia player and framework that plays most multimedia files as well as DVDs, Audio CDs, VCDs, and various streaming protocols. Check out the [official site](https://www.videolan.org/vlc/) for more information. 

## Project 

The goal of this project is to contribute to the development of VLC 4.0.0, an upcoming version that showcases a redesigned interface. The project focuses on enhancing user experience and introducing a more intuitive "media center" feel. 

Within this context, the project entails integrating the new interface with the existing media library and current interface. By incorporating various features, the aim is to enhance usability and enrich the software with additional functionalities. These improvements will empower users with a more intuitive and feature-rich media playback experience. 

VLC uses QML(Qt Modeling Language) as the front end and C++ as the back end.

## Work

### Community Bonding Period

In this period, I mostly focused on gaining a solid grasp of QML and Qt framework in general. For this, I followed [Qt/QML Tutorial Playlist](https://www.youtube.com/playlist?list=PL6CJYn40gN6hdNC1IGQZfVI707dh9DPRc) by KDAB. I also read some of the chapters of the book [Qt5 Cadaques](http://qmlbook.github.io/).

Apart from these, I tried to work on some issues as it is the best way to learn about the codebase.

### Some Merge Requests before the official coding period

### [Fix alignment issues when qt-safe-area is enabled](https://code.videolan.org/videolan/vlc/-/merge_requests/3446)

VLC 4 provide the ability to run on TV (on a set-top box, or a raspberry pi for example), TV has constraints regarding where you're allowed to put graphical elements,  see https://en.wikipedia.org/wiki/Safe_area_(television). There were some alignment issues in this setup. 
I didn't even know QML when I started working on this issue 😅. But with the help of my mentor, I got my first patch merged to VLC.

### [Add option for opening parent folder in MLContextMenu](https://code.videolan.org/videolan/vlc/-/merge_requests/3437)

![Screenshot_20230714_182851](https://github.com/mohit-marathe/vlc-gsoc-2023-report/assets/96789026/3bc7fc1c-1c89-4488-9646-139740f0af25)

This was supposed to be a _good first issue_ but it turned out to be a bit challenging (at least for beginners). I learned a lot about VLC's codebase while working on this issue as I had to understand how each component connects with each other. Working on this MR gave me good insights about model-view-delegate architecture in Qt.
Initially, I wrote the function to open parent directory 2 times (for video and audio), and then my mentor suggested I refactor it (to avoid code duplication). Then I learned about a really powerful thing called [template](https://en.m.wikipedia.org/wiki/Template_(C%2B%2B)) in C++, with the help the which I was able to refactor the function.


### Coding Period

### [Redesign Synchronization Page](https://code.videolan.org/videolan/vlc/-/merge_requests/3796)

| Before      | After |
| ----------- | ----------- |  
![](screenshots/TracksPageAudio_before.png) | ![](screenshots/TracksPageAudio_after.gif)
![](screenshots/TracksPageSubtitle_before.png) | ![](screenshots/TracksPageSubtitle_after.png)

This was my first task in the coding period. The idea was to make synchronizing audio and subtitles easier for the users. Now you don't have to calculate the delay in the track manually. I learned about a lot of things includings things specific to Qt framework and also a lesson on good code design vs bad code design. It was while working on this feature that I realized the power of **Signals** and **Slots** in Qt. I also learned about how to create custom components in C++ that can be used in QML. 
Initially I connected the delay buttons with the spinbox to change the value of subtitle or audio delay in the spinbox, which will then change the delay. This was an easier and intuitive way to implement this feature but its a bad code design because this is how it works: **Calculate Delay with the help of buttons --> Change the value of SpinBox --> Change the actual delay to the value of SpinBox**__. This is also known as [spaghetti code](https://en.wikipedia.org/wiki/Spaghetti_code). My mentor suggested this instead: _**Calculate Delay with the buttons --> Change the delay to the calculated delay**_. The reason why the latter structure is better is because its less complicated and hence easier to maintain.


### [Add option to delete Discover/URL items in MLContextMenu](https://code.videolan.org/videolan/vlc/-/merge_requests/3819)

With VLC, you can stream videos or radio from the internet by using URL. After you stream any media, it gets added to the history. The task was to add an option to delete any media item from the history. 
While working on this task, I learned how to use [glue code](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=&cad=rja&uact=8&ved=2ahUKEwj1xKDNjaaAAxUgSWwGHaaGC5YQFnoECBgQAw&url=https%3A%2F%2Fen.wikipedia.org%2Fwiki%2FGlue_code&usg=AOvVaw2B0EirDGNdV-8WF5TVlMjF&opi=89978449) to access code from different modules that would otherwise be incompatible. I also learned to use [Lambda expressions](https://en.cppreference.com/w/cpp/language/lambda) in C++.


### [Add preset layouts in Preferences](https://code.videolan.org/videolan/vlc/-/merge_requests/3924)

VLC allows a lot of customization options. The task was to add some preset layouts for the user to choose from.

















