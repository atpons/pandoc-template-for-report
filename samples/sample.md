---
documentclass: ltjsarticle
title: 良い感じレポート
author:
  - id: 17000001
    name: 山田太郎
lecture:
  - teacher: 山田花子
  - date: 2017年10月10日
  - deadline: 2018年12月10日
---
# 概要
これは文章です．

プログラムは[@lst:helloworld]のように引用できます．

表は[@tbl:sample]のように書けます．

![図も挿入できます．[^fig]](sample.png){#fig:sample height=20mm}

[^fig]: 脚注です．

|a|b|
|-|-|
|1|2|
|3|4|

:表のサンプル {#tbl:sample}


$1 + 1 = 2$

# 付録
## プログラム1
``` {label=lst:helloworld .numberLines caption="Hello World" style=customc .listings}
#include <stdio.h>
int main(){
  printf("Hello, World!");
  return 0;
}
```
