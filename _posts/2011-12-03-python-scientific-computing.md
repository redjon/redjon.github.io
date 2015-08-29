---
layout: post
title:  "파이썬 과학 계산"
date:   2011-12-03 10:22:00
categories: [python]
tags: [python, scientific_computing]
---
Python Scientific Computing

- SciPy: numpy와 scipy. 과학계산을 위한 파이썬 라이브러리. 오픈소스 (New BSD).
- matplotlib: 파이썬 2차원 그래프 라이브러리. 오픈소스 (BSD compatible). 
- IPython: 파이썬 인터랙티브 과학계산을 편리하게. 오픈소스 (BSD).
- SymPy: 파이썬 Symbolic mathematics 라이브러리. 오픈소스 (New BSD)
- EPD (Enthought Python Distribution): 상용이지만 아카데믹 버전은 무료. Enthought는 SciPy를 서포트하는 회사이다.
- PyIMSL Studio: 상용이지만 비상업적 용도는 무료.

IPython과 함께 SciPy, matplotlib, SymPy를 함께 사용하면 MATLAB이나 Mathematica와 같은 기능을 가지게 된다.


### 설치

SciPy는 NumPy와 SciPy로 이루어져 있다. 설치는 홈페이지의 설명을 보고 해야 한다. 버전에 따라서 운영체제에 따라서 상황이 다를 수 있다. Mac OSX 10.7 Lion에서 기본으로 설치되어 있는 python 2.7.1을 사용할 때에 SciPy는
http://fonnesbeck.github.com/ScipySuperpack/
를 이용해서 설치하는 것이 편리하다. 이것을 이용하면 다른 과학계산 관련 패키지들도 한꺼번에 설치할 수 있다.

IPython은 다음 명령으로 간단히 설치할 수도 있다.

```
$ sudo easy_install ipython
```

### 실행

ipython을 pylab모드로 실행하면 편리하다. numpy, matplotlib 모듈을 기본적으로 사용할 수 있다.

```
$ ipython --pylab
```


### EPD

EPD는 상용이지만 아카데믹 버전은 무료로 제공된다. 홈페이지 들어가서 학교 메일 주소만 써주면 다운로드 링크를 보내준다. Mac용, Windows용, Linux용으로 32bit, 64bit 버전이 제공된다. 과학 계산용 라이브러리들이 모두 함께 패키징되어 있어 편리하다. NumPy, SciPy, IPython, matplotlib과 같은 라이브러리는 물론이고 Enthought에서 만들어진 2D 그래픽 라이브러리 Chaco도 포함되어 있다.

