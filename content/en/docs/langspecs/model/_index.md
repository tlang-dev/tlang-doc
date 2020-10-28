---
title: "Model"
description: "Model section"
date: 2020-01-11T14:09:21+09:00
draft: false
weight: 2
---

The model is where your will define your types and most of your variables. Those variables may also describe the architecture of your program.
There are five types of variables:
* the primitives such as string, int or bool
* the arrays
* the entities that can contain other variables of all types.
* the function declarations that define the parameters and the return types
* the references that are short cuts to the other types

## Entities
An entity is both a type and a variable (or an implementation). When it's a type, it defines what can be set inside. It could be seen as an interface or a trait in other languages.

First we define or set a new type:
```tlang
model {
    set MyEntity(param1 String, param2 Int[], param3 AnotherEntity) {
        var1 String,
        var2 AThirdEntity[],
        var3 (String, Int[]) -> (String),
        var4 impl{
            var1 String
        } 
        var5 &var4.var1
        var6 (param1 Bool) {
            var1 String
        },
        var7 impl[]
    }
}

```

## Variables