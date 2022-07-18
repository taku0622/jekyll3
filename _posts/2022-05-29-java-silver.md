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
<img src="https://images-na.ssl-images-amazon.com/images/I/516G9d-lTgL._SX351_BO1,204,203,200_.jpg" width="200px">

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
- 引数はString配列型を1つ受け取ること

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

## 第5章 配列の操作

### No.2

大カッコはデータ型の後ろだけでなく、変数名の後ろに記述できます。さらに複数記述する大カッコを一度にまとめて記述することは必要ありません。

```java
public class Sample {
	public static void main(String[] args) {
		int[] a;		// 1次元配列
		int b[];		// 1次元配列
		int[][] c;		// 3次元配列
		int d[][];		// 2次元配列
		int[] e[];		// 2次元配列
		int[][] f[];		// 3次元配列
	}
}
```

上記のプログラムを実行してもコンパイルエラーにはならない。

### No.5

配列インスタンスを生成しただけでは要素の中身が作られることはありません。配列インスタンスを生成するとき、要素の値は次のように代入しなければいけません。

**【配列の要素のデフォルト値】**

|型|デフォルト値|
|---|---|
|整数型|0|
|浮動小数点型|0.0|
|真偽型|false|
|文字型|\u0000|
|オブジェクト型|null|

### No.7

newと初期化子を使って、配列のインスタンス生成と初期化を同時に行う場合、要素数は自動算出されるため、大カッコの中に要素数は指定できません。


初期化しを使って、配列のインスタンス生成と初期化を同時に行う場合、変数の宣言と参照の代入も同時に行います。セミコロン「;」を使って変数宣言と配列のインスタンス生成のタイミングを分けることはできません。

### No.10

cloneメソッドは、配列の内容をそのままコピーします。

```java
public class Sample {
	public static void main(String[] args) {
		int[] arrayA = {1,2,3};
		int[] arrayB = arrayA.clone();
		System.out.println(arrayA == arrayB);
		System.out.println(arrayA.equals(arrayB));
		System.out.println("arrayA= {" + arrayA[0] +","+ arrayA[1] +","+ arrayA[2] +"}");
		System.out.println("arrayB= {" + arrayB[0] +","+ arrayB[1] +","+ arrayB[2] +"}");
	}
}
```

出力結果

```
false
false
arrayA= {1,2,3}
arrayB= {1,2,3}
```

## 第6章 インスタンスをメソッド

### No.4

インスタンスの参照がなくなった時点で、ガベージコレクションの対象となります。ガベージコレクションのタイミングはJVMが決めます。gcメソッドはガベージコレクションの実行を促すだけで、保証はされません。


ガベージコレクタは、インスタンスの破棄を繰り返すことで細切れになったメモリをまとめ、大きな空間を確保する「コンパクション」という機能があります。そのため、ガベージコレクションはCPUに対して負荷の高い処理なのです。

```java
public class Sample {
	public static void main(String[] args) {
		Object aObject = new Object();
		Object bObject = new Object();
		Object cObject = aObject;
		aObject = null;
		bObject = null;
		// more code この時点でbObjectがガベージコレクションの対象になる。
	}
}
```

### No.15

実行されないことが明白なコードがあった場合、コンパイラは「到達不可能なコードがある」とコンパイルエラーを発生させます。

```java
private static void method(int num) {
		if(num < 0) return;
		System.out.println("A");
		return;
		System.out.println("B"); // 到達不能コード。この箇所でコンパイルエラー。
	}
```

### No.17

double型はint型よりも範囲が大きく、暗黙の型変換によって互換性が保たれているデータ型です。そのため、2つのint型を渡した呼び出しはdoubleとintを受け取るcalcメソッドにも、intとdoubleを受け取るcalcメソッドにも両方適応できてしまいます。このような場合、JVMはどちらのメソッドを呼び出すべきかを判断できません。そのため、「あいまいなメソッド呼び出し」としてコンパイルエラーが発生します。

```java
public class Sample {
	public static void main(String[] args) {
		Sample s = new Sample();
		System.out.println(s.calc(0, 0)); // あいまいな呼び出しなので、この箇所でコンパイルエラーが発生する。
	private double calc(int a,double b) { // 2つのcalcメソッドは引数の型の順番が異なるので、オーバーロードは成り立っている。
		return a + b;
	}
	private double calc(double a,int b) { // 2つのcalcメソッドは引数の型の順番が異なるので、オーバーロードは成り立っている。
		return a + b;
	}
}
```

