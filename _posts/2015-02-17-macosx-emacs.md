---
layout: post
title:  "MacOSX에서 Emacs 사용하기"
date:   2015-02-17 17:16:00
categories: [emacs]
tags: [macosx, emacs]
---

Mac에서는 Cocoa Emacs나 Aquamacs를 사용할 수 있다. Aquamacs에 관해서는 [여기](/articles/emacs/aquamacs)

- Cocoa Emacs
  - http://emacsformacosx.com/ : 바이너리 다운로드 받아 설치 가능.
  - http://www.gnu.org/software/emacs/ : 소스 코드
- Aquamacs
  - http://aquamacs.org/ : 디스크 이미지 (dmg) 다운로드
  - https://github.com/davidswelt/aquamacs-emacs : 소스 코드 저장소

Cocoa Emacs는 brew를 이용하여 설치할 수도 있다.

```
$ brew install emacs --HEAD --cocoa --with-librsvg --with-glib --with-imagemagick
$ brew linkapps emacs
```

지원하는 옵션을 확인하려면 `brew info emacs`.
