---
layout: post
title:  "Mac에서 Haskell 하기"
date:   2011-12-02 15:54:00
categories: [programming]
tags: [programming]
---

### 설치

Mac에서 Haskell을 하려면 Haskell Platform을 설치하면 된다. Windows, Mac, Linux를 지원한다.

- http://hackage.haskell.org/platform/

위 링크에서 pkg를 받아 설치하면 된다. Xcode가 설치되어 있어야 한다. Haskell Platform에는 GHC (Glasgow Haskell Compiler)와 표준 라이브러리, 유틸리티, 문서가 포함되어 있다.

### 인터랙티브 모드

하스켈을 인터랙티브 모드에서 사용하려면 Terminal.app를 열고 ghci를 실행하면 된다.

```
$ ghci
```
