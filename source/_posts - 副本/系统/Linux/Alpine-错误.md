---
title: Alpine-错误
categories:
  - 系统
  - Linux
tags:
  - alpine
date: 2023-07-04 11:31:41
---





错误：


```
$ su
su: must be suid to work properly
```

解决：

```
$ docker exec -it --user root mycontainername bash or sh
```

[How to run bash as user root on alpine images with docker? su: must be suid to work properly - Stack Overflow](https://stackoverflow.com/questions/61683448/how-to-run-bash-as-user-root-on-alpine-images-with-docker-su-must-be-suid-to-w)



