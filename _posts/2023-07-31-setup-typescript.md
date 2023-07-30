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
<img src="https://images.app.goo.gl/QrekmNyNC8A3p8RS7" width="200px">

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

- index.tsを作成する

```ts
let hello: string = 'hello';
console.log(hello);
```

- tscコマンドでコンパイルしてjsファイル作成

```bash
tsc index.ts
```

エラーが出た場合(powershell))
+ "このシステムではスクリプトの実行が無効～～"以下参照
	<https://rainbow-engine.com/ps-script-execution-disabled/>

+ "for (let i = startIndex ?? 0;～～"以下参照
	<https://zenn.dev/hayato94087/articles/cdf411c0181820>
	<https://kumaskun.hatenablog.com/entry/2019/10/23/231348>