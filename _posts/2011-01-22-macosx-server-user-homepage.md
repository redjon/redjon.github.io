---
layout: post
title:  "Mac OS X Server에서 계정별 홈페이지 활성화"
date:   2011-01-22 12:36:00
categories: [macosx]
tags: [macosx]
---
Mac OS X 10.6.6 Snow Leopard Server에서 계정 홈페이지가 열리지 않았다. 애플의 문서 Web Technologies Administration에 보면 기본 웹사이트의 폴더는

```
/Library/WebServer/Documents
```

로 설정되어 있고 등록된 사용자 계정이 rj라면

```
/User/rj/Sites
```

폴더가 http://localhost/~rj  로 서비스된다고 설명되어 있다. 설정에 관해서는 아무런 말이 없다. 기본적으로 그렇게 된다는 소리다. 그런데 막상 http://localhost/~rj 를 열어보면 에러만 난다.

```
Object not found!
The requested URL was not found on this server. If you entered the URL manually please check your spelling and try again.
If you think this is a server error, please contact the webmaster.
Error 404

localhost
Sat Jan 22 12:32:07 2011
Apache/2.2.15 (Unix) DAV/2
```

뭔가 해서 한참 뒤졌는데 너무 단순한 문제였다. userdir_module이 활성화되지 않은 것이다. Server Admin 을 실행하고 서버를 선택한 후 Web > Settings > Modules로 들어가서 userdir_module를 체크해 주고 서버를 재시작하면 된다.

