---
layout: post
title:  "Mac에서 NTFS, ext2, ext3 사용하기"
date:   2011-01-09 00:03:00
categories: [macosx]
tags: [macosx]
---

Mac에서 기본적으로 지원하는 파일 시스템는  HFS+ (Mac OS Extended), FAT, exFAT이다. 현재 최신 버전인 Mac OS X 10.6.5 Snow Leopard에서는 Windows의 NTFS나 리눅스의 ext2, ext3 등은 지원하지 않는다. 다음 둘을 설치하면 ext2/ext3 파일시스템을 사용할 수 있다.

- fuse-ext2   http://sourceforge.net/projects/fuse-ext2/
- macfuse    http://code.google.com/p/macfuse/

Snow Leopard에서  fuse-ext2 (버전 2.0.0.7)과 macfuse (버전 2.0.3.2)을 설치하였고 제대로 작동하였다. 설치 후 재부팅을 해야 한다. USB 외장하드를 연결하니 자동으로 마운트되어 바탕화면에 외장 하드가 떴다.

### MacPorts로 설치할 때 문제

MacPorts가 설치되어 있는 상태라 다음 명령으로 간단히 설치하려고 했었다.

```
$ sudo port install ext2fuse
```

설치가 완료된 후 재시동을 하였다.

그런데, 문제가 있다. USB 외장 하드에는 NTFS 파티션과 EXT3 파티션이 들어 있었다. 외장 하드를 연결하자 마자 NTFS 파티션은 자동으로 마운트가 되어 바탕화면에 디스크 아이콘이 나타났지만 EXT3 파티션들은 나타나지 않았다. diskutil로 확인해 보면  외장 하드의 파일 시스템이 다음처럼 제대로 나타났다.

```
$ diskutil list

/dev/disk2
   #:                       TYPE NAME                    SIZE       IDENTIFIER
   0:     FDisk_partition_scheme                        *160.0 GB   disk2
   1:               Windows_NTFS WinXP                   74.1 GB    disk2s1
   2:                 Linux_Swap                         2.0 GB     disk2s2
   3:                      Linux                         33.9 GB    disk2s3
   4:                      Linux                         50.0 GB    disk2s4
```

마운트하려고 다음처럼 해보았지만

```
$ sudo mkdir /Volumes/hd1
$ sudo mount -t fuse-ext2 /dev/disk2s3 /Volumes/hd1
```

다음 같은 에러 창만 나타났다.

```
FUSE-EXT2 could not mount /dev/disk2s3 at /Volumes/hd1 because the following problem occured:

dyld: Library not loaded: /usr/local/lib/libfuse.2.dylib 
Referenced from: /usr/local/bin/fuse-ext2
Reason: image not found 
```

한참 헤맸다. 문제는 두 가지이다.

하나는 port가 설치해 주는 것이 fuse-ext2가 아니라 ext2fuse이다.

- ext2fuse    http://sourceforge.net/projects/ext2fuse/

둘은 전혀 다른 프로젝트이고 뭐가 문제인지 모르겠지만 ext2fuse는 잘 작동하지 않았고 fuse-ext2는 잘 작동했다.

또 하나 문제는 port로 설치한 macfuse는 fuse-ext2와 함께 제대로 작동하지 않는다. macfuse를 프로젝트 홈페이지에서 다운로드받아서 설치하니 제대로 작동한다.
