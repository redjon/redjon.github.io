---
layout: post
title:  "Perl 6 시작하기"
date:   2013-01-13 16:24:00
categories: [perl6]
tags: [perl]
---

우선 아주 간단한 것부터 정리해본다. 2013년 1월 현재.

Perl 6에 대해서 정보를 얻을 수 있는 곳은

- http://perl6.org/ - Perl6 홈페이지
- https://github.com/perl6 - Perl6 관련 저장소 목록

홈페이지에 있는 Documentation의 Using Perl 6를 한번 쭉 훑어보는 것이 괜찮은 듯 하다.


### Rakudo


Perl 6의 구현으로는 현재 Rakudo가 대표적이고 Niecza도 있다. Pugs는 이제 역사가 되었다.

- http://rakudo.org/ - Rakudo 홈페이지
- https://github.com/rakudo - Rakudo 관련 저장소 목록


#### 설치: 데비안 패키지

2014년 1월 현재 Debian testing에서 다음과 같이 설치할 수 있다.

```
$ sudo apt-get install rakudo
```

#### 설치: MacOSX에서 Homebrew

2014년 6월 현재 Mac에서도 Homebrew를 통해 간단하게 설치할 수 있다.

```
$ brew install rakudo-star
```

#### 설치: 소스코드

Perl 6를 사용해보려면 Rakudo Star를 설치한다. 소스 코드를 다운로드 받아 설치해보자.

- https://github.com/rakudo/star - Rakudo Star 저장소

한달에 한번씩 배포되고 있는데 최신 배포판을 받고 싶다면 다음 링크로 들어가서 찾아보자.

- https://github.com/rakudo/star/downloads

 Mac OSX에 설치하려면 기본적인 개발 도구들이 있어야한다. XCode가  설치되어 있다면 추가적으로 필요한 것은 없을 듯. 압축을 풀고 Configure.pl를 하자.

```
$ tar -xzvf rakudo-star-2012.11.tar.gz
$ cd rakudo-star-2012.11
$ perl Configure.pl --gen-parrot
```

한참 설정하고 나면 make를 하라고 나온다. 다음처럼 하면 된다.

```
$ make
$ make rakudo-test
$ make rakudo-spectest    # 시간 오래 걸린다. 별 문제 없을 것 같으면 안 해도 될 듯.
$ make install
```

이때 make install을 걱정할 필요없다. 시스템은 건드리지 않는다. 방금 압축을 풀고 make를 실행한 소스 코드 디렉토리 아래에 보면 install이라는 이름의 디렉토리가 있는데 거기에 설치되는 것이다. 실행은 

```
$ ./install/bin/perl6
```

와 같이 할 수 있다. 필요하면 PATH에 넣어주거나 ~/bin/perl6로 소프트 링크를 만들어주거나 하면 되겠다.


### REPL


간단하게 계산기로 사용해보자. 

```
$ perl6
> 3 + 4
7
> [+] 1, 2, 3, 4, 5
15
> [+] 1..10
55
> [*] 1..10
3628800
> ( 3 + 4 ) * 2
14
```

기본적인 수학 함수들도 사용할 수 있다.

```
> abs(-3)
3
> floor(3.2)
3
> ceiling(3.2)
4
> round(3.7)
4
> sqrt(2)
1.4142135623731
> exp(1)
2.71828182845905
> e
2.71828182845905
> 
> log(2)
0.693147180559945
> log10(2*64)
2.10720996964787
> pi
3.14159265358979
> cos(pi)
-1
> sin(pi/2)
1
> sin(pi/4)
0.707106781186547
> tan(pi/4)
1
```

변수도 이용할 수 있다.

```
> my $a = 3;
3
> my $b = 4;
4
> $a
3
> $b
4
> $a + $b;
7
```

서브루틴도 만들어 쓸 수 있다.

```
> sub sum(*@nums) { [+] @nums }
sub sum(*@nums) { ... }
> sum 1,2,3
6
> sum(1,2,3)
6
> sub mean(*@nums) { ([+] @nums) / @nums.elems }
sub mean(*@nums) { ... }
> mean 1, 2, 3, 4
2.5
```
