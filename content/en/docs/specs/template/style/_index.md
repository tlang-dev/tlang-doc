---
title: "Style template"
description: "Style template specifications"
date: 2024-01-11T00:36:39+09:00
draft: false
weight: 5
---

A style template can be used to generate CSS, TLang formatters, or Charts with Dot Language.

## Style structure

```tlang
style [css] myTemplate() {

    p {
        font-family: verdana;
        font-size: 20px;
    }

}
```

## Include

```tlang
style [css] myTemplate() {

    p {
        font-family: verdana;
        font-size: 20px;
    }

    <[anotherTemplate()]>

}
```

## Data types
