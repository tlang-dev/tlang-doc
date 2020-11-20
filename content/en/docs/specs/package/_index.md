---
title: "Package"
description: "Package section"
date: 2020-01-11T14:09:21+09:00
draft: false
weight: 5
---

A package is represented by a folder in the file system. It has access to only one level, meaning the folder inside the current folder. Of course you get access to all files in the same folder.

## One level
```
    MyCurrentFolder
    |- File1.tlang
    |- File2.tlang
    |- FirstFolderInside
    |  |- File11.tlang
    |  |- File12.tlang
    |- SecondFolderInside
       |- File21.tlang
       |- File22.tlang
```
Based on the above hierarchy, assuming that your are working in File1.tlang and want to access functions in File2.tlang, File11.tlang, File21.tlang you can do the following:
* to access functions in File2.tlang you don't need to import or expose anything, File2.func1() will work
* to access functions in File11.tlang you need to expose first the functions in

## Two levels and more
```
    MyCurrentFolder
    |- File1.tlang
    |- File2.tlang
    |- FirstFolderInside
       |- File11.tlang
       |- File12.tlang
       |- SubSubFolder
          |- File111.tlang
          |- File112.tlang
```

## Other folders inside same parent
```
    MyCurrentFolder
    |- File1.tlang
    |- File2.tlang
    AnotherFolder
    |- File3.tlang
    |- File4.tlang
```