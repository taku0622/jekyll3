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

### No.4

nullとはリテラルの一種で参照型変数が「何も参照しない」ことを表現するためのデータです。プリミティブ型の変数は値を保持するものであって参照を保持できません。

### No.5

識別子(変数・メソッド・クラスの名前)に使える記号はアンダースコア「_」とドル記号「$」であることと、数字は2文字目以降に使える。特に変数名は数字から初めてはいけない。


### No.12

StringクラスのindexOfメソッドの引数に「c」という文字を渡すと2が戻されます。
また、引数で指定した文字がなければ-1が戻されます。

文字列を渡すこともできます。文字列を引数に渡した場合、このメソッドは、その文字列が始まる最初の文字位置を戻します。もし、文字列が存在しなければ、-1が戻されます。

```java
public class Sample {
	public static void main(St
		String string = "abcde";
		System.out.println(string.indexOf('c'));	// 2
		System.out.println(string.indexOf('f'));	// -1
		System.out.println(string.indexOf("cd"));	// 2
		System.out.println(string.indexOf("cdf"));	// -1
	}
}
```

### No.19

nullが代入されたString型変数に+=演算子を使って文字列「null」を連結することによって、変数stringは「nullnull」という文字列を保持していることになります。

```java
public class Sample {
	public static void main(String[] args) 
		String string = null;
		string += "null";
		System.out.println(string); // nulllnull
	}
}
```

### No.20

変更可能な文字列を扱うクラスとして、**java.lang.StringBuilderクラス**が用意されています。StringBuilderは、内部にバッファを持った文字列を扱うためのクラスです。Stringが文字列と同じ長さのchar配列を扱うのに対し、StringBuilderは保持している文字列+余分のバッファを持ち、デフォルトで16文字分のバッファを持っています。


## 第3章 演算子と判定構造

### No.4

前置インクリメントと後置インクリメントは加算と減算のタイミングに注意する。

```java
public class Sample {
	public static void main(String[] args) {
		int a = 10;
		int b = a++ + a + a-- - a-- + ++a; 	// b = 10 + 11 + 11 - 11 + 11
		System.out.println(b);				// 32
	}
}
```

### No.5

数値や文字、真偽値、参照などさまざまな対象物を比較できます。しかし、このうち「>」「>=」「<」「<=」の4つの演算子は数値の大小を比較するもので、数値以外の比較はできません。


