---
layout: post
title:  "Lion에서 LG NAS 접속 에러"
date:   2011-11-08 00:40:00
categories: [macosx]
tags: [macosx]
---

Lion으로 업그레이드한 후에 LG NAS에 afp로 접속하려고 하니 에러가 난다. 이 서버 버전에서는 접속이 안 된다는 에러이다. 이 에러를 피하려면 설정을 바꾸어야 한다. 다음 링크 참조.

참조: http://www.alexanderwilde.com/2011/04/os-x-lion-connection-error-with-afp-and-workaround


1)  Terminal.app를 실행하고 다음 명령을 내린다.

```
$ sudo chmod o+w /Library/Preferences
$ defaults write /Library/Preferences/com.apple.AppleShareClient afp_host_prefs_version -int 1 
```

2) Finder를 열고 Command + K를 눌러서 AFP 서버를 연결한다. 여전히 에러가 난다.

3)  다시 Terminal.app를 열어서 다음 명령을 내린다.

```
$ sudo defaults write /Library/Preferences/com.apple.AppleShareClient afp_disabled_uams -array “Cleartxt Passwrd” “MS2.0″ “2-Way Randnum exchange”
$ sudo chmod o-w /Library/Preferences
```
