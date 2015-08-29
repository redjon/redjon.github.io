---
layout: post
title:  "Mac에서 오픈 소스 소프트웨어 사용하기"
date:   2011-11-12 13:46:00
categories: [macosx]
tags: [macosx]
---

### 소프트웨어 모음 사이트

맥에서 사용할 수 있는 오픈 소스 소프트웨어 모음 사이트

- http://www.freesmug.org/
- http://opensourcemac.org/
- http://opensourcemac.com/


### 패키지 시스템

Mac에서 오픈소스 소프트웨 소프트웨어 설치를 관리해 주는 시스템으로는 MacPorts, Fink가 꽤나 오래전 부터 사용되어 왔고 Homebrew가 나름 새롭게 등장되어 인기를 끌고 있다. 결론적으로 정리해 보자면 Fink는 업데이트가 늦어서 MacPorts를 쓰는 것이 낫다. 이 둘은 유닉스 툴을 쓸 수 있는 시스템을 거의 통째로 Mac으로 끌고 들어오는 것이다. 설치하는 데 시간이 꽤나 오래 걸리고 하드 디스크도 상당히 차지하고 기존의 설치된 것들과 중복이 되거나 충돌이 있을 수 있다. 이 둘과 달리 Homebrew는 설치하고자 하는 특정 소프트웨어만 의존성을 최소화하여 설치해준다는 점에서 인기를 끌고 있다. 유닉스 시스템을 본격적으로 쓸 것이라면 MacPorts, 단지 원하는 소프트웨어 몇 개를 쓰고 싶은 것이라면 Homebrew. 이 정도로 정리될 듯 하다.

- Hombrew http://mxcl.github.com/homebrew/
  - github에 등록
  - Ruby scripts
- MacPorts http://www.finkproject.org
  - BSD ports 시스템의 영향
  - 소스 코드 받아서 컴파일해서 설치. 일부는 바이너리로.
- Fink http://www.finkproject.org
  - sourceforge에 등록
  - Unix 오픈 소스 소프트웨어를 Mac OS X에
  - Debian 패키지 시스템 기반. 바이너리 다운로드 받아 설치.
  - Perl scripts
  
참조
- http://tedwise.com/2010/08/28/homebrew-vs-macports/
- http://www.astrobetter.com/do-you-homebrew-does-it-outdo-macports-and-fink/
- http://bitboxer.de/2010/06/03/moving-from-macports-to-homebrew/


