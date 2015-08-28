---
layout: post
title:  "MacOSX에서 git 사용하기"
date:   2011-03-17 08:09:00
categories: [git]
tags: [git]
---

git는 MacPorts로 설치할 수도 있고 git 홈페이지에서 직접 다운로드 받아 설치할 수도 있다. git 홈페이지에서 다운로드 받는 게 나은 것 같다. 여러가지로 MacPorts에는 실망스러운 점이 많아서 따로 제공되는 것이라면 그것을 받아서 설치하는 게 좋다는 게 경험에서 얻은 결론이다.

### push/pull 에러

Mac OS X Server (Snow Leopard Server)의 /github 아래 저장소들을 보관하고 있다. 원격에서 ssh로 pull하거나 push할 수 있다. 데비안에서 (아무 것이라도 마찬가지겠지만) 한 저장소를 push하려고 하니 에러가 났다:

```
$ git push you@macosx_server:/github/your_repo
Password:
bash: git-receive-pack: command not found
fatal: The remote end hung up unexpectedly
```

이런 에러가 났을 때 문제는 클라이언트에 있지 않다. 문제는 원격 서버의 계정 설정에 있다. 위의 경우에 macosx_server의 계정 you의 $PATH에 git-receive-pack이 없기 때문에 나는 에러이다. macosx 서버에서 다음처럼 소프트 링크를 만들어주면 해결된다.

```
$ ln -s /opt/local/bin/git-receive-pack /usr/bin/git-receive-pack
```

물론 `$PATH`에 필요한 경로를 추가할 수도 있고 ~/bin/ 아래 소프트 링크를 만들어도 되고 어쨌든 자신의 계정의 PATH 환경변수에 git-receive-pack만 있으면 된다. 

마찬가지로 git pull를 실행할 때도 데 에러가 날 수 있다.

```
$ git pull 
Password: 
bash: git-upload-pack: command not found 
fatal: The remote end hung up unexpectedly
```

별 문제는 아니었다. 다음처럼 링크 만들면 해결된다.

```
$ sudo ln -s /opt/local/bin/git-upload-pack /usr/bin/git-upload-pack 
```

최근에 위치가 바뀌었나 보다 (2011-11-22)

```
$ sudo ln -s /usr/local/git/bin/git-upload-pack /usr/bin/git-upload-pack 
```

일단 급해서 이렇게 해결하고 말았는데, 왜 에러가 나는지 이유를 모르겠다. PATH도 잘 걸려있는데 git-upload-pack를 찾지 못하는 이유는?

참조
- http://stackoverflow.com/questions/225291/git-upload-pack-command-not-found-how-to-fix-this-correctly
