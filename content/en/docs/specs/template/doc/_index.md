---
title: "Doc template"
description: "Doc template specifications"
date: 2024-01-11T00:36:39+09:00
draft: false
weight: 4
---

Doc represents the structure of a document. It can be generated into HTML doc, Markdown or other formats.

## Title

Use '#' to set the following sequence as a title of level one. The following examples shows how to define titles for any levels:

```tlang
doc[HtmlDoc] myTemplate() {
    # Title level 1

    ## Title level 2

    ### Title level 3

    #(4) Title level 4

    #(5) Title level 5
}
```

## Plain text
```tlang
doc[HtmlDoc] myTemplate() {
    Plain text can ben added just this way.
    Compared to lang, data or cmd templates, there is no restriction to write anything.
}
```


## List

An unordered or a numbered list can be defined like this:

```tlang
doc[HtmlDoc] myTemplate() {
    [list "bullet"
    * An element
    * Another element
    * Even one more element
    ]

    [list "numbered"
    * First element
    * Second element
    * Third element
    ]
}
```


## Table

## Image

## Link

## Include

## Code block

## Span

## As is
