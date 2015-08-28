---
layout: post
title:  "Github 유용한 팁 모음"
date:   2013-06-06 15:44:00
categories: [git]
tags: [git, github]
---

### commit 지우기

github에 commit을 막 push하고 보니 실수했다. 이때는 우선 로컬에서 해당 commit을 지우고 정리한 후에 다음 명령을 내린다.

```
$ git push origin +master
```

### 쓰기 권한 문제

`.git/config` 파일에 다음과 같이 설정되어 있어야 한다.

```
url = git@github.com:username/repo.git
```

참고
- http://stackoverflow.com/questions/13509293/git-fatal-could-not-read-from-remote-repository
