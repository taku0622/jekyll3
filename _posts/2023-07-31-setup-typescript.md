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

### boolean&number&strig

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

