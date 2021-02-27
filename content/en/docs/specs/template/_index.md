---
title: "Template"
description: "Template section"
date: 2020-01-11T14:09:21+09:00
draft: false
weight: 4
---

The template section is a bit special because it is not interpreted the same way as the other sections. As long as it is grammatically correct it's fine, even if it doesn't make any sense.
A template is simply taken and transformed into another language without interpreting or attempting to make any sense if the destination language. The generated code might not compile.

If you create your own template you need to know the destination language to make compilable and executable code. If you reuse someone else's template you don't have too if the template is well documented.

## Imports, uses, requires, ...

```tlang
tmpl[java] myTemplate() {
use java.util.Date 
}
```

## Variables

```tlang
tmpl[java] myTemplate() {
    var myVar:String = "The value"

    var[public static final] MY_CONST = "The constant value"
}
```

## Classes, traits, interfaces, ...

```tlang
tmpl[java] myTemplate() {
    impl[public interface] myInterface {
    }

    impl[public class] myClass for myInterface {
    }
}
```

## Functions and methods

```tlang
tmpl[java] myTemplate() {
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
