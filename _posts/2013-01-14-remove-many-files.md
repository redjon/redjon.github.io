---
layout: post
title:  "파일 한꺼번에 많이 지우는 방법"
date:   2013-01-14 17:31:00
categories: [bash]
tags: [bash]
---

웬만큼 되는 파일과 디렉토리를 한꺼번에 지울 때는 `rm -rf *`를 하면 된다. 시스템에 따라 차이가 있는지 모르겠지만 파일이 10만개 정도되면 에러가 난다. 에러 메시지라고 명확하게 보여주면 다행이다. LG NAS에 있는 파일을 정리하려고 명령을 내려보았는데 하드디스크 도는 소리는 나는데 아무 것도 지워지지 않는다. 자체적으로 지원하는 AjaXplorer인지 뭔지에서 지우는 명령을 내려보았는데 열심히 돌다가 (아마도 지울 파일 목록 만드는 중인 모양이다) 그냥 조용히 끝나버린다. 물론, 파일은 하나도 지우지 않고.

가장 쉬운 방법은 `find` 명령에 `-delete` 옵션을 쓰는 것인 듯하다. `-print` 옵션을 같이 주면 지워지는 파일 또는 디렉토리 이름도 화면에 출력된다.

```
$ find . -print -delete
```

현재 디렉토리 아래 모든 것을 다 지울 때는 아무래도 위 명령이 제일 편할 듯 하다. 파일만 지우고 싶다면 `-type f` 옵션을 추가할 수도 있다.

```
$ find . -type f -print -delete
```

아마도 더 표준적인 방법은 `xargs`를 이용하는 것일 것이다. 속도 차이가 있는지는 모르겠다. 가장 간단하게는 다음처럼 할 수 있다. 물론 이런 방식으로는 파일과 디렉토리를 함께 지울 수는 없다.

```
$ find . -type f | xargs rm
```
요즘에는 파일이름이 길고 공백도 포함한 경우가 많다. 위 명령은 파일명에 공백문자가 들어있을 경우에 문제가 되는데 이 때에는 다음처럼 널문자를 구분자로 사용하는 옵션을 주면 문제가 생기지 않는다.

```
$ find . -type f -print0 | xargs -0 rm
```

참조

- [How to delete million of files on busy Linux servers (Work out Argument list too long)](http://pc-freak.net/blog/how-to-delete-million-of-files-on-busy-linux-servers-work-out-argument-list-too-long/)
- [xargs: Problems with Spaces and Newlines](http://linuxdevcenter.com/pub/a/linux/lpt/09_22.html)
