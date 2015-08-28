---
layout: post
title:  "MacOSX 터미널 한글 자동 완성"
date:   2015-02-17 15:01
categories: [maosx]
tags: [macosx]
---

터미널에서 한글이 자동 완성되지 않는 것은 bash 버전이 낮기 때문이다. help 명령을 내려보면 버전을 확인할 수 있다.

```
$ help
GNU bash, version 3.2.53(1)-release (x86_64-apple-darwin13)
...
```


최신 버전을 설치하자. http://ftp.gnu.org/gnu/bash/에서 소스 코드를 다운로드 받아서 설치하거나 brew로 설치하거나 한다.

```
$ brew install bash
```

이렇게 설치한 bash는 다음 경로로 실행할 수 있다.

```
$ /usr/local/bin/bash
```

방금 설치한 최신 버전의 bash가 기본 셸로 작동하도록 하자. 우선 /private/etc/shells 파일을 열고 맨 아랫줄에 다음처럼 경로를 추가해 준다.

```
/bin/bash
/bin/csh
/bin/ksh
/bin/sh
/bin/tcsh
/bin/zsh
/usr/local/bin/bash
```

다음으로 기본으로 실행되는 /bin/bash를 삭제하고 최신 bash로 링크를 걸어준다.

```
$ cd /bin
$ sudo mv bash bash3.2
$ sudo ln -s /usr/local/bin/bash bash
```

이제 터미널 창을 새로 열고 버전을 확인해보자.

```
$ help
GNU bash, version 4.3.33(1)-release (x86_64-apple-darwin13.4.0)
...
```

한글 자동 완성이 잘 될 것이다.
