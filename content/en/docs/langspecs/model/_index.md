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
        attr1 String,
        attr2 AThirdEntity[],
        attr3 (String, Int[]): (String),
        attr4 impl{
            attr41 String
        } 
        attr5 &attr4.attr41
        attr6 (param61 Bool) {
            attr61 String
        },
        attr7 impl[]
    }
}

```
MyEntity defines three parameters and seven attributes. Those three parameters makes MyEntity a model within a model. MyEntity is a model because it can be and will be implemented by a variable. The variables will be required to implement the seven attributes. However, the parameters will be implemented by the attributes of type "impl" defined by the attributes attr4 and attr7. In the next section, we are going to implement this model which should make it easier to understand.

With one entity, it is possible to represent the whole structure of a program that would require many interfaces and classes in other languages.

### The parameters

* param1 is of type String which is a simple chain of characters
* param2 is of type Int[] which is an array of integers
* param3 is of type AnotherEntity which is another entity such as MyEntity (not defined in this example)

## Variables

It is actually a bit misleading to call them variables as they cannot change. They are immutable variables. You can write them once, read them and change their value only when you affect them to another variable.

The power of immutable variables is that they prevent many side effects. If you cannot change the value, you cannot alter the behaviour of another part of your program. 

### Primitives

```tlang
model {
    let myString = "String value"
    
    let myInt = 10

    let myBool = true

    let myDouble = 1337.42
}
```

### Arrays

```tlang
model {
    let myStrings String[] = ["String1", "String2", "String3"]

    let myInts Int[] = [1, 2, 3, 4, 5]

    let myMap String[] = ["key1" "Value1", "key2" "Value2", "key3" "Value3"]
}
```

### Entities
```tlang
model {
    let myFirstEntity MyEntity("Param1", [1, 2], param3 AnotherEntity {}) {
        var1 "Var1",
        var2 [AThirdEntity{}, AThirdEntity{}, AThirdEntity{}],
        var3 myFuncDefinedInHelper(#, [42,1337]),
        var4 impl("Param1", [3,4], param3 AnotherEntity {}){
            var1 "Var1"
        } 
        var6 (true) {
            "Var1"
        },
        var7 [
            ("Param1", [1, 2], param3 AnotherEntity {}),
            ("Param1", [5, 6], param3 AnotherEntity {})
        ]
    }
}

```
