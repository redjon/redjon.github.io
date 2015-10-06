---
layout: post
title:  "LibreOffice Macro"
date:   2011-12-09 14:51:00
categories: [tools]
tags: [tools]
---

LibreOffice 또는 OpenOffice 또는 NeoOffice에서는 여러가지 언어로 매크로를 작성할 수 있다.

현재 MacOSX Lion에서 LibreOffice 3.4.4를 사용하고 있다. 한국어 팩도 설치했다.

### 매크로 기능 활성화

우선, LibreOffice를 실행하고 "LibreOffice" 메뉴 아래 "환경설정" 창을 열고 "LibreOffice >  일반" 탭을 연후에 "실험적인 (불안정한) 기능 사용"에 체크한다.

이제 "도구" 메뉴 아래 "매크로 > 매크로관리"를 보면 다음과 같은 목록을 볼 수 있다.

- LibreOffice Basic
- JavaScript
- BeanShell
- Python

Basic, JavaScript, BeanShell은 편집 기능을 제공하지만 Python은 편집 기능을 제공하지 않는다.

### 스크립트 파일 경로

#### LibreOffice 매크로

"도구 > 매크로 > 매크로관리 > Python"에 들어가 보면 다른 언어도 마찬가지이지만 "LibreOffice 매크로"아래 이미 만들어진 몇개 매크로가 들어있는 것을 볼 수 있다. 이 매크로들은

`/Applications/LibreOffice.app/Contents/basis-link/share/Scripts`

디렉토리 아래 언어별로 나누어 들어있다.

#### 내 매크로

그리고 같은 창에 "내 매크로"라는 것도 있는데 그 아래에는 자신이 만든 매크로가 있다면 그 목록이 나타난다. 이것들은 자신의 홈 아래

`~/Library/Application\ Support/LibreOffice/3/user/Scripts/`

에 들어있는 것들이다. 일단 매크로를 한번도 사용하지 않았다면 이 디렉토리에는 아무 것도 없다. 이 아래 python이라는 디렉토리를 만들고 그 안에 Python으로 작성한 스크립트를 넣는 방식으로 새로운 매크로를 등록할 수 있다.

```
$ cd ~/Library/Application\ Support/LibreOffice/3/user/Scripts/
$ mkdir python
```

다른 언어는 LibreOffice의 매크로 관리에서 새 매크로 작성과 편집 기능을 제공하므로 이렇게 하지 않아도 되고 해당 언어를 위한 디렉토리가 자동으로 만들어진다.

## Python Macro

### Hello World

파이썬으로 새로운 매크로를 작성하려면 LibreOffice 내에서는 안 되고 개별적으로 스크립트를 작성해서 해당 디렉토리에 넣어두어야 한다.

```
$ cd ~/Library/Application\ Support/LibreOffice/3/user/Scripts/python/
$ vi HelloWorld.py
```

로 새로운 파일을 열고 다음 내용을 그대로 입력해보자. 이것은 LibreOffice에 기본적으로 포함되어 있는 예제를 그대로 가져온 것이다.

```
def HelloWorldPython( ):
    model = XSCRIPTCONTEXT.getDocument()
    text = model.Text
    tRange = text.End
    tRange.String = "Hello World (in Python)"
    return None
```
	
스크립트 파일을 저장하고 LibreOffice의 "도구 > 매크로 > 매크로관리 > Pyhton" 창을 열고 "내 매크로"을 열어보면 방금 만든 HelloWorld가 나타나고 그 아래 HelloWorldPython가 있는 것을 확인할 수 있다. 선택하고 실행을 누르면 된다. 이 매크로는 텍스트 문서(Writer)에서 실행된다. 스프레트시트(Calc)나 슬라이드(Impress)에서는 실행되지 않는다.
