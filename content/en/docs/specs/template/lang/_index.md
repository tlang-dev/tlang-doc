---
title: "Lang template"
description: "Lang template specifications"
date: 2024-01-11T00:36:39+09:00
draft: false
weight: 2
---



## Imports, uses, requires, ...

```tlang
lang [java] myTemplate() {
use java.util.Date 
}
```

## Variables

```tlang
lang [java] myTemplate() {
    var myVar:String = "The value"

    var[public static final] MY_CONST = "The constant value"
}
```

## Classes, traits, interfaces, ...

```tlang
lang [java] myTemplate() {
    impl[public interface] myInterface {
    }

    impl[public class] myClass for myInterface {
    }
}
```

## Functions and methods

```tlang
lang [java] myTemplate() {
    impl[public interface] myInterface {
        func myFunc(param1: String, param2: Int)
    }

    impl[public class] myClass {
        func myFunc(param1: String[], param2: String):Int {
	    return 42
        }
    }
}
```

## Conditions

## Loops
