---
title: "Hello world !"
description: "Running the \"Hello world!\" programm with TLang"
date: 2020-01-28T00:34:41+09:00
draft: false
weight: 2
---

## Classic "Hello, World"

Main.tlang:
```tlang
use io.Terminal

helper {

    func main() {
        Terminal.println("Hello, World !")
    }
}
```

manifest.yaml
```yaml
name: HelloWorld
project: IntegrationTests
organisation: TLang
version: 1.0.0
stability: alpha
releaseNumber: 1
dependencies:
  - TLang/IO/Terminal 1.0.0:alpha:1 io
```

## Generate "Hello, World" in Scala

Main.tlang:
```tlang
use io.Terminal
use gen.Generator

helper {

    func main() {
        Terminal.println(Generator.generate(helloWorld()))
    }
}

tmpl[scala] helloWorld {
    pkg hello_world

    impl HelloWorld {
        func main(args: String[]) {
            println("Hello, World!")
        }
    }
}
```

manifest.yaml
```yaml
name: HelloWorldInScala
project: IntegrationTests
organisation: TLang
version: 1.0.0
stability: alpha
releaseNumber: 1
dependencies:
  - TLang/IO/Terminal 1.0.0:alpha:1 io
  - TLang/Generator/Generator 1.0.0:alpha:1 gen
```

To run this example, in your favourite terminal, go to the folder where you saved these files and then run:
```shell
tlang run .
```