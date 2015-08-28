---
layout: post
title:  "MacOSX에서 원격 파일 시스템 공유"
date:   2015-02-02 14:20:00
categories: [macosx]
tags: [macosx]
---

## 터미널에서 마운트하는 방법

원격 서버 주소가 server.name이라 하고 shared라는 이름으로 AFP 프로토콜로 공유된 디렉토리가 있을 때:

```
$ mount -t afp afp://username:password@server.name/shared /Volumes/mounted
```

원격 서버 주소가 server.name이고 shared라는 이름으로 SMB로 공유된 디렉토리가 있을 때:

```
$ mount -t smbfs smb://username:password@server.name/shared /Volumes/mounted
```
