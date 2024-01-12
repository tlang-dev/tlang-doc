---
title: "Generators"
description: "Overview of the available generators"
date: 2024-01-11T00:34:39+09:00
draft: false
weight: 3
---

## How to use

### Dependency in manifest

First you need to declare them in your manifest.
For instance, if you would like to use the Kotlin generator, declare it as follow in the "dependencies" section:

```yaml
name: HelloWorld
project: MyFirstProject
organisation: MyOrg
version: 1.0.0
stability: alpha
releaseNumber: 1
dependencies:
  - TLang/Generator/Kotlin 1.0.0:alpha:1 kotlin
```

### Use in template

In a tlang file, you need to import it with the "use" keyworkd and define a lang template as Kotlin code in the braquets after the "tmpl" keyword.

```tlang
use kotlin.Kotlin

tmpl[kotlin] myTemplate() lang {
    var myVar:String = "The value"

    impl MyClass {
        func myFunc(param1: String[], param2: String):Int {
	        return 42
        }
    }
}
```

## Generators

This is a list of known generators. If you have created your own you can ask us to add it here.

### Lang

* Kotlin https://github.com/tlang-dev/kotlin-generator
* Java https://github.com/tlang-dev/java-generator
* TypeScript https://github.com/tlang-dev/typescript-generator
* Dart https://github.com/tlang-dev/dart-generator
* Javascript, not yet implemented
* Python, not yet implemented
* Rust, not yet implemented
* C#, not yet implemented
* C, not yet implemented
* C++, not yet implemented

More languages will come

### Data

* JSON https://github.com/tlang-dev/json-generator
* YAML https://github.com/tlang-dev/yaml-generator
* XML https://github.com/tlang-dev/xml-generator
* HTML https://github.com/tlang-dev/htmldata-generator

More data format will come

### Doc

* HTML https://github.com/tlang-dev/htmldoc-generator
* Markdown https://github.com/tlang-dev/markdown-generator

More doc format will come

### Cmd

* Bash https://github.com/tlang-dev/bash-generator
* SQL https://github.com/tlang-dev/sql-generator
* PowerShell, not yet implemented

More command languages will come

### Style

* CSS https://github.com/tlang-dev/css-generator

More style will come