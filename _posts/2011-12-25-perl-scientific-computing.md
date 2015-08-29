---
layout: post
title:  "Perl 과학계산"
date:   2011-12-25 00:47:00
categories: [perl]
tags: [perl, scientific_computing]
---

###
PDL
PDL: Perl Data Language는 Perl에서 과학계산(Scientific Computing)을 가능하게 해 준다.

#### 설치

PDL 홈페이지에서 다운로드 받아 설치할 수 있다. Mac OSX 10.7 Lion에 가장 손쉽게 설치할 수 있는 방법은 SciPDL에서 pkg를 다운로드받아 설치하는 것이다. 클릭만 하면 자동으로 설치된다.

- http://sourceforge.net/projects/pdl/

이것만으로 되는 것은 아니다. PDL 모듈을 설치해야 한다. cpan을 이용하면 간단히 설치된다.

```
$ sudo cpan PDL
```

#### 실행

실행은 Terminal.app를 열고

```
$ perldl
```

이라고 치면 된다. 다음과 같이 pdl 프롬프트가 뜨면 간단하게 행렬 연산을 해 보자.

```
pdl> $A = pdl q[2, 2, 3; 4, 7, 8; 2, 3, 1];

pdl> print $A;

[
 [2 2 3]
 [4 7 8]
 [2 3 1]
]

pdl> $b = pdl q[1, 2, 1];

pdl> print $b x $A;

[
 [12 19 20]
]
```



