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

### No.12

「コンスタントプール」：コード中に同じ文字列リテラルが登場した場合、同じStringインスタンスへの参照型が使い回されます。そのため、==演算子を使って同一性を判定するとtrueとなります。

### No.19

switch文は、条件式が戻す値と一致するcase式を実行します。条件式が戻せる値の型には制限があり、条件式は次の型の値を戻す式ではなくてはいけません。
- char
- short
- Character
- Short
- String
- byte
- int
- Byte
- Integer
- Enum

たくさん種類がありますが、次のように覚えましょう。

- int型以下の整数型とそのラッパークラス
- 文字と文字列
- 列挙型

間違えやすいのはlong型が含まれていない点です。ほかにもdoubleやfloatといった浮動小数点を扱う方や、booleanも含まれません。

## 第4章 制御構造

### No.3

while文やdo-while文では、中カッコを省略した場合、次の1文だけが繰り返しの対象となります。

do-while文で中カッコを省略した場合には、doとwhileの間には1文のみを記述できます。2文以上記述した場合には、コンパイルエラーが発生します。

### No.4

for文の初期化文では、同じ型の変数を複数宣言できます。異なる型の変数を同時に宣言することはできません。コンパイルエラーになります。

### No.7

for文で複数の条件文を記述する場合は、論理演算子を使います。初期化文や更新文のように、カンマ「,」で区切って複数の条件を記述するとコンパイルエラーになります。

```java
public class Sample {
	public static void main(String[] args) {
		for (int i = 0; i < 3; i++, period()) {
			System.out.print(i);
		}
	}
	private static void period() {
		System.out.print(",");
	}
}
```

出力結果

```
0,1,2,
```

### NO.11

```java
public class Sample {
	public static void main(String[] args) {
		String[][] array = {{"A","B","C"}};
		for(Object object : array) {
			System.out.println(object);
		}
	}
}
```

出力結果

```
[Ljava.lang.String;@1e81f4dc
```

### No.13

条件式でインクリメントされると変数の値は更新されます。

前置インクリメントの場合、更新されてから判定文。

後置インクリメントの場合、判定してから更新。

```java
public class Sample {
	public static void main(String[] args) {
		int num = 10;
		do {
			num++;
		} while (++num < 10);
		System.out.println(num);
	}
}
```

出力結果

```
12
```

## 配列の操作

### No.2

大カッコはデータ型の後ろだけでなく、変数名の後ろに記述できます。さらに複数記述する大カッコを一度にまとめて記述することは必要ありません。

```java
public class Sample {
	public static void main(String[] args) {
		int[] a;				// 1次元配列
		int b[];				// 1次元配列
		int[][] c;			// 3次元配列
		int d[][];			// 2次元配列
		int[] e[];			// 2次元配列
		int[][] f[];		// 3次元配列
	}
}
```

上記のプログラムを実行してもコンパイルエラーにはならない。

### No.5

配列インスタンスを生成しただけでは要素の中身が作られることはありません。配列インスタンスを生成するとき、要素の値は次のように代入しなければいけません。

【配列の要素のデフォルト値】

|型|デフォルト値|
|---|---|
|整数型|0|
|浮動小数点型|0.0|
|真偽型|false|
|文字型|\u0000|
|オブジェクト型|null|