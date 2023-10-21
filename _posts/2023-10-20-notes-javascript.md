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