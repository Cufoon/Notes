---
title: "Git默认配置文件所在位置(windows)"
date: 2019-07-10T11:03:21+08:00
draft: false
tags: ["Windows"]
---

假设Git安装在 D:\Dev\Git

那么配置文件所在位置为 D:\Dev\Git\mingw64\etc
目录中有一个 gitconfig
可以优化为
```javascript
[core]
    symlinks = false
    autocrlf = false
[color]
    diff = auto
    status = auto
    branch = auto
    interactive = true
[help]
    format = html
[http]
    sslCAinfo = /ssl/certs/ca-bundle.crt
[diff "astextplain"]
    textconv = astextplain
[rebase]
    autosquash = true
[filter "lfs"]
    clean = git-lfs clean -- %f
    smudge = git-lfs smudge -- %f
    process = git-lfs filter-process
    required = true
[credential]
    helper = manager
```
