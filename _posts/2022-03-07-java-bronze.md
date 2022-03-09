---
layout: post
title: Java Bronze
author: taku
date: 2022-03-07 23:23
tags: [Java, Certification]
---

Studying Java Bronze☕

今日から、試験日3/12(土)まで、毎日この記事を更新していこうと思います。

以前から少しずつ勉強していて、この参考書を使用しています。


**徹底攻略Java SE Bronze問題集［1Z0-818］対応**
<img src="https://img.ips.co.jp/ij/19/1119101075/1119101075-520x.jpg" width="200px">

第8章 総仕上げ問題を実施したので、間違えた問題の中で注意が必要な問題の紹介をしていきます。

## 間違えた問題

|  No  |
| :--: |
|  1  |
|  7  |
|  8  |
|  9  |
|  10  |
|  14  |
|  15  |
|  16  |
|  17  |
|  21  |
|  24  |
|  28  |
|  29  |
|  30  |
|  31  |
|  33  |
|  35  |
|  42  |
|  44  |
|  50  |
|  54  |
|  57  |
|  58  |

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

答え、写す

```
インタフェースの定義に関する問題です。
インタフェースは、情報隠蔽を実現するために分けた公開・非公開のうち、公開する部分を定義するために使います。そのため、インタフェースには、public以外のフィールドやメソッドは定義できません。
また、インタフェースに定義できるフィールドは定数だけです。そのため、初期値を設定していないフィールドの宣言はコンパイルエラーとなります。

インタフェースに定義するメソッドは、すべてpublic abstractで対照的に修飾される抽象メソッドです。抽象メソッドはstaticで修飾できません。抽象メソッドは実装を持たず、実装を提供するクラスが別に必要です。一方、staticなメソッドは、インスタンスを作らなくても実行できるメソッドです。そのため、staticなメソッドは実装を持たなければなりません。

以上のことから、選択肢A,Dが正解です。これらのメソッドは、コンパイラによって暗黙的にpublic, abstractで修飾されるため、修飾子を省略しても問題ありません。
```