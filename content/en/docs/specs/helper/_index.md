---
title: "Helper"
description: "Helper section"
date: 2020-01-11T14:09:21+09:00
draft: false
weight: 3
---

The helper is the logic part, this is where everything is executed. It contains only functions that are static and therefore, there are no global variables inside an helper. However, a function can have access to variables inside a model segment because they are static and immutable as well.

## Functions

```tlang
helper {
    func myFunc(param1 String, Int, param3 AnEntity[], (Int, String):(Bool)) {
        
    }
}
```

The function "myFunc" takes four parameters:
1) param1 of type String
2) anonymous parameter of type Int
3) param3, an array of entities "AnEntity"
4) anonymous parameter which is a function with two parameters (Int and String) and returns a Bool

You can use an anonymous parameter with underscore and the parameter position. Example : _2 for the second parameter and _4 for the fourth parameter.
Then, you can call the function this way: _4(1337, "Foo bar !")

### Currying

```tlang
helper {
    func myFunc(param1 String, param2 Int)(param3 Bool, param4 Double) {
        
    }
}
```

Currying let you define multiple sets of parameters which are very helpful to simplify the call of a function. The main scenario is to use a dedicated set of parameters for the references when setting an entity. This way, only one set of parameters would be needed when calling the function. This is the how dependencies can be injected. This is an advanced topic and it will be covered later on in more details.

Inside the function, you will use the parameters as if there was just one set of parameters which means than they all require a unique name.

## Variables

```tlang
helper {
    func myFunc() {
        let myString = "String value"
    
        let myInt = 10

        let myBool = true

        let myDouble = 1337.42
    }
}
```

## Conditions

```tlang
helper {
    func myFunc() {
        if(((myVar == myVar2 && myVar3) || myVar4) && myVar5) {

        } else {

        }
    }
}
```

## Loops

```tlang
helper {
    func myFunc() {
        for(i 0 to 10) {
        
        }

        for(i 0 until 10) {
        
        }

        let myArray = ["One", "Two", "Three"]
        for(count in myArray) {
        
        }
    }
}
```