---
layout: post
title: Set Up TypeScript
author: taku
date: 2023-07-30 0:00
last_modified_at: 2023-07-30 0:15
tags: [ts]
toc: true
---

Set Up TypeScript🌙

私用PCにもTypeScriptの開発環境を構築する。

**超TypeScript入門 完全パック**
<img src="https://img-c.udemycdn.com/course/480x270/2785212_a1d0_7.jpg" width="200px">

## TypeScriptってなに？

JavaScriptにコンパイルさせる静的型システムが付いたJavaScriptの上位集合。

## インストール方法

### npmインストール

以下サイトを参考にしてnpmコマンドを使えるようにする。
<https://qiita.com/sefoo0104/items/0653c935ea4a4db9dc2b>

node.js公式HPからインストーラーをダウンロードする。

※npmはnode package managerの略でjsを使ったフロントエンド開発を行うためのパッケージ管理ツール

### TypeScriptインストール

以下のコマンドを実行。

```bash
npm i -g typescript
```

## TypeScript実行方法

例）

1. index.tsを作成する

```ts
let hello: string = 'hello';
console.log(hello);
```

2. tscコマンドでコンパイルしてjsファイル作成

```bash
tsc index.ts
```

エラーが出た場合(powershell))
- "このシステムではスクリプトの実行が無効～～"以下参照
	<https://rainbow-engine.com/ps-script-execution-disabled/>

- "for (let i = startIndex ?? 0;～～"以下参照
	<https://zenn.dev/hayato94087/articles/cdf411c0181820>
	<https://kumaskun.hatenablog.com/entry/2019/10/23/231348>

3. コンパイルで作成されたindex.jsを実行

```bash
node index.js
```

実行結果

```bash
hello
```

## TypeScriptの型

TypeScriptとJavaScriptの型は全く別物。
型検査するものが違う。

TypeScript：tsc

JavaScript：JavaScriptエンジン(ブラウザに搭載されているもの。chrome：v8エンジン、FireFox：SpiderMonkey、Edge：chakra、Safari：JavaScriptコア)


TypeScript → JavaScript → 機械語　のイメージ

TypeScriptのString型とJavaScriptのString型は違うもの。

### 型注釈&型推論

型注釈：変数宣言の際の ***: string*** の部分。

型推論：型注釈を省略したもの。

### boolean&number&string

```ts
// boolean
let hasValue: boolean = true;

// number
let count: number = 10;
let float: number = 3.14;
let negative: number = -0.12;

// string
let single: string = 'hello';
let double: string = "hello";
let back: string = `hello`;
```

### object

```ts
// object
// 型注釈
const person1: {
  name: string;
  age: number;
} = {
  name: 'jack',
  age: 21
}
// 型推論
const person2 = {
  name: 'jack',
  age: 21
}
// 型推論
const person3 = {
  name: {
    first: 'Jack',
    last: 'Smith'
  },
  age: 21
}
```

### array

```ts
// array
// 型注釈
const fruits1: string[] = ['Apple', 'Banana', 'Grape']
// 型推論
const fruits2 = ['Apple', 'Banana', 'Grape']
```

### tuple

明示的に型注釈をして型・要素数をする型。

オブジェクト型に近い。

配列に制限をかけたもの。

```ts

// Tuple
const book: [string, number, boolean] = ['business', 1500, false];
book.push(21);
book[1] = 700; // 値変更
console.log(book[2]); // 値参照
console.log(book[3]); // 後から入れたものは参照できない
```

### enum(列挙型)

特定のまとまったグループのみを受け入れるようにする。

```ts
const CoffeeSize = {
  SHORT: 'SHORT',
  TALL: 'TALL',
  GRANDE: 'GRANDE',
  VENTI: 'VENTI'
}
const coffee = {
  hot: true,
  size: CoffeeSize.TALL
}
coffee.size = 'hello' // 値変更できてしまう。
```

(sizeを)特定のまとまったグループのみを受け入れるようにする。

```ts
enum CoffeeSize {
  SHORT = 'SHORT',
  TALL = 'TALL',
  GRANDE = 'GRANDE',
  VENTI = 'VENTI'
}
const coffee = {
  hot: true,
  size: CoffeeSize.TALL
}
```

+＠

```ts
// 初期化を省略すると要素数が入る
enum CoffeeSize {
  SHORT, // 0
  TALL, // 1
  GRANDE, // 2
  VENTI // 3
}
```

### any

なんでも入る型。

正しくTypeScriptを書くためには、
なるべくanyは使わない。

```ts
// any
let anything: any = true;
anything = 'hello';
anything = ['hello', 33, true];
anything = {};
anything.name = 'john';
let banana = anything; // こんなこともできてしまう。
console.log(banana); // { name: 'john}
```

### union

複数の型を受け入れられるようにした型。

```ts
// union
let unionType: string | number = 10;
unionType.toString; // numberで使えるメソッド
unionType = 'hello';
unionType.toUpperCase; // Stringで使えるメソッド
let unionTypes: (number | string)[] = [21, 'hello', 5]; // 配列
```

### literal

決まった値のみを扱う型。

```ts
// literal
const apple: 'apple' = 'apple';
let clothSize: 'small' | 'medium' | 'large' = 'large';
const cloth: {
  color: string,
  size: 'small' | 'medium' | 'large'
} = {
  color: 'white',
  size: 'large'
}
```

### type alias

複雑な型を変数のように扱う。

```ts
// typeエイリアス
type clothSize = 'small' | 'medium' | 'large';
const cloth: {
  color: string,
  size: clothSize
} = {
  color: 'white',
  size: 'large'
}
```

### 関数に型をつける

```ts
// 関数：足し算
function add(num1: number, num2: number): number {
  return num1 + num2;
}
add(3, 4);
```