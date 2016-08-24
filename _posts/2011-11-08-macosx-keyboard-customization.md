---
layout: post
title:  "Mac 키보드 사용자화"
date:   2011-11-08 15:56:00
categories: [macosx]
tags: [macosx]
---


MacOSX에서는 기본적으로 이맥스 키바인딩을 사용할 수 있게 되어있다. kdjfd



### Karabiner와 Seil

- Karabiner: https://pqrs.org/osx/karabiner/index.html.en
- Seil:   https://pqrs.org/osx/karabiner/seil.html.en


Emacs쓸 때 유용한 기능

- Shift+Space to Command+Space (except Emacs)
- Command+Space to Option+Space (only in Emacs)
- Swap Command+Tab and Control+Tab


Programmer Settings
- Shifts to Parentheses : 시프트 키만 단독으로 누를 때 괄호가 입력됨.
- Swap backtick and underscore





### 기본설정

- RealForce91UBK 키보드.
- MacOSX의 시스템환경설정에서 "키보드 > 키보드유형변경"에서 JIS일본 키보드로
  설정. 이것을 US로 설정하여 쓸 수도 있지만 그럴 경우 자판의 2개 키를 못 쓰게
  된다. (백스페이스 왼쪽의 일본 엔화 `BACKSLASH` 키와 오른쪽 시프틋  바로 왼쪽의 `JIS_UNDERSCORE` 키)

* Karabiner에서
  - "Use Japanese Keyboard as US Keyboard" 활성화.
  - JIS Yen to Backslash
  - 

  - 모든 기본키가 미국식 키보드에 있는 것과 동일하게 작동한다.
  -  E/J 키: 정상적으로 `BACKQUOTE`와 물결(~) 기호가 된다.
  - 엔화 키: 백슬래시와 파이프가 된다.
  - 3행 엔터키 왼쪽에 있는 키:  백슬래시와 파이프가 된다.
  - `JIS_UNDERSCORE` 키: `BACKQUOTE`와 물결(~) 기호가 된다.
  - 작동하지 않는 키: NFER, XFER, KANA


### 설정1

- Seil에서 "For Japanese"에 있는 키들을 활성화한다.
  - NFER -> Command_L (55)
  - XFER -> Command_R (54)
- KATAKANA -> Option_R (61)


| RF91UBK | Ctrl | Win | Alt | NFER | SPC | XFER | KANA | ALT | Menu | Ctrl |
|    설정 | Ctrl | Com | Opt | Com  | SPC | Com  | Opt  | Opt | Com  | Ctrl |


입력기 변환: Com+SPC



### 설정2

- Seil에서 "For Japanese"에 있는 키들을 활성화한다.

- NFER -> Control_L (59)
- XFER -> Control_R (62)
- KATAKANA -> Option_R (61)
- Command_L -> Shift_L (56)
- Option_R -> Shift_R (60)
- Control_L -> Command_L (55)

| RF91UBK | Ctrl  | Win | Alt | NFER | SPC | XFER | KANA | ALT | Menu | Ctrl |
|  Mac    | Shift | Cmd | Opt | Ctrl  | SPC | Ctrl  | Opt  | Shift | Cmd  | Ctrl |
|  Emacs  | S-    | C-  | M-  | C-  | SPC | C-  | M-  | S- | C-  | Ctrl |


### 설정3

- Seil에서 "For Japanese"에 있는 키들을 활성화한다.

- NFER -> Control_L (59)
- XFER -> Control_R (62)
- KATAKANA -> Option_R (61)
- Option_R -> Shift_R (60)
- Control_L -> Command_L (55)

| RF91UBK | Ctrl  | Win | Alt | NFER | SPC | XFER | KANA | ALT | Menu | Ctrl |
|  Mac    | Shift | Cmd | Opt | Ctrl  | SPC | Ctrl  | Opt  | Shift | Cmd  | Ctrl |
|  Emacs  | S-    | C-  | M-  | C-  | SPC | C-  | M-  | S- | C-  | Ctrl |




### Emacs Command Frequency

- http://ergoemacs.org/emacs/command-frequency.html


C-n	previous-line
C-p	next-line
M-f	forward-word
C-f	forward-char
M-b	backward-word
C-b	backward-char
C-d	delete-char
C-s	i-search
C-a	move-beginning-of-line
C-backsapce	backward-kill-word
C-y	yank
C-x C-s	save-buffer
C-k	kill-line
C-x o	other-window
C-e	move-end-of-line
C-x C-f	find-file
C-v	scroll-up
C-M-f	forward-sexp
M-x
C-x k	kill-buffer
C-SPC	set-mark-command
C-r	isearch-backward
C-/	undo
C-x 1	delete-other-window



### 옛날 자료

애플 키보드가 아니라 Realforce 91UBK 키보드를 사용하고 있다. 키감도 좋지만 무엇보다도 Emacs에서 Ctrl과 Meta의 단축키 조합 때문에 이것을 쓴다. 스페이스바가 아주 짧은 대신에 스페이스 바 양쪽에 아마도 일본어 입력과 관련된 듯한 이상한 모양의 키들이 배치되어 있다. CapsLock을 Control로 바꾸는 것에 대해서 이것을 Meta로 바꾸어 쓰면 정말 편리하기 때문이다.


KeyRemap4MacBook과 PCKeyboardHack을 쓰면 키보드를 상당히 많이 커스터마이징할 수 있다. 다운로드는 다음 사이트에 가면 할 수 있다. 둘 다 설치해야 한다.

- http://pqrs.org/macosx/keyremap4macbook/

설치하고 재부팅하고 나서 시스템 환경설정에 들어가보면  두 개 설정 메뉴가 생긴 것을 볼 수 있다. 우선 PCKeyboardHack을 실행시켜서 For Japanese 아래 다음 옵션들을 켜준다. 

- Enable NFER Key on PC Keyboard  : 스페이스 바로 왼쪽에 있는 키를 활성화
- Enable XFER Key on PC Keyboard :  스페이스 바로 오른쪽에 있는 키를 활성화
- Enable KATAKANA Key on PC Keyboard: 스페이스 오른쪽으로 한 칸 건너 KANA라고 써있는 키를 활성화

이제 KeyRemap4MacBook 메뉴로 들어가서 이 키들을 적절히 Remap한다.  그런데 여기서 좀 헤깔리는 것이 있다.  KeyRemap4MacBook에서 이 키들을 지칭하는 명칭이 혼동스럽다.

- EISUU Key: 스페이스 바로 왼쪽
- KANA Key:  스페이스 바로 오른쪽
- Command_R: 스페이스 오른쪽 한 칸 건너 KANA 라고 새겨진 키

그러니까 키보드에 KANA라고 새겨진 키는 따로  Remap할 필요없이 저절로 Command 키가 된다. 스페이스 바 양쪽에 있는 두 키만 Remap하면 된다. 

개인적으로 이맥스를 많이 쓰기 때문에 다음처럼 설정해서 쓴다.

- CapsLock을 Control_L로 Remap
- 스페이스바 바로 왼쪽에 있는 EISUU 키는 Command_L로  Remap

그리고 나서 Alt 대신 Command를 Emacs의 Meta가 되도록 설정한다. 설정 방법은

- http://redjon.github.io/articles/emacs/aquamacs/

스페이스 오른쪽에 있는 키들은 거의 사용하지 않아서 깊이 생각해 보지 않았다. 그냥 전부 Command_R로 매핑해서 쓴다. 

