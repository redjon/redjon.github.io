---
layout: post
title:  "Mac에 Clozure CL 설치 및 설정"
date:   2011-12-04 14:34:00
categories: [lisp]
tags: [lisp]
---

## Clozure CL 설치


CCL은 다운로드 페이지에서 dmg로도 배포된다. 다운로드 받아서 열어보면 "Clozure CL32.app"와 "Clozure CL64.app"이 들어있고 다른 여러 폴더들이 들어있다. 일단 이것 전체를 $HOME/src/ccl 아래 두었다고 하자. Emacs에서 slime을 쓸 생각이기 때문에 맥용 app은 일단 쓸일이 별로 없을 것 같다. 셸에서 실행되도록 해야하는데 스크립트를 PATH에 넣어주고

```
$ cp ~/ccl/scripts/ccl64 ~/bin/
$ chmod +x ~/bin/ccl64
```

그리고 ~/bin/ccl64를 열어 다음과 같이 바꾸어 준다.

```
if [ -z "$CCL_DEFAULT_DIRECTORY" ]; then
  CCL_DEFAULT_DIRECTORY=$HOME/src/ccl
fi
```

를 추가해 주자. 그럼 이제 셸에서 ccl64로 실행할 수 있다. 처음 실행하고 물음표(?)가 뜨면 디렉토리를 제대로 찾을 수 있는지 다음처럼 테스트해 보자.

```
$ ccl64
Welcome to Clozure Common Lisp Version 1.7-r14925M  (DarwinX8664)!
? (probe-file "ccl:level-1;level-1.lisp")
#P"/Users/rj/my_lisp_stuff/ccl/level-1/level-1.lisp"
```

## Slime

Slime은 Superior Lisp Interaction Mode for Emacs이다. Slime을 설치하려면:

- [Slime 설치](/articles/lisp/slime)

Clozure CL과 Slime을 쓰며 유니코드를 사용한다면 다음과 같은 설정이 필요하다. Slime이 설치된 경로와 ccl 스크립트의 경로를 알려주어야 한다. Slime 다운로드 받은 것이 ~/.emacs.d 아래 있다고 하면 다음처럼 될 것이다.

```lisp
(set-language-environment "utf-8")

(add-to-list 'load-path "~/.emacs.d/slime/") ;; path to slime
(setq inferior-lisp-program "~/bin/ccl64") ;; path to ccl script

(require 'slime)
(setq slime-net-coding-system 'utf-8-unix)
(slime-setup '(slime-fancy))
```

(참조: http://trac.clozure.com/ccl/wiki/InstallingSlime)

한글도 당연히 잘 된다.

```
CL-USER> "한글"
"한글"
CL-USER> (length "한글")
2
CL-USER> (format t "~X" (char-code #\가))
AC00
CL-USER> (defun 영어로-말해봐 () (print "Hello"))
영어로-말해봐
CL-USER> (영어로-말해봐)

"Hello" 
"Hello"
```

관련 링크:
- http://yellowbirds.kr/18