### No.18

オーバーロードの条件は、シグニチャが異なることです。シグニチャは、メソッド名と引数のリストから成り、オーバーロードとして見なされるためにはメソッド名が同じで、引数の数、型、順番のいずれかが異なる必要があります。この条件にアクセス修飾子は含まれません。そのため、アクセス修飾子が異なるだけではオーバーロードとしてみなされません。

### No.19

コンストラクタはプログラマーが自由に定義できるメソッドの一種です。コンストラクタを定義する際、アクセス修飾子についての制限はなく、public、protected、デフォルト、privateの4つ全てのアクセス修飾子で、コンストラクタを修飾することができます。

|アクセス修飾子|概要|
|:----|:----|
|public|すべてのクラスからアクセス可能|
|protected|同じパッケージに属するか、継承しているサブクラスからのみアクセス可能|
|デフォルト|同じパッケージに属するクラスからのみアクセス可能|
|private|クラス内からのみアクセス可能|

### No.21

コンストラクタと初期化子が設定されている場合、初期化子はコンストラクタよりも先に実行されます。

初期化子「{}」は、クラスブロック直下にフィールドやメソッド、コンストラクタと並べて記述する。

初期化子を使えば、オーバーロードされたすべてのコンストラクタで共通の前処理を宣言できます。


***Itemクラス***

```java
public class Item {
	Item(){
		System.out.println("A");
	}
	{
		System.out.println("B");
	}
}
```

***Sampleクラス***

```java
public class Sample {
	public static void main(String[] args) {
		Item item = new Item();
	}
}
```

**実行結果**
```
B
A
```

***static初期化子の例***

```java
public class Item {
	static int num;
	static {
		num = 10;
	}
	public Item() {
		num = 100;
	}
}
```

このようにすると、インスタンスを生成しなかった場合には10が表示されます。

### No.25

thisを使って、コンストラクタ内から、オーバーロードされたコンストラクタを呼び出す場合、コンストラクタ呼び出しのコードよりも前には処理を記述できません。記述するとコンパイルエラーになります。

```java
public class Item {
	public Item() {
		System.out.println("hello");
		this(0, 0);	// コンパイルエラーになる
	}
	public Item(int a, int b) {
		System.out.println(a + b);
	}
}
```

### No.29 & No.30

プリミティブ型の値をメソッドに渡すとき、その値はコピーされて渡されます。
そのため、呼び出したメソッド内で値が変更されても、呼び出し元の値は変わりません。


オブジェクト型の引数では、呼び出し元から呼び出し先のメソッドに参照値がコピーされます。そのため、2つメソッドから参照されるインスタンスは同じになります。メソッドの引数がプリミティブ型なので、参照型なのかは重要なポイントなので、必ずチェックしましょう。

## 第7章 クラスの継承、インターフェース、抽象クラス

### No.3

インターフェースは他のクラスからの「扱い方」を規定したものです。他のクラスから扱えるようにするために、規程する抽象メソッドはすべてpublicでると解釈されます。たとえばアクセス修飾子を記述しなくてもインターフェースはコンパイラによって自動的にpublicで修飾されます。

```java
public interface Interface {
	void hello(); // コンパイラによってpublicで修飾される
}
```

また、インターフェースは、次の2角ルールを満たすフィールドであれば、記述できます。

- finalを使って、動的に値が変更されていないこと(つまり定数)

- staticを使って、インスタンスが生成できなくても使えること

### No.3

Java SE 8からデフォルトメソッドを用いることでインターフェースに実装を記述できるようになりました。これを活用すれば、共通処理をすべての実現クラスで実装したり、抽象クラスで実現したり、抽象クラスを間に挟んだりする必要がなくなります。デフォルトメソッドは次のようにdefault修飾子をつけて定義します。

```java
public interface Interface {
	default void hello() {
		System.out.println("hello");
	}
}
```

default修飾子で修飾されている以外は、クラスに定義するメソッド定義と同じです。なお、デフォルトメソッドもインターフェースに定義するメソッドと同様に、自動的にpublicで修飾されます。

