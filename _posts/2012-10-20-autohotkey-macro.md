---
layout: post
title:  "AutoHotKey: Windows용 자동화. 스크립팅, 매크로 기능"
date:   2012-10-20 20:00:00
categories: [mswin]
tags: [mswin]
---

Windows에서 반복적인 작업을 자동화하는 기능이 필요할 때가 있다. 단순하게는 정해진 순서대로 키보드를 누르는 일을 사람 대신 반복하는 키 매크로 같은 것이 필요할 때가 있다. 이런 일을 해주는 [AutoHotKey](http://www.autohotkey.com/) 강력하다. 단순한 키 매크로는 훨씬 뛰어넘는다. 스크립트 파일의 형태 작성하여 실행시킬 수 있으며 키보드, 마우스 제어 뿐만 아니라 Windows의 상당한 부분을 제어할 수 있다. 프로그램을 실행시킬 수도 있고  파일이나 폴더를 조작할 수도 있고 Message Box를 띄울 수도 있다. 특정한 제목을 가진 윈도를 활성화시키는 일도 할 수 있다. 화면에 여러 개의 윈도가 떠 있을 때 이들 사이를 돌아다니면서 무언가 반복적인 일을 하는 매크로도 만들 수 있다.

그리고 오픈소스이다.  라이선스는 GNU GPL2.


AutoHotKey를 다운로드 받아 설치하고 난 후에 스크립트를 만들면 된다. 스크립트를 보관한 폴더를 적절히 선택하고  마우스 오른쪽 버튼을 눌러서 "New > AutoHotKey Script"를 선택하여 새로운 .ahk 파일을 만든다. 텍스트 편집기에서 열어서 스크립트를 짜면 된다. 스크립트 파일을 더블 클릭하면 실행된다. 스크립트가 돌아가는 동안에는 오른쪽 아래 작업줄에 H자가 써있는 작은 아이콘이 나타난다.

반복은 다음처럼 할 수 있다.
Loop 100
{
% 여기에 반복할 내용
}

키보드 입력은 Send를 통해 보낼 수 있고 Ctrl(^), Alt(!), Shift(+), WIN(#) 등의 modifier를 쓸 수 있다. 문자 키가 아닌 경우에는 {Enter}, {Tab}, {Down}, {Up}, {Left}, {Right} 등으로 보낼 수 있다. 예를 들어, 다음처럼 Ctrl+a, Ctrl+c 키를 연달아 누른 효과를 낼 수 있다.

Send ^{a}
Send ^{c}

Loop와 Send만 이용해도 단순 반복적인 키 입력을 자동화할 수 있게 된다.


참조

http://www.techsupportalert.com/best-free-hotkey-macro-recorder-utility.htm
http://www.autohotkey.com/
http://cafe.naver.com/AutoHotKey
