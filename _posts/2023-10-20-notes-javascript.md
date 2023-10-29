---
layout: post
title: JavaScript
author: taku
date: 2023-10-20 0:00
last_modified_at: 2023-10-20 1:15
tags: [js]
toc: true
---

Notes JavaScript👀

JavaScriptのコースを受講して、注意事項をまとめる。

**超JavaScript入門 完全パック**
<img src="https://img-c.udemycdn.com/course/750x422/4652658_cdfe_16.jpg" width="200px">

## 同値演算子(===) vs 等値演算子(==)

差は以下。等値演算子はデータ型が異なっていても値が等しいのであれば、trueを返してしまう。

```js
let flag;
flag = 1 === 1; // true
flag = 1 === '1'; // false

flag = 2 == 2; // true
flag = 2 == '2' // true
```

また、どちらもオブジェクトや配列の比較はfalseになる。

```js
const coffee1 = { name: "black", size: "small" };
const coffee2 = { name: "black", size: "small" };

console.log(coffee1 === coffee2); // false
console.log(coffee1 == coffee2); // false

const fruits1 = ["apple", "banana"];
const fruits2 = ["apple", "banana"];

console.log(fruits1 === fruits2); // false
console.log(fruits1 == fruits2); // false
```

## Truthy vs Falsy

条件式で使用される真偽値の判定基準。

Falsy一覧は以下になっている。

|  値  |  型  |  説明  |
| --------- |--------- |--------- |
|  null  |  null  |  キーワード null : 値が存在しないことを示します。  |
|  undefined  |  undefined  |  undefined :プリミティブ値。  |
|  false  |  論理値型  |  	キーワード false。  |
|  NaN  |  数値型  |  NaN : 数値ではない  |
|  0  |  数値型  |  数値ゼロ （従って、 0.0 や 0x0 なども含みます）。  |
|  -0  |  数値型  |  長整数型のゼロ（従って、 0x0n も含みます）。なお、長整数型にはマイナスゼロはありません。 0n の負の数は 0n です。  |
|  ""  |  	文字列型  |  空文字列値。'' や `` も含みます。  |
|  document.all  |  	オブジェクト  |  JavaScript で唯一の偽値のオブジェクトは、組み込みの document.all です。  |

URL:https://developer.mozilla.org/ja/docs/Glossary/Falsy

## 論理演算子

基礎は以下。

```js
ok = true && false;
console.log(ok); // false
ok = true || false;
console.log(ok); // true
```

応用的な考えは以下。

論理積演算子：
- 左側がTruthyであれば、右側の値を返す。
- 左側がFalsyであれば、左側の値を返す。

```js
ok = 'hello' && 'ok'; // ok
ok = 0 && 'ok'; // 0(Falsyのため)
```

論理和演算子：
- 左側がTruthyであれば、左側の値を返す。
- 左側がFalsyであれば、右側の値を返す。

```js
ok = 'hello' || 'ok'; // hello
ok = '' || 'ok'; // ok
```

上記のコードはユーザがユーザ名を入力しない時などに使える。

```js
const userName = inputUser || 'sampleName';
```