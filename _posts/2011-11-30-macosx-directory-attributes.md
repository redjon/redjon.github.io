---
layout: post
title:  "MacOSX 디렉토리 속성"
date:   2011-11-30 00:23:00
categories: [macosx]
tags: [macosx]
---



### GUI에서 숨김


MacOSX에서 Finder.app에서 홈 디렉토리를 열어보면 "라이브러리" 폴더가 보이지 않는다. 하지만 Terminal에서 보면 Library라는 폴더가 있다. 이것은 Library 폴더에 숨김 속성을 부여해 놓았기 때문이다. 이것을 보이게 하려면 터미널에서 다음 명령을 내리면 된다.

```
$ chflags nohidden ~/Library
```

다시 숨기려면 hidden으로 세팅하면 된다.

### 아이콘 바꾸기

- http://docs.info.apple.com/article.html?path=Mac/10.6/ko/8591.html
