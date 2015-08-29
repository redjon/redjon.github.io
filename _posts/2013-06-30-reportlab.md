---
layout: post
title:  "reportlab: Python PDF 라이브러리"
date:   2013-06-30 23:46:00
categories: [python]
tags: [python, pdf]
---

ReportLab은 Python에서 PDF 생성, XML 파싱, 텍스트 전처리 등을 할 수 있는 오픈소스 라이브러리를 제공한다. 이중 reportlab은 PDF를 생성할 수 있게 해주는 라이브러리이다.

### 설치

reportlab은 Python3을 지원하지 않는다. Python 2.7 버전을 사용해야한다. 설치는 간단하다.
$ easy_install reportlab

### 한글 또는 유니코드

사용법은 어렵지 않다. 매뉴얼도 잘 되어있다. 아무래도 한글이 잘 찍히느냐가 관심사일 것이다. 잘 된다. 글꼴 지정만 잘 해주면 된다. 아스키로만 된 문서를 찍는 기본적인 튜토리얼은 생략하고 한글을 찍는 방법을 보자. 한글 뿐만 아니라 유니코드의 문자를 다양하게 사용하는 경우도 마찬가지이다.

```python
#-*- coding: utf-8 -*-
# hello.py
from reportlab.pdfgen import canvas
from reportlab.pdfbase import pdfmetrics
from reportlab.pdfbase.ttfonts import TTFont

pdfmetrics.registerFont(TTFont("HCR Batang", "HANBatang-LVT.ttf"))

c = canvas.Canvas("hello.pdf")
c.setFont("HCR Batang", 16)
c.drawString(100,100, u"안녕")
c.showPage()
c.save()
```

위 코드에 대해 몇가지 코멘트를 달면 다음과 같다.
위 스크립트를 저정할 때 UTF-8 인코딩으로 저장해야한다. 한글을 직접 포함할 때 UTF-8을 사용하는 것이 좋다.
TTFont, pdfmetrics를 이용해 트루타입 글꼴에 이름을 부여하여 reportlab에서 사용할 수 있다.
글꼴파일 확인은 Linux나 MacOSX에서는 fc-list로 확인할 수 있다. 물론 다른 방법으로 해도 되겠지만...
위 예제에서는 함초롬바탕 첫가끝 글꼴을 사용하였다. 다운로드하려면: 함초롬체/GSUB @ KTUG
위 예제는 Canvas를 이용한 것으로 문서를 찍는 것이 아니라 그림을 그리면서 텍스트를 추가하는 예제이다.

### 문서 생성

아무래도 Canvas를 이용해서 그림을 그릴 일 보다는 문서를 생성할 일이 더 많을 것 같다. 문서를 생성할 때는 platypus가 사용된다. 간단한 예제를 보면 다음과 같다. 역시 한글을 사용하려면 글꼴을 이름을 붙여 등록해야하는 것은 물론이고 ParagraphStyle에서 원하는 한글 글꼴을 사용하도록 지정하여 새로운 스타일일 만들어주어야한다. 간단한 예제를 보이면 다음과 같다. 

```python
#-*- coding: utf-8 -*- 
# doc.py
from reportlab.lib.styles import getSampleStyleSheet, ParagraphStyle
from reportlab.lib.pagesizes import A4
from reportlab.platypus import Paragraph, SimpleDocTemplate
from reportlab.pdfbase import pdfmetrics
from reportlab.pdfbase.ttfonts import TTFont

pdfmetrics.registerFont(TTFont("HCR Batang", "HANBatang.ttf"))

styles = getSampleStyleSheet()
styles.add(ParagraphStyle(name="Hangul", fontName="HCR Batang"))

hangul1 = u"안녕하세요."
hangul2 = u"반갑습니다."

story = []
story.append(Paragraph(hangul1, style=styles["Hangul"]))
story.append(Paragraph(hangul2, style=styles["Hangul"]))
doc = SimpleDocTemplate("doc.pdf", pagesize=A4)
doc.build(story)
```

### 단락 내의 세세한 스타일 지정

위 예제에서는 Paragraph 단위로 스타일을 지정하는 것만 보았다. 한 단어만 빨간색으로 하고 싶거나 하면 어떻게 하는가? 이때는, 다른 방법이 있는지 모르겠지만, XML 태그를 이용한 스타일 마크업을 사용하는 것이 편리하다. 예를 들어 위 문서 생성 예제를 그대로 쓰는 대신에

```python
hangul1 = u'<font color="red">안녕</font>하세요'
```

와 같은 식으로 해주면 "안녕"이라는 부분은 빨간색으로 출력된다. 이렇게 작동한다는 것은, 다른 한편으로 생각하면, PDF로 생성하려는 대상 텍스트 파일에 태그가 들어있는데 그대로 출력하려면 &lt; 등으로 미리 바꾸어주어야 제대로 되 결과를 얻을 수 있다는 것이다.
