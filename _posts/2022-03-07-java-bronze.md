---
layout: post
title: Java Bronze
author: taku
date: 2022-03-07 23:23
last_modified_at: 2022-03-13 15:33
tags: [Java, Certification]
toc:  true
---

Studying Java Bronze☕

今日から、試験日3/12(土)まで、毎日この記事を更新していこうと思います。

以前から少しずつ勉強していて、この参考書を使用しています。


**徹底攻略Java SE Bronze問題集［1Z0-818］対応**
<img src="https://img.ips.co.jp/ij/19/1119101075/1119101075-520x.jpg" width="200px">

第8章 総仕上げ問題を実施したので、間違えた問題の中で注意が必要な問題の紹介をしていきます。

## 間違えた問題

以下間違えたの重要な部分です。

### No.14

コンストラクタチェーン

以下のプログラムは次の順番で実行される。

```java
package bronze;

public class SubClass extends SuperClass {
	private int a;
	private int b;

	public SubClass(int a) {
    super(); // コンパイル時、暗黙的に生成される。
		this.a = a;
	}

	public SubClass(int a, int b) {
		this(a);
		this.b = b;
	}

	public static void main(String[] args) {
		SubClass subClass = new SubClass(2, 3);
		System.out.println(subClass.num + ":" + subClass.a + ":" + subClass.b);
	}

}
class SuperClass {
	protected int num;
	public SuperClass() {
		this.num = 1;
	}
	public SuperClass(int num) {
		this.num = num;
	}
}
```

1. mainメソッドのsubClassインスタンスが生成される。
2. コンストラクタSubClass(a,b)が呼ばれて、その中のthis(a)が呼ばれる。
3. コンストラクタSubClass(a)が呼ばれて、コンパイル時、暗黙的に生成されたsuper()が実行される。
4. super();でSuperClassのコンストラクタSuperClass()が呼ばれて、フィールドnumに1が代入。
5. this.a = aが実行、this.b = bが実行。


実行結果
```
1:2:3
```

### No.16

インタフェースの定義に関する問題です。
インタフェースは、情報隠蔽を実現するために分けた公開・非公開のうち、公開する部分を定義するために使います。そのため、インタフェースには、public以外のフィールドやメソッドは定義できません。
また、インタフェースに定義できるフィールドは定数だけです。そのため、初期値を設定していないフィールドの宣言はコンパイルエラーとなります。


インタフェースに定義するメソッドは、すべてpublic abstractで対照的に修飾される抽象メソッドです。抽象メソッドはstaticで修飾できません。抽象メソッドは実装を持たず、実装を提供するクラスが別に必要です。一方、staticなメソッドは、インスタンスを作らなくても実行できるメソッドです。そのため、staticなメソッドは実装を持たなければなりません。


以上のことから、選択肢A,Dが正解です。これらのメソッドは、コンパイラによって暗黙的にpublic, abstractで修飾されるため、修飾子を省略しても問題ありません。

### No.17

インスタンスフィールドの初期化処理を記述しなかった場合、次のデフォルト値で暗黙的に初期化される。

【デフォルト値】

**プリミティブ型**
- 整数型：0
- 浮動小数点型：0.0
- 文字列型：\u0000
- 真偽値型：false

**参照型**
null


### No.21


アクセス修飾子を使ったアクセス制限に関する問題です。privateで修飾されたメソッドは、同一クラス外からはアクセスできないこと
がポイントです。privateは「同一クラスからアクセス可能」であることを表すアクセス修飾子です。たとえ、サブクラスであってもスーパークラスのprivateなメソッドにはアクセスできません。

同一クラスからであれば、明示的に自インスタンスを参照するthis変数を使ってprivateメソッドにアクセスできます。次のコートは、自インスタンスを参照するthis変数を使ってprivateメソッドにアクセスする例です。

```java
package bronze;

public class Sample {
	void fuga() {
		this.hoge();
	}
	private void hoge() {
		System.out.println("hoge");
	}
	public static void main(String[] args) {
		// TODO 自動生成されたメソッド・スタブ
		Sample sample = new Sample();
		sample.fuga();
	}

}
```

出力結果

```
hoge
```

### No.29

情報隠蔽の概念に関する問題です。

情報隠蔽は、抽象化を維持するための設計原則です。抽象化することで共通の部分だけに着目すればよくなるため、クラス間の関係はシンプルになります。

シンプルなソフトウェアは、理解しやすく、バグを減らしやすく、そして変更を容易にしてくれます。このシンプルなソフトウェアを維持するために情報を隠蔽します。ここでいう情報とは、インスタンスが持っているデータではなく、ソフトウェアの構造の詳細、つまり実際に動作するインスタンスの種類(型)のことです。

情報隠蔽では、まず公開するものと、非公開にするものに分けます。Javaでは、公開部分をインタフェースとして定義し、ポリモーフィズムによって実際に動くインスタンスの型に隠蔽します。また、非公開にしたい部分への不適切なアクセスを防ぐために、パッケージやアクセス修飾子を使ってアクセス制限を行います。

抽象化が複数のクラスの関係性に関する原則であるのに対し、選択しBのカプセル化は単独のクラスをどう作るべきかという原則です。よって、抽象化を維持する情報隠蔽とは関係がありません。選択肢Cのアクセサメソッドは、データ隠蔽の結果として必要になるもので、情報隠蔽とは関係がありません。選択肢Fのインスタンス化は、オブジェクト指向全般に必要な概念であり、情報隠蔽に特化するものではありません。

### No.31

