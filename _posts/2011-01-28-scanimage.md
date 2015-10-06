---
layout: post
title:  "scanimage"
date:   2011-01-28 11:14:00
categories: [tools]
tags: [tools]
---

Debian에서

칼라로

```
$ scanimage -x 210mm -y 297mm --resolution=300 > myscan.ppm
$ ppmtojpeg myscan.ppm > myscan.jpg
```

라인아트로

```
$ scanimage --mode=Lineart -x 210mm --y 297mm --resolution=600 > 
```

