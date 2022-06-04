---
layout: post
title: Java Silver
author: taku
date: 2022-05-28 17:00
tags: [Java, Certification]
toc: true
---

Studying Java Silver☕

以前、java bronzeを取得したので、silverの勉強を進めていこうと思います。参考書は下記を使用しています。

**徹底攻略Java SE 11 Silver問題集[1Z0-815] 対応**
<!-- <img src="https://images-na.ssl-images-amazon.com/images/I/516G9d-lTgL._SX351_BO1,204,203,200_.jpg" width="200px"> -->

参考書の問題と解説を読んで、必要だと思った箇所をメモしていきます。

## 第1章 簡単なJavaプログラムの作成

### No.3

例:java.utilパッケージに属する全クラスのインポート宣言

```java
import java.util.*;
```

上記の宣言でインポートされるのはjava.utilパッケージに属するクラスだけで、サブパッケージであるjava.util.regexやjava.util.loggingパッケージに属するクラスをインポートできるということではありません。

### No.5

処理を始めるためのメソッドをエントリーポイントと呼びます。

エントリーポイントに適用されるルールは次の通りです。

- 公開されていること(publicであること)
- インスタンスを生成しなくても実行できること(staticであること)
- 戻り値は戻せない(voidであること)
- メソッド名mainであること
- 引数はString配列型を1つ老けとること

エントリーポイントの引数には、String配列型だけではなく、次のように可変長引数のString型を受け取ることもできます。

```java
public static void main(Strgin... args){
}
```

### No.8

以下のコマンドの引数はいくつか。

```
java Sample.java a \" a\" "a "b c
```

A. 5個
①a
②"
③a"
④ab
⑤c

## 第2章 Javaの基本データ型と文字列操作

### No.2

次の式のうち、コンパイルエラーになるものを選びなさい。(1つ選択)

A.int a = 267; // 267

B.int b = 0413; // 267←8進数

C.int c = 0x10B; // 267←16進数、"Bは11"

D.int d = 0b100001011; // 267←2進数

E.int e = 0827; // 8進数表記だが、"8"があるためエラー

### No.3

アンダースコア「_」を使った数値表記は、桁数の多い数値リテラルの見やすさを向上させる目的でJava SE 7 から導入されました。以下のルールに従えば、出現する場所や回数は基本的に自由です。

- リテラルの先頭と末尾には記述できない
- 記号の前後には記述できない(記号とは小数点を表すドット「.」、long型やfloat型リテラルを表す「L」や「F」、2進数を表す「0b」、16進数を表す「0x」)