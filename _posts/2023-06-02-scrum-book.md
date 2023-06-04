---
layout: post
title: SCRUM BOOT CAMP
author: taku
date: 2023-06-02 21:00
last_modified_at: 2023-06-03 23:00
tags: [読書]
toc: true
---

Readinging Scrum book☕

仕事の先輩から業務導入しているスクラム開発についての本をお借りしたのでメモします。

**SCRUM BOOT CAMP THE BOOK【増補改訂版】 スクラムチームではじめるアジャイル開発**
<img src="https://m.media-amazon.com/images/I/51Az2GGiHGL.jpg" width="200px">

## SCRUMってなに？

### はじめに

ソフトウェアを作る上でで重要なこととは、顧客や利用者の課題を解決したり、お金を稼いだりする、つまり成果をあげること。

何のために作るのかを明らかにし、現在作っているものが本当に成果を実現できているのかをこまめに確認しながら進めていくことが必要。

その過程で当初作ろうと思っていたものよりも良いアイデアが出てくれば、それを受け入れ、作るものを変えていく。そうすることで成果が最大化していく。

### アジャイル開発とは？

成果を最大化する進め方とは

- 関係者は目的の達成のためにお互いに協力し合いながら進める。
- 一度にまとめてではなく、少しずつ作り、早い段階から実際に動作するものを届け続けて評価を繰り返す。
- 利用者の反応や関係者からのフィードバックを継続的に得ながら、作っているもの自体や計画を調整する。

アジャイル開発とは何か単一の開発手法を指すものではなく、似たような開発手法に共通した価値観と行動原則に名前がついたものであり、それを体現するさまざまな手法がある。スクラム、エクストリーム・プログラミング(XP)、カンバンがある。

共通してるものは「事前にすべてを正確に予測し、計画することはできない」ということを前提にしているということ。

どのくらいの期間や人数で仕事するかを決めて、その範囲内で大事な要求から順位プロダクト(アジャイル開発において実際に作られるもののこと。主にソフトウェアを指すが、必要なドキュメントなども含む)を作っていく。つまり、重要なもの、リスクが高いものほど先に作り、そうでないものは後回しにすることで成果を最大化していく。

参考：アジャイルソフトウェア開発宣言(https://agilemanifesto.org/iso/ja/manifesto.html)

### スクラムってなんだろう？

前述のとおり、アジャイル開発手法の1つ。以下の特徴がある。

- 要求を価値やリスクや必要性を基準にして並び替えて、その順にプロダクトを作ることで成果を最大化する。
- スクラムでは固定の短い時間に区切って作業を進める。固定の時間のことを"タイムボックス"と呼ぶ。。
- 現在の状況や問題点を常に明らかにする。これを"透明化"と呼ぶ。
- 定期的に進捗状況やつくっているプロダクトで期待されている成果をえられるのか、仕事の進め方に問題がないかどうかを確認する。これを"検査"と呼ぶ。
- やり方に問題があったり、もっとうまくできるほうほうがあったりすれば、やり方そのものを変える。これを"適応"と呼ぶ。

スクラムはわかっていることよりも分からないことが多いような複雑な問題を扱うのにてきしており、5つの"イベント"(会議など)、3つの"ロール"(人の役割)、3つの"成果物"など最低限のルールのセットで構成されている。

スクラムのルールは"スクラムガイド"(https://scrumguides.org/)で定義されている。

### 機能や要求を並べ替える

【作成物1】プロダクトバックログ

- 実現したいことをリストにして並べ替える
	- 優先度ではない
- 常にメンテナンスして最新を保つ
	- 項目が追加されてたり、削除されたりする
	- 順番を定期的に見直す
- 上位の項目は見積りを済ませておく(定期的に見積もり直す)

スクラムでは、機能や要求、要望、修正などプロダクトに必要なものを抽出し、順番に並び替えた"プロダクトバックログ"と呼ばれるリストを作成する。プロダクトに１つで、順番はその項目が実現されたときに得られる価値やリスク、必要性などによって決定する。

### プロダクトの責任者は誰？

【ロール1】プロダクトオーナー
- プロダクトのWhat担当
- プロダクトの価値を最大化する
- プロダクトの責任者(結果責任)でプロダクトに1人必ず必要
- プロダクトのバックログの管理者
- プロダクトバックログ項目の並び順の最終決定権をもつ
- プロダクトバックログ項目が完成しているかどうかを確認
- 開発チームに相談できるが干渉はできない
- ステークホルダーとの協業

プロダクトバックログの管理の責任者を"プロダクトオーナー(PO)"と呼ぶ。プロダクトオーナーはプロダクトの責任者であり、1プロダクト1人。開発チームを活用して、そのプロダクトが生み出す価値を最大化する責任がある。プロダクトバックログの並び替えのほかに、次のようなことを行う。

- プロダクトのビジョンを明らかにし、周りと共有する
- おおよそのリリース計画を定める
- 予算を管理する
- 顧客、プロダクトの利用者や組織の関連部署などの関係者と、プロダクトバックログの項目の内容を確認したり、作る順番や実現時期を相談したりする
- 既存のプロダクトバックログの項目の内容を最新の状態に更新する
- プロダクトバックログの項目の内容を関係者が理解できるように説明する
- プロダクトバックログ項目が完成しているかどうかを確認する

### 動作するプロダクトを開発する

【ロール2】開発チーム
- プロダクトのHow担当
- モノを作る
- 3人～9人が適切な規模
- 全員揃えばプロダクトを作る能力が揃う
- 肩書きやサブチームはなし

主な役割は、プロダクトオーナーが順位づけたプロダクトバックログの項目を順番に開発してくこと。

開発チームは、プロダクトを作るために必要なすべての作業をできなればいけない、要求の分析をする、設計する、コードを書く、サーバを構築する、ドキュメントを書くといった能力が開発チームの中に必要。これを"機能横断的"なチームと呼ぶ。

開発チーム内での仕事の進め方は、開発チームで行い、責任は開発チーム全体で持つ、これを"自己組織化"と呼ぶ。

このように開発チームで主体的に作業を進めることによって、開発チームの能力は継続的に向上していく。

### 短く区切って繰り返す

【イベント1】スプリント

- 1ヶ月までの同じ時期に区切って繰り返す、1つの区切りをスプリントと呼ぶ
- スプリントは、ほかのイベントのコンテナ(入れ物)となる
- 期間の長さが変わっていけない

開発チームはこの期間の中で、計画、設計、開発、テストなどプロダクトバックログ項目を完成させるのに必要な作業をすべて行う。

### 頻繁に計画する

スプリントで何を作るのか(What)、どのように作るのか(How)を計画する必要がある。計画は"スプリントプランニング"と呼ばれるイベントで決定する(スプリント計画会議とも呼ぶ)。スプリントプランニングに使える時間は、1カ月スプリントであれば、8時間程度。

【イベント2】スプリントプランニング
- スプリント計画会議とも呼ぶ
- スプリントで開発をするためには計画が必要なので、スプリントの冒頭で実施する
- プロダクトオーナーは何をほしいか(トピック1)
- 開発チームはどれくらいできそうか(トピック1)
- 開発チームはどうやって実現するか(トピック2)

トピック1：スプリントで何を達成するか決める

プロダクトオーナーが今回のスプリントで達成した目的("スプリントゴール")を明らかにする。プロダクトバックログの上位の項目になるのが一般的。


トピック2：開発チームがどうやって選択したプロダクトバックログ項目を実現するかについて計画を立てる。洗濯したプロダクトバックログ項目ごとに、具体的な作業を洗いだすなどして作業計画("スプリントバックログ")を立てる。スプリントバックログは1日以内で終わるように分割するのが一般的。

【作成物2】スプリントバックログ
- 選択したプロダクトバックログ項目と実行計画
- プロダクトバックログを具体的に分割する
- 後から増えることもある
- 1タスクは1日以内で終わるサイズ

### スプリントごとに完成させていく

【作成物3】インクリメント
- 開発チームは完成したインクリメントを作成
	- インクリメントとはこれまでのスプリントでの成果とコンスプリントで完成したプロダクトバックログ項目に併せたものを指す
	-	リリースするかどうかに関係なく動作して検査可能でなければいけない

スクラムでは、スプリント単位で評価可能な"インクリメント"を作ることが求められる

プロダクトオーナーと開発チームが「完成」の指す内容について共通の基準を持つ必要がある。これを"完成の定義"と呼ぶ。開発チームは、この定義を満たしたプロダクトを作らなければならない。

【完成の定義】
- 完成の定義を作り、何をもって「完成」とするのか基準を定める
- スプリントでどこまでやるか決める
- 以下はあくまで一例。プロダクトオーナーと開発りーむで事前合意する
	- コードレビュー
	- チェックイン
	- ユニットテスト
	- カバレッジ85%
	- 結合テスト
	- 受入テスト
	- クロスブラウザ
	- 静的解析
	- ドキュメント
	- 性能
	- セキュリティ
	- デプロイ

### 毎日確認する






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

### No.17

キャスト式は、プログラマーがコンパイラに対して、互換性を保証することを意味します。

AにはBとの互換性を示すものは何もないため、自動で型変換をすることはできません。そこでキャスト式を記述して、プログラマーがコンパイラに対して、互換性の保証を行っています。そのため、コンパイルエラーが発生することはありません。

しかし、変数aの参照先にあるインスタンスは、Aのインスタンスです。AのインスタンスにはBの差分が含まれていないため、Bでオーバーライドしたメソッドを実行できません。

AのインスタンスをBのインスタンスに変換することはできません。そのため、コンパイルは問題なく通りますが、実行すると型の変換に失敗した旨の例外がスローされます。

```java
public class AClass {
	void hello() {
		System.out.println("helloA");
	}
}
```

```java
public class AClass {
	void hello() {
		System.out.println("helloA");
	}
}
```

```java
public class Sample implements Interface {
	public static void main(String[] args) {
		AClass a = new AClass();
		BClass b = (BClass)a; // コンパイルは通るが、実行時に例外がスローされる。
		b.hello();
	}
}
```

## 追記(2022/09/28)

9/25、Java Silverの試験がありました。

結果は、**合格**でした。

正答率は70%だったので、分からない問題もありました。
ギリギリで危なかった。

以下の問題が不正解だったようです。

- Local Variable Typeインタフェース
- static変数とstaticメソッド
- インタフェースの作成と実装
- オブジェクトのフィールドへの読取と書き込み
- パッケージ宣言とインポート
- メソッドのオーバーライドによるポリモーフィズム
- メソッドのオーバーロードとメソッド呼び出し
- 参照型のキャストとポリモーフィックなメソッドの呼び出し
- 変数のスコープ
- 変数の宣言及び初期化（基本データ型のキャストとプロモーションを含む）
- 引数や戻り値を持つメソッドとコンストラクタの作成
- 抽象クラスの作成と継承
- 文字列の作成と操作

今後も精進していきます。

以上。