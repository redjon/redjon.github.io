---
layout: post
title:  "Mac 키보드 사용자화"
date:   2011-11-08 15:56:00
categories: [macosx]
tags: [macosx]
---


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

