---
title: "Overview"
description: "Language specification overview"
date: 2020-01-28T00:36:39+09:00
draft: false
weight: 1
---

The TLang code is written in .tlang files. They are composed of different parts that are not mandatory. The first part is the context of the file, mainly the packages that are imported or exposed. More will be said latter.

Then in the sections of the file are described. There are three types: 
* model, it represents the objects and the structure of your program
* helper, it contains the logic. Everything that will be executed is written in this section
* template, it defines the templates that will be used to generate the final code

You don't need to use all of them in every file. It is actually a good practice to separate correctly the different sections, especially if your project grows fast.

This is an example of an tlang file:

```tlang
use myFile1

expose myFunc

model {

}

helper {

}

lang[java] myTemplate() {

}


```

At that point, this program does nothing, it won't even run but it shows the different parts.