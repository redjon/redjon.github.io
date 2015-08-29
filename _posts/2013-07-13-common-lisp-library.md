---
layout: post
title:  "Common Lisp 라이브러리"
date:   2013-07-13 23:20:00
categories: [lisp]
tags: [lisp]
---

### Quicklisp


[Quicklisp](http://www.quicklisp.org/)는 라이브러리 관리자이다. 현재 (2013–07–13) Quicklisp에서는 약 700여개의 라이브러리를 지원하고 있다. 자동으로 라이브러리를 다운로드 받고 설치해준다. ASDF는 새로운 라이브러리의 다운로드 기능을 제공하지 않는다.


#### 설치

다운로드를 받고

```
$ curl -O http://beta.quicklisp.org/quicklisp.lisp
```

clisp을 실행시키고 quicklisp.lisp를 불러들인 후에 설치 명령을 내린다. $HOME/quicklisp에 설치된다.

```lisp
CL-USER> (load "quicklisp.lisp")
CL-USER> (quicklisp-quickstart:install)
```

설치는 완료되었다. 이후에는 다음처럼 quicklisp를 불러들인 후 사용하면 된다.

```lisp
CL-USER> (load "~/quicklisp/setup.lisp")
```

#### 사용

사용하고 싶은 라이브러리를 quickload하면 된다. 해당 라이브러리가 없으면 자동으로 다운로드받아 설치해준다. 예를들어, 정규표현 라이브러리 cl-ppcre를 사용하려는 경우에 다음처럼 명령을 내리면 된다.

```lisp
CL-USER> (ql:quickload "cl-ppcre")
CL-USER> (cl-ppcre:split "\\s+" "hello world")
("hello" "world")
```

### ASDF


[ASDF](http://common-lisp.net/project/asdf/)는 Anonther System Definition Facility의 약자이다. make 같은 역할을 하는 것으로 CLISP 라이브러리를 빌드할 때 사용되는 도구이다. SBCL 1.1.8에는 기본으로 포함되어 있다.
