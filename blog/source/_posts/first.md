---
title: Install hexo and Apply theme
date: 2020-07-15 13:55:37
tags:
---
Record the install process of hexo in windows 10 x64

## Download [nodejs](https://nodejs.org/en/)

## Download [git](https://git-scm.com/download/win)

## Download [hexo](https://hexo.io/)

``` bash
$ npm install -g hexo-cli
```

``` bash
$ init hexo blog
```

## Download [Next](https://github.com/theme-next/hexo-theme-next)

``` bash
$ cd blog
```

``` bash
$ git clone https://github.com/theme-next/hexo-theme-next themes/next
```

open blog/_config.yml and apply next

theme: next 

``` bash
$ hexo server
```

open brower http://localhost:4000/







