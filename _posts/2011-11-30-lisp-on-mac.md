---
layout: post
title:  "Mac에서 Lisp하기"
date:   2011-11-30 15:56:00
categories: [lisp]
tags: [lisp]
---

## Common Lisp

Common Lisp 구현에는 여러가지가 있다. 자유롭게 사용할 수 있는 것으로

- [SBCL](http://www.sbcl.org/) (Steel Bank Common Lisp, forked from [CMUCL](http://www.cons.org/cmucl/))
- [CLISP](http://www.clisp.org/)
- [CCL](http://ccl.clozure.com/) (Clozure CL, aka OpenMCL)

이 대표적이고 [ECL](http://ecls.sourceforge.net/) (Embeddable CL) 같은 것도 있다. 상용이면서 무료 버전을 제공하는 LispWorks, Allegro CL도 있다. LispForum의 단순한 설문조사에 의하면 SBCL 사용자가 절반 이상으로 가장 많고 CLISP 사용자가 20% 정도이며 Clozer CL과  LispWorks 사용자가 그 다음이라고 한다. 유닉스 계열 시스템에서라면 SBCL이 대세이다. <del>Windows에서는 SBCL이 지원이 안 되기 때문에 CLISP이 대안이 될 것이다.</del> 2013년 현재 Windows도 지원하지만 아직 완벽하지는 않다. Mac OS X에서는 Clozure CL이 가장 좋을 수 있다. CCL은 지금은 다른 운영체제도 지원하지만 원래 Macintosh Common Lisp의 오픈 소스 포크이고 실험적이지만 Mac OS X에서 IDE를 포함하고 있다. NIX계열과 Windows에서 32bit, 64bit 모두 지원하고 있다는 것이 강점이다.

- [Clozure CL 설치 및 설정](/articles/lisp/clozure-cl-getting-started)
- [SBCL 설치 및 설정](/articles/lisp/sbcl-getting-started)

CLISP은 brew로 간단히 설치할 수 있다.

```
$ brew install clisp
```

SBCL도 마찬가지이다.

```
$ brew install sbcl
```

## Scheme

MIT/GNU Scheme는 Linux, MacOSX, Windows를 위한 바이너리를 제공한다. MacOSX용 바이너리를 받으면 된다. 특별한 설치과정은 필요없다.

- http://www.gnu.org/software/mit-scheme/

Applications에서 MIT/GNU Scheme을 실행하면 Emacs 비슷한 창이 뜬다. Terminal.app에서

```
$ /Applications/MIT\:GNU\ Scheme.app/Contents/Resources/mit-scheme
```

로 실행할 수도 있다.

Emacs 관련
- http://alexott.net/en/writings/emacs-devenv/EmacsScheme.html
- http://www.emacswiki.org/cgi-bin/wiki/SchemeComplete
- http://www.neilvandyke.org/quack/


Emacs Lisp



Clojure
