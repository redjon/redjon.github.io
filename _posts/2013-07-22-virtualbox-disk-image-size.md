---
layout: post
title:  "VirtualBox 디스크 이미지 사이즈 크기 줄이기"
date:   2013-07-22 00:09:00
categories: [admin]
tags: [admin]
---

Virtual Box 디스크 이미지는 크기를 정적(static)하게 구성할 수도 있고 동적(dynamic)으로 구성할 수도 있다. 동적으로 구성하는 것이 공간을 절약할 수 있다. 예를 들어, 40G로 할당하여도 실제 이미지 크기는 40G가 되지 않고 파일이 있는 만큼만 차지를 한다. 그런데 MS Windows를 쓰다보면 파일이 조각 나면서, 예를 들어, 파일은 6G 밖에 없는데 VDI 크기는 30G가 되기도 한다. 이때 VDI 크기를 줄이려면

- 가상머신에서 조각 모음을 실행한다.
- 가상머신에서 sdelete -z c:로 디스크의 빈 공간을 깨끗하게 지운다.
- 호스트에서 VBoxManage modyfyhd Win.vdi --compact 명령을 내린다.

참조: [How to compact your Virtual Disks](https://blogs.oracle.com/virtualbox/entry/how_to_compact_your_virtual)