クラス名に利用できる文字に関する問題です。

1文字目以降に利用できる文字は、Unicode文字、アンダースコア「_」、ドル記号「$」、2文字目以降はこれらに加えて(0～9)です。
パーセント記号「%」、シャープ記号「#」、ハイフン「-」は、いずれもクラス名に利用できない文字です。


### No.33

Javaの特徴に関する問題です。

Javaプログラム言語には、次のような特徴があります。

- プラットフォームに依存しない
- アーキテクチャに依存しない
- 自動でメモリが解放される
- 実行時にコンパイルしながら実行する「実行時コンパイル方式」を採用している
- マルチスレッドによる並行処理をサポートしている
- セキュリティ性能が高い

Javaでは「Write once, Run Anywhere」の標語が示すとおり、様々プラットフォームで動作します。

Javaではｍメモリ管理はJVM(Java Virtual Machine)の「ガベージコレクタ」と呼ばれる自動メモリ管理機能によって行われます。これにより、プログラマーは煩雑なメモリ操作のためにプログラミングする必要がなくなります。これは即ち、プログラマーがメモリを直接操作できないことを意味します。

アーキテクチャとはソフトウェアを構成するクラス同士の構造のことで、ソフトウェアの用途や形態によってさまざまなアーキテクチャがあります。Javaは用途を特定しておらず、特定のアーキテクチャに依存しません。

Javaのソースコードは、コンパイラによってプログラムの実行に最適化された中間コードにコンパイルされます。実行時にはJVMがこの中間コードを読み込んでネイティブコードにコンパイルして実行します。


### No.35

staticメソッドからアクセスできるフィールドの種類に関する問題です。

staticメソッドからインスタンスフィールドへは、アクセスできないので注意しましょう。

staticメソッドの特徴は、インスタンスを生成しなくても呼び出せることです。一方、インスタンスフィールドの特徴は、インスタンスごとにフィールドを持っていることです。そのため、インスタンスを必要としないstaticメソッドから、インスタンスが存在しなければいけないインスタンスフィールドにアクセスすることができません。

設問のコード6行目で、staticメソッドからインスタンスフィールドnameにアクセスしているためコンパイルエラーとなります。

### No.58

コンストラクタに関する問題です。

サブクラスは、スーパークラスに定義したフィールドやメソッドを引き継ぎます。ただし、サブクラスのインスタンスは、次の2つのスーパークラスから引き継げません。

- コンストラクタ
- privateなフィールドやメソッド

コンストラクタっは、そのコンストラクタが定義されているクラスのインスタンスの準備をするためのメソッドです。よって、スーパークラスのコンストラクタがサブクラスに引き継がれることはありません。

コンストラクタの定義には、次の3つのルールがあります。

- コンストラクタはクラス名と同じであること
- インスタンス生成時にしか使えない
- 戻り値型を記述できない

コンストラクタは、上記のようなルールを持つ以外は通常のメソッドと変わりません、そのため、publicやprotected、デフォルト、privateのいずれかのアクセス修飾子も使えます。

コンストラクタの目的は、インスタンスの準備です。ほかのインスタンス唐津割れる前に、事前にすべきことがあればコンストラクタで処理します。
コンストラクタで必ずしもすべてのフィールドを初期化する必要なありません。

## デフォルトコンストラクタ

コードに明示的にコンストラクタを定義すると、デフォルトコンストラクタは自動的に追加されなくなることに注意しましょう。
設問のコード4～6行目では、String型の引数を1つとるコンストラクタを定義しています。そのため、デフォルトコンストラクタは追加されません。9行目で引き数足のコンストラクタを呼び出していますが、Trainクラスには引数無しのコンストラクタは定義されていないためコンパイルエラーとなります。

## オーバーライド

オーバーライドとは、スーパークラスに定義したメソッドをサブクラスで「再定義」することです。オーバーライドが成り立つ条件は、次の3点です。

- メソッドのシグニチャがスーパークラスのものと同じであること
- 戻り値の型がスーパークラスのメソッドと同じか、サブクラスであること
- メソッドのアクセス制御がスーパークラスと同じか、それよりも緩いこと
※シグニチャ｛メソッド名、引数の型、引数の順番｝

## static

staticフィールドの値の保持とstaticメソッドの呼び出しに関する問題です。

- インスタンスメソッドからstaticメソッドの呼び出しはできる。
- staticメソッドからインスタンスメソッドの呼び出しはできない。

## データ型

データ型が保持できる値の範囲を次に示します。

【データ型】

|  データ型  |  ビット数  |  保持できる値  |
| --------- |--------- |--------- |
|  byte  |  8  |  -128 ~ 127  |
|  short  |  16  |  -32,768 ~ 32,767  |
|  int  |  32  |  -2,147,483,648 ~ 2,147,483,647  |
|  long  |  64  |  -9,223,372,036,854,775,808 ~ 9,223,372,036,854,775,807  |


## 追記(2022/03/12)

本日、Java Bronzeの試験がありました。

結果は、**合格**でした。

正答率は80%だったので、分からない問題もありました。

以下の問題が不正解だったようです。

- Javaのデータ型(プリミティブ型、参照型)
- Javaプログラムのコンパイルと実行
- do-while文の作成と使用
- static変数およびstaticメソッド
- while文の使用
- メソッドのオーバーライド
- 具象クラス、抽象クラス、インターフェース
- 参照型の型変換
- 各種演算子の使用
- 変数屋定数の宣言と初期化、値の有効範囲

今後も精進していきます。

以上。