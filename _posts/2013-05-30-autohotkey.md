---
layout: post
title:  "MS Windows에서 AutoHotKey로 CapsLock과 Control 바꾸기"
date:   2013-05-30 16:36:00
categories: [mswin]
tags: [mswin]
---

[AutoHotKey](http://www.autohotkey.com/)는 윈도우즈에서 자동화를 가능하게 해주는데 CapsLock과 Control을 바꾸는 용도로 쓸 수도 있다. 다음과 같은 내용으로 capslock2control.ahk라는 파일을 만들어 두고 더블클릭해서 실행시키면 된다.

```
+Capslock::Capslock ; make shift+Caps-Lock the Caps Lock toggle
Capslock::Control   ; make Caps Lock the control button
```

특정 프로그램에서만 CapsLock이 Control이 되도록 할 수도 있다. 다음처럼 하면 된다.

```
#IfWinActive emacs  ; if in emacs
+Capslock::Capslock ; make shift+Caps-Lock the Caps Lock toggle
Capslock::Control   ; make Caps Lock the control button
#IfWinActive        ; end if in emacs
```
