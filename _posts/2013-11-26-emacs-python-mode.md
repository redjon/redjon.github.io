---
layout: post
title:  "Python 프로그래밍을 위한 Emacs 설정"
date:   2011-11-26 19:32:00
categories: [emacs]
tags: [emacs, python]
---

Emacs에서 Python 프로그래밍을 하기 위해서는 python-mode가 가장 널리 이용되는 듯하다. Emacs 24 부터는 package 관리에서 python-mode를 설치할 수 있다.

직접 최신 버전을 다운로드 받아 설치하는 것이 좋을 수 있다. python-mode의 개발 저장소는 launchpad에 있고 bzr로 다운받을 수 있다. 홈페이지는

- https://launchpad.net/python-mode

여기에 가면 "latest version"이라고 하여 압축파일을 다운받을 수 있는데 이것을 받아서 써보려고 했더니 바로 에러가 난다. 저장소를 내려받는 것이 가장 좋다. 최근에 거의 매일 같이 python-mode.el 파일이 업데이트되고 있다. (2013-11-26)

bzr를 설치하는 것이 좋다. brew가 있다면 brew install bzr로 간단히 설치할 수 있다. 적당한 디렉토리, 예를 들어 ~/.emacs.d/ 아래에 다운받으면 된다.

```
$ cd ~/.emacs.d
$ bzr branch lp:python-mode
```

그리고 Emacs 설정 파일(보통 ~/.emacs)에 다음과 같은 내용들을 추가해준다. 마지막 두 줄은 코드 실행할 때 강제로 python3.3을 쓰게 하기 위한 것이다. 물론 필수는 아니다.

```lisp
(add-to-list 'load-path "~/.emacs.d/python-mode/") 
(setq py-install-directory "~/.emacs.d/python-mode/")
(when (featurep 'python) (unload-feature 'python t))
(require 'python-mode)
(setq py-shell-name "python3.3")
(setq py-force-py-shell-name-p t)
```

