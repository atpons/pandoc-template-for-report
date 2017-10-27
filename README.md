Pandoc Template for Report
===

このテンプレートを使えばPandocを使って大学に提出するための講義用レポートを手軽に作成することができます．

## 概要
レポートをMarkdownで書いた後にPandocを使ってLaTeX形式もしくはPDF形式に出力することができます．
このテンプレートを使うことで，大学の講義用レポート向けに以下の設定が可能です．
- タイトル
- 学籍番号
- 氏名
- 講義担当教員
- 出題日
- 提出日

## 動作環境
- Pandoc
- pandoc-crossref
- LuaTeX

## 使い方
```shell
pandoc -F pandoc-crossref document.md -o output.pdf --template=template.tex --latex-engine=lualatex -N --listings -M "crossrefYaml=./config/crossref_config.yaml"
```

```markdown
---
documentclass: ltjsarticle
title: サンプルレポートI 提出課題
author:
  - id: 17000001
    name: 山田太郎
lecture:
  - teacher: 山田花子
  - date: 2017年10月10日
  - deadline: 2018年12月10日
---
## 以下文章
これはサンプルテキストです
```

### ソースコードの張り付け
pandoc-crossrefによるソースコードの挿入ではなく，listingsを利用したソースコードの挿入を行う場合は以下のように挿入してください．
```markdown
'''{label=lst:helloworld .numberLines caption="サンプル" style=customc .listings}
#include <stdio.h>
int main(){
  printf("Hello, World!");
  return 0;
}
'''
```
labelを`lst:hogehoge`のように指定することで，listings環境を利用しても`[@lst:hogehoge]`のように引用することができます．

## ライセンス
MIT

## 参考リンク
- [Texで作成するレポートの見本](http://www.dml.cs.gunma-u.ac.jp/~seki/lec/rep-sample2.txt)