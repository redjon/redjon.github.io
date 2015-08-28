---
layout: post
title:  "MacOSX Time Machine"
date:   2015-02-03 10:06:00
categories: [macosx]
tags: [macosx]
---
### 타임머신에 문제가 생겼을 때

- http://pondini.org/TM/Troubleshooting.html

### 백업 크기가 너무 클때

이상하게 매번 10~20G가 백업이 된다. 백업 디스크가 순식간에 차버린다. 가상 머신 디스크 이미지 같은 것이 있어서 그런 일이 일어날 수 있다.
하지만 타임머신 오류일 수도 있다. 

타임머신 멈추고 백업용 외장 디스크 제거하고 다음 설정 파일을 삭제한다.

```
$ sudo rm /Library/Preferences/com.apple.TimeMachine.plist
```

재부팅하고 백업용 외장 디스크 연결하고 타임머신 실행하면 모든 설정이 사라져있다. 다시 설정한다.

### 백업에서 제외할 폴더

물론 ~/Downloads 같은 것은 제외하는 것이 좋다. 

Mail.app를 사용한다면 다음 폴더를 확인해보자. 수십 기가 로그 파일이 들어있을 수도 있다. 백업 제외 목록에 넣어주자. Mail.app을 종료한 후에 로그 파일을 잠시 다른 곳에 옮겨놓고 Mail.app을 다시 실행해 보자. 로그 파일을 지워도 큰 문제는 없다.

```
$ cd ~/Library/Containers/com.apple.mail/Data/Library/Logs/
$ du -sh
```
