---
title: "Installation"
description: "Installing TLang"
date: 2020-01-28T00:34:13+09:00
draft: false
weight: 1
---

Make sure that you have java version 11 or above installed.

Download the latest version of TLang https://github.com/tlang-dev/tlang/releases

Then run the jar:
```shell
java -jar tlang.jar version
```

## Set env

We advise you to set an environment variable to run the jar. in the next chapters we will use the command tlang instead of java -jar tlang.jar

### Unix
On unix systems add a path to your PATH variable in your shell config file.

### Windows
For Windows you need to create a batch file (for instance: C:\Users\YOUR_NAME\tools\tlang\tlang.bat):
```batch
java -jar C:\Users\YOUR_NAME\tools\tlang\tlang.jar %*
```

Then add the folder to your Path in your environment variables (C:\Users\YOUR_NAME\tools\tlang).