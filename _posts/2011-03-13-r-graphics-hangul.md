---
layout: post
title:  "R 그래프에 한글 쓰기"
date:   2011-03-13 18:37:00
categories: [tools]
tags: [tools]
---

Mac OS X용 R에서 그래프에 한글을 쓰려고 하면 네모만 나타난다. 이때는 다음처럼 글꼴을 지정해 주면 된다.

```
> par(family="AppleGothic")
> plot(0, main="한글제목")
```

여러 시스템에서 사용할 스크립트를 작성하고 있다면 경우라면 다음처럼 Mac OS일 때만 글꼴을 따로 지정해 줄 수도 있다.

```
if(Sys.info()[["sysname"]] == "Darwin") { par(family="AppleGothic") }
```

R console에서 한글이 포함된 그래프를 Quartz로 출력하는 데에는 문제가 없고 이렇게 출력된 그래프를 메뉴 "File > Save As"에서 PDF로 저장할 수 있다. 하지만, pdf()를 이용하여 직접 PDF 파일을 생성하려고 할 때는 다음처럼 Korean1deb 글꼴을 이용해야 한다.

```
> pdf("hangul-test.pdf")
> par(family="Korea1deb")
> plot(0, main="한글")
> dev.off()
```

다른 트루타입 글꼴을 사용하려고 하면 다음처럼 에러만 난다.

```
> pdf("hangul-test.pdf")
> par(family="AppleGothic")
> plot(0, main="title")
이하에 에러axis(side = side, at = at, labels = labels, ...) : 
  Invalid font type
추가정보:Warning messages:
1: In axis(side = side, at = at, labels = labels, ...) :
  font family not found in PostScript font database
2: In axis(side = side, at = at, labels = labels, ...) :
  font family not found in PostScript font database
3: In axis(side = side, at = at, labels = labels, ...) :
  font family not found in PostScript font database
4: In axis(side = side, at = at, labels = labels, ...) :
  font family not found in PostScript font database
5: In axis(side = side, at = at, labels = labels, ...) :
  font family not found in PostScript font database
6: In axis(side = side, at = at, labels = labels, ...) :
  font family not found in PostScript font database
7: In axis(side = side, at = at, labels = labels, ...) :
  font family not found in PostScript font database
```

