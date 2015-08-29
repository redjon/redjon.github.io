---
layout: post
title:  "SBCL 설치 및 설정"
date:   2012-02-20 23:59:00
categories: [lisp]
tags: [lisp]
---

### Debian
설치는 간단하다. sbcl 패키지만 설치하면 된다. slime 패키지도 함께 설치하면 좋다.

```
$ sudo apt-get install sbcl slime
```

따로 설정하거나 할 것은 없다. Emacs에서 M-x slime으로 slime 모드를 실행할 수 있다.


### Mac
#### SBCL 설치
SBCL을 다운로드 받아 압축을 풀고 다음 명령을 내리면 자신의 홈 디렉토리 아래 설치된다.

```
INSTALL_ROOT=$HOME sh install.sh
```

그리고 SBCL_HOME 환경변수를 설정한다. .bash_profile에 다음 행을 추가하면 된다.

```
export SBCL_HOME=$HOME/lib/sbcl
```

Brew를 이용하고 있다면 설치가 간편하다.

```
$ brew install sbcl
```

#### SLIME 설정
CL 프로그래밍을 위한 환경이 여럿 있지만 아무래도 그중의 최고는 Slime일 것이다.

- http://redjonathan.blogspot.com/2011/02/slime.html



## 스크립트 실행

다음과 같이 hello.lisp이라는 파일을 작성하면

```lisp
#!/usr/local/bin/sbcl --script
(write-line "Hello, World!")
```

실행 가능하게 퍼미션을 준 후에

```
$ ./hello.lisp
```

로 실행할 수 있다. 또는 hashbang 라인이 없어도 다음처럼 실행할 수 있다.

```
$ sbcl --script hello.lisp
```

- 참조: http://www.sbcl.org/manual/Shebang-Scripts.html

## 바이너리 컴파일

다음과 같은 lisp 소스를 작성하고 파일 이름은 hello.lisp이라고 하자.

```lisp
(defun main()
  (write-line "Hello, World!"))
```
sbcl을 실행하고 interactive 모드에서 다음 명령을 실행하면 바이너리 파일이 생성된다.

```lisp
(load "hello.lisp")
(sb-ext:save-lisp-and-die "hello" :executable t :toplevel 'main)
```

이제 다음처럼 제대로 바이너리 파일이 만들어졌는지 확인해 보자.

```
$ ./hello
Hello, World!
```