### No.5

インターフェースに定義するデフォルトメソッドですが、***java.lang.Objectクラス***に定義されているメソッドの扱いです。java.lang.Objectクラスに定義されているメソッドをインタフェースでデフォルトメソッドとしてオーバーライドするとコンパイルエラーとなります。

```java
public interface Interface {
	@Override
	default String toString() { // コンパイルエラー
		return "hello";
	}
}
```

***インターフェースと実装クラスの関係***

例↓

**インターフェース**
```java
public interface Interface {
	default String hello() {
		return "hello";
	}
}
```

**実装クラス**
```java
public class Item implements Interface {
	@Override
	public String hello() {
		return "HELLO";
	}
}
```

**Mainクラス**
```java
public class Sample {
	public static void main(String[] args) {
		Interface inter = new Item();
		System.out.println(inter.hello());
	}
}
```

**実行結果**
```
HELLO
```

### No.6

デフォルトメソッドをオーバーライドしたメソッドから、元のデフォルトメソッドを呼び出すには、次の構文を使います。
```
インターフェース名.super.メソッド名();
```

**インターフェース**
```java
public interface Interface {
	default void hello() {
		System.out.println("hello");;
	}
}
```

**実装クラス**
```java
public class Item implements Interface {
	@Override
	public void hello() {
		Interface.super.hello();
		System.out.println("HELLO");
	}
}
```

### No.11

メソッドのオーバーライドには、次の3つのルールがある。

- シグニチャが同じであること
- 戻り値型は同じ型か、サブクラス型であること
- アクセス修飾子は同じか、より緩いものを指定すること

そのため、以下のクラスのサブクラスを定義するとき、helloメソッドのアクセス修飾子はprotected or publicになります。

```java
public class Item  {
	protected void hello() {
		System.out.println("hello");
	}
}
```

### No.12

ポリモーフィズムを使った場合、スーパークラスとサブクラスに同じ名前のフィールドがあったとき、どちらのフィールドを利用するかは宣言した変数の型によって決まります。

どの変数を使うかは、コンパイル時に決まります。コンパイル時には、どの型のインスタンスが動作するかをチェックできないため、変数の型だけが判断基準となります。そのため、「どちらのフィールドを使うか？」という問いは、変数の型によって判断することができます。一方、どのメソッドを使うかは実行時に決まります。そのため、ポリモーフィズムを使ったときには、「どのインスタンスが動作しているか？」「どのメソッドがオーバーライドされているか？」確認しなければいけません。

- フィールドを参照した場合には、変数の型で宣言された方を使う。
- メソッドを呼び出した場合、メソッド内の指示に従う。

**親クラス**
```java
public class AClass {
	String val = "A";
	void print() {
		System.out.println(val);
	}
}
```

**子クラス**
```java
public class BClass extends AClass{
	String val = "B";
}
```
**Mainクラス**
```java
public class Sample {
	public static void main(String[] args) {
		AClass a = new AClass();
		AClass b = new BClass();
		System.out.println(a.val);
		System.out.println(b.val); // AClass型なので、Aが出力
		a.print();
		b.print(); // 変数同様Aが出力
	}
}
```

### No.14

ポリモーフィズムを使った出題の場合、次の2点を確認してください

- 継承関係や実現関係があり、ポリモーフィズムが成り立つ条件を備えているかどうか

- インスタンスが扱っている「型」に、呼び出しているメソッドが定義されているかどうか

```java
public class AClass {
	void hello() {
		System.out.println("hello");
	}
}
```

```java
public class BClass extends AClass{
	void sample() {
		System.out.println("sample");
	}
}
```

```java
public class Sample implements Interface {
	public static void main(String[] args) {
		AClass b = new BClass();
		b.sample();  // コンパイルエラー　Aクラスには存在しないメソッド
	}
}
```

### No.16

ダウンキャスト。
親を子の型に入れられない。
ポリモーフィズムなどは子を親の型に入れている。

```java
public class BClass extends AClass{
	void sample() {
		Number n = 1.0; // Number型はdouble型の親クラス
		double d = n; //コンパイルエラー　
		System.out.println("sample");
	}
}
```

