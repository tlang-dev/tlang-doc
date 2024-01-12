---
title: "Template introduction"
description: "Introduction to the template concept"
date: 2024-01-1T00:36:39+09:00
draft: false
weight: 1
---

The template section is a bit special because it is not interpreted the same way as the other sections. As long as it is grammatically correct it's fine, even if it doesn't make any sense.
A template is simply taken and transformed into another language without interpreting or attempting to make any sense if the destination language. The generated code might not compile.

If you create your own template you need to know the destination language to make compilable and executable code. If you reuse someone else's template you don't have too if the template is well documented.

There are four types of templates :
* Lang, for programming languages such as Java, Python, Kotlin, Rust, Go, Typescript, ... 
* Data, for data structure understandable by human and machine such as JSON, HTML, XML, YAML, ...
* Doc, for document such as HTML, Markdown, ...
* Cmd, for command instructions such as Bash, SQL, Batch, PowerShell, ...
* Style, for styling documents such as CSS. It is uesd as well to format generated code with TLang.
