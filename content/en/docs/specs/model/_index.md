---
title: "Model"
description: "Model section"
date: 2020-01-11T14:09:21+09:00
draft: false
weight: 2
---

The model is where your will define your types and most of your variables. Those variables may also describe the architecture of your program.
There are five types of variables:

* the primitives such as string, long or bool
* the arrays
* the entities that can contain other variables of all types.
* the function declarations that define the parameters and the return types
* the references that are short cuts to the other types

## Entities
An entity is both a type and a variable (or an implementation). When it's a type, it defines what can be set inside. It could be seen as an interface or a trait in other languages. The type of an entity is called the model.

### Model

First let's define a simple model called MyModel:
```tlang
model {
    set MyModel {
        attr1: String,
        attr2: Long,
        attr3: AnEntity,
        attr4: Double[]
    }
}

```
MyModel defines four attributes, it is a model because it can be and will be implemented by variables (entities). The entity will be required to implement the four attributes.

#### The attributes
This model has four attributes:

* attr1 is of type String which is a simple chain of characters
* attr2 is of type Long which is an integer
* attr3 is of type AnEntity which has to be a model declared somewhere else
* attr4 is an array of Doubles which are real numbers, so an array of real numbers.

#### Entity using "MyModel"
Let's see how an entity using our model MyModel could look like:
```tlang
model {
    let myEntity: MyModel = {
        attr1="Oh! It's so good, it's so good, it's so good, it's so good, it's so good!",
        attr2= 1977,
        attr3= {
            subAttr1 = "We pretend this entity requires a string attribute"
        },
        attr4= [3.1415, 42.0, 0.2357111317192329313741]
    }
}

```

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

    let myLongs Long[] = [1, 2, 3, 4, 5]

    let myMap String[] = ["key1" "Value1", "key2" "Value2", "key3" "Value3"]
}
```

### Entities
```tlang
model {
    let myFirstEntity: MyModel = {
        var1 "Var1",
    }
}

```

## Implementations

An implementation is a special features that help design the structure of a program. It is possible to get multiple implementations inside an entity of the same model.
The power is that you can easily choose the implementation you want to use to operate different behaviours.
```tlang
model {
    set MyModel(attr1: String, attr2: Long){
        attrX: impl,
        attrY: impl[]
    }
}
```

This an example of an entity using the model MyModel and implementing it:
```tlang
model {
    let myEntity: MyModel = {
        attrX = impl {
            attr1 = "I wear my sunglasses at night",
            attr2 = 1984
        }
        attrY = [
            impl {
                attr1 = "If there's somethin' strange in your neighborhood, who ya gonna call?",
                attr2 = 1984
            },
            impl {
                attr1 = "I always feel like somebody's watching me",
                attr2 = 1984
            }
        ]
    }
}
```

## Extensions

Extensions expand the capabilities of a model with another offering the leverage to separate a program in smaller and cleaner units.

```tlang
model {
    set MyTopModel{
        attr1: String,
        attr2: Long
    }

    
    set MyModel ext MyTopModel{
        attr3: String,
        attr4: Long
    }
}
```

An example of an entity using MyModel:
```tlang
model {
    let myEntity: MyModel = {
        attr1 = "Attr1 value",
        attr2 = 1337,
        attr3 = "Attr3 value",
        attr4 = 42
    }
}
```

## References

A reference can point to a variable or a function and can use the value or the result of that function as a parameter to another function or expose them.

```tlang
model {

    let aVariable = "The value of my variable"

    set MyModel {
        attr3: &aVariable
    }
}
```


