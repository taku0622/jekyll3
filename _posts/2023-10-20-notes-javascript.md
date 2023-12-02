---
layout: post
title: JavaScript
author: taku
date: 2023-10-20 0:00
last_modified_at: 2023-10-20 1:15
tags: [js]
toc: true
---

Notes JavaScript👀🦴

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
const inputUser = ''
const userName = inputUser || 'sampleName'; // sampleName
```

### Null合体演算子(Nullish Coalescing)

論理和演算子に似ているが、
- 左側が **Truthy, 空文字**であれば、左側の値を返す。
- 左側が **Null, undefined** であれば、右側の値を返す。
- AND演算子やOR演算子と一緒に使えない。※括弧を使えば、使用可能。

```js
let user = '' ?? 'Taro'; // 空文字を返す
```

## Loop

### for-of文

```js
const fruits = ['apple', 'banana', 'grape', 'orange', 'mango'];
for (const fruit of fruits) {
  console.log(fruit);
}
```

for文内でconstが使われている。
const fruit = fruits[i]が要素数毎に宣言されているイメージ。


iterableなオブジェクトで使用可能。(※iterable:反復可能)

### for-in文

```js
const coffee = {
  name: 'Caffe latte',
  size: 350,
  isHot: true,
};
for (const key in coffee) {
  console.log(coffee[key]);
}
```

for-in文はオブジェクトに使う。
また、for-of同様、配列にも使える。

```js
const fruits = ['apple', 'banana', 'grape', 'orange', 'mango'];
for (const key in fruits) {
  console.log(fruits[key]);
}
```

### label文

複数ネストから抜け出す時に使う。
labelとbreakを1組で使う。

ブロック、if、for文で使用可能。

分かりにくいので、一般的にはあまり使われない。

```js
const coffee = {
  name: 'Caffe latte',
  size: 350,
  isHot: true,
};
coffeepoint: if (true) {
  for (const key in coffee) {
    if (key === 'size') {
      console.log('break!!');
      break coffeepoint;
    }
    console.log(key);
    console.log(coffee[key]);
  }
}
```

実行結果
```
name
Caffe latte
break!!
```

## 関数

関数とはオブジェクトであり、変数(関数名)に代入している。

つまりオブジェクトのように扱える。

```js
function add(a, b) {
  return a + b;
}
console.log(add); // オブジェクトが返ってくる
console.log(add.name); // add
console.log(add.length); // 2 ※引数の数
const newAdd = add; // オブジェクトの代入
console.log(newAdd(3, 4)); // 7
```

functionから始まるものを **関数宣言文** (関数オブジェクトを作成 + 変数(let)addを作り代入している)

また、関数宣言文だけでなく、**関数宣言、関数文、Function文** ともいう。

### 関数式

自分解釈：関数オブジェクトを明示的に変数に入れたもの。

```js
const sayHi = function hi() { // 名前付き関数
  return "hi"
}
const sayHello = function () {  // 無名関数 
  return "hello"
}
console.log(sayHi());     // hi
console.log(sayHello());  // hello
console.log(hi());        // エラーになる。
```

### 関数宣言文 vs 関数式

関数宣言文：巻き上げられる。→宣言箇所よりも上の位置で呼んでも実行できる。

関数宣言文：巻き上げられない。→宣言箇所よりも上の位置で呼ぶと実行できない。

```js
console.log(add(8, 9)); // 17 ※実行可能
function add(a, b) {
  return a + b;
}

console.log(sayHi());     //  実行できない　参照エラー
const sayHi = function hi() {
  return "hi"
}
```

|  | メリット  |
| --------- | ----- |
|  関数宣言文 | どこでも使える、(文頭がfunctionなので)わかりやすい|
|  関数式  |  必ず呼び出し式の上に定義されている、constを使える(上書き不可能)  |

どちらが良いかというのはないが、プロジェクト・プログラムの上で統一するのが良い。

### メソッド

オブジェクトのkey:valueのvalueに関数をいれた場合、その関数のことを **メソッド** という。

```js
const person = {
  name: "Taro",
  sayHi: function () {  // メソッド
    return "Hi"
  },
};
console.log(person.sayHi());  // Hi
```

### アロー関数

無名関数を簡単に書き換えたもの。

```js
const sayHiAnonymous = function (name) { // 無名関数
  return `Hi ${name} !`;
}
console.log(sayHiAnonymous('Taro'));  // Hi Taro !

const sayHiArrow = (name) => {       // アロー関数
  return `Hi ${name} !`;
}
console.log(sayHiArrow('Jiro'));  // Hi Jiro !
```

アロー関数のメリット 2点

1. 1つの式の場合は波括弧・returnを省略できる。

```js
const sayHiArrow = (name) => `Hi ${name} !`;
console.log(sayHiArrow('Jiro'));  // Hi Jiro !
```

※オブジェクトを返したい場合、丸括弧をつける
！！

```js
const person = (name) => ({
  name: name,
  age: 16,
});
console.log(person('Jiro').age);  // 16
```

2. パラメータが1つだけの場合、丸括弧を省略できる。

```js
const sayHiArrow = name => `Hi ${name} !`;
console.log(sayHiArrow('Jiro'));  // Hi Jiro !
```

### デフォルトパラメータ

引数に何も指定しないor引数に **undifined** 場合の値を指定する。

```js
const sayHiArrow = (name = 'anonymous') => `Hi ${name} !`;
console.log(sayHiArrow());  // Hi anonymous !
```

### レストパラメータ

残引数を配列としてまとめることができる。

```js
let sum = (a, b, ...nums) => {
  console.log('a: ' + a);             // a: 1
  console.log('b: ' + b);             // b: 2
  console.log('...nums: ' + nums);    // ...nums: 3,4,5,6
  let total = 0;
  for (num of nums) { total += num }
  return a + b + total;               // 21
}
console.log(sum(1, 2, 3, 4, 5, 6));
```

### コールバック関数

関数の引数に関数を入れることができる。

```js
let substract = (a, b, callback) => {
  let result = a - b;
  callback(result);
};
substract(4, 3, (result) => {
  console.log(result)           // 1
});
```

## JavaScriptについて

### 後方互換性

過去のコード・プログラムを現在でも使えるようにすること。

ネット引用：後方互換性とは、互換性（コンパチビリティ）の区分のうち、より新しい製品が既存の（古い）製品を扱うことができること。

### use strict

以前使用していた、緩いルール(スコープが大きいvar変数など)を使わせないようにして、厳しいルールでコードを書かせるもの。

後方互換性による不備やバグを発生させないようにするもの。

```js
grape = "grape";    // var let const を使わずに宣言・代入できてしまう
console.log(grape); // grape
```

```js
'use strict';
grape = "grape";
console.log(grape); // Uncaught ReferenceError: grape is not defined
```

use strictを使用することでルールが厳しくなる。

### primitive vs object(reference/参照型)

|  primitive  |  object  |
| --------- |--------- |
|  number  |  オブジェクト  |
|  string  |  配列  |
|  boolean  |  関数  |
|  undefined  |    |
|  null  |    |

表面上の理解

---

- primitive型

コード順番
1. let x = 8;
2. let x = 13;
3. x = y;

primitive型はxのメモリ領域に直接入れる。

メモリ領域内

x = 13

y = 13

---

- object型

コード順番
1. let x = {x:0};
2. let y = {y:0};
3. x = y;

object型はxのメモリ領域に参照できるアドレスを入れる。

メモリ領域内

x = 300(アドレス値を入れる)

y = 300(アドレス値を入れる)

200 = {x:0}  // 残ったまま(ガベージコレクターによって削除される)

300 = {y:0}

---


例）

```js
const coffee = {
  name: 'Caffe Latte'
};
const coffee2 = coffee;     // アドレス値の代入
coffee2.name = 'Espresso';
console.log(coffee.name);   // Espresso
```

**object型のconstは値が変化する。**
→ミュータブル(可変)

primitive型はイミュータブル(不可変)


## 発展的な関数

JavaScriptの関数は全てクロージャ。

クロージャ：外部の変数の情報を持った関数。

プライベート(変更が限られた)変数を作成することができる。

例1.カウンター）

```js
let createCounter = () => {
  let count = 0;
  return () => {
    count++;
    console.log(count);
  };
};
let counter = createCounter();
counter(); // 1
counter(); // 2
```

例2.人）個人的に、こちらについてはJavaなどのsetter, getterに近い印象。

```js
let genetatePerson = (name) => {
  let age = 0;
  return {
    getName: () => name,
    getAge: () => age,
    incrementAge: () => {
      age++;
    },
  };
};
const jiro = genetatePerson('Jiro');
console.log(jiro.getAge()); // 0
jiro.incrementAge();
jiro.incrementAge();
console.log(jiro.getAge()); // 2
console.log(jiro.getName());// Jiro

const tom = genetatePerson('Tom');
tom.incrementAge();
tom.incrementAge();
tom.incrementAge();
console.log(tom.getAge());  // 3
```

### 再帰関数

```js
let factorial = (n) => {
  if (n === 0) return 1;
  return n * factorial(n - 1);
}
console.log(factorial(3)); // 6
console.log(factorial(5)); // 120
console.log(factorial(0)); // 1

// 省略
let factorial2 = (n) => n === 0 ? 1 : n * factorial2(n - 1);
```

## Object

### key

すべてのオブジェクトのキーは文字列で(内部的に)管理されている。

```js
const interests = 'interests';
const person = {
  name: 'John',
  age: 30,
  greeting: () => hello,
  const: 'const',                     // 予約語
  'current city': 'Tokyo',            // 文字列
  3: 3,                               // 数値
  3.1: 3.1,                           // 小数
  '-4': -4,                           // 負は文字列のみ
  [interests]: ['music', 'travel'],   // 変数
};
console.log(person.name);       // John
console.log(person['name']);    // John
console.log(person.greeting);   // hello
console.log(person['greeting']);// hello
console.log(person.const);      // const
console.log(person['const']);   // const
console.log(person['current city']); // Tokyo
console.log(person['3']);       // 3
console.log(person[3]);         // 3
console.log(person[3.1]);       // 3.1
console.log(person['3.1']);     // 3.1
console.log(person[interests]); // ['music', 'travel']
```

### お便利関数

```js
const interests = 'interests';
const person = {
  name: 'John',
  age: 30,
  greeting: () => hello,
  const: 'const',                     // 予約語
  'current city': 'Tokyo',            // 文字列
  3: 3,                               // 数値
  3.1: 3.1,                           // 小数
  '-4': -4,                           // 負は文字列のみ
  [interests]: ['music', 'travel'],   // 変数
};
// key一覧：['3', 'name', 'age', 'greeting', 'const', 'current city', '3.1', '-4', 'interests']
console.log(Object.keys(person));
// value一覧：[3, 'John', 30, ƒ, 'const', 'Tokyo', 3.1, -4, Array(2)]
console.log(Object.values(person));
// key&valueが配列で一覧：[[key, value],[key, value],[key, value]...]
console.log(Object.entries(person));
```

### Object property

```js
const interests = 'interests';
const person = {
  name: 'John',
  age: 30,
  greeting: () => hello,
  const: 'const',                     // 予約語
  'current city': 'Tokyo',            // 文字列
  3: 3,                               // 数値
  3.1: 3.1,                           // 小数
  '-4': -4,                           // 負は文字列のみ
  [interests]: ['music', 'travel'],   // 変数
};
person.name = 'Taku'; // 値変更
person.gender = 'man' // 値追加
delete person.age;    //  property(age)削除
```

```js
// propertyの省略
const name = 'Espresso';
const size = 350;
const coffee = {
  name,
  size,
};
console.log(coffee);
```

### スプレット構文

オブジェクトは===でつなげるとアドレスを共有する参照型だが、
以下のコードではオブジェクトをコピーして別アドレスに保存する。

```js
const name = 'Espresso';
const size = 350;
const coffee = {
  name,
  size,
};
const coffee2 = {
  ...coffee,        // スプレット構文：オブジェクト自体をコピー
  name: 'Latte',    // 後に書けば上書き
};
console.log(coffee2); // {name: 'Latte', size: 350}
```

また、シャロ―コピー(浅いコピー)であり、オブジェクトの中にオブジェクトがある場合、浅いオブジェクトしかスプレット構文の対象ではない。

対策

```js
const name = 'Espresso';
const size = 350;
const coffee = {
  name,
  size,
  nutritions: {
    calories: 5,
    suger: 0,
  }
};
const coffee2 = {
  ...coffee,
  name: 'Latte',
  nutritions: {
    ...coffee.nutritions
  },
};
coffee2.nutritions.calories = 180;
console.log(coffee); // 値が上書きされない
```

### Object.assign

オブジェクトのマージ

```js
const o1 = { a: 1 };
const o2 = { b: 2 };
Object.assign(o1, o2);  // o1に結合される
console.log(o1);        // {a: 1, b: 2}
```

また以下のように書くとスプレット構文と同じ挙動になる。

```js
const newCoffee = Object.assign({}, coffee);
```

### 分割代入

```js
const book = {
  title: 'JavaScriptBook',
  price: 9.99
}
// const title = book.title;      // 通常の代入
// const price = book.price
const { title, price } = book;    // 分割代入：挙動は一緒
console.log(title, price);        // JavaScriptBook 9.99
```

応用1：別名をつける

```js
const book = {
  title: 'JavaScriptBook',
  price: 9.99
}
const { title: bookTitle } = book; 
console.log(bookTitle);  // JavaScriptBook
```

応用2：オブジェクトのオブジェクト

```js
const book = {
  title: 'JavaScriptBook',
  price: 9.99,
  auther: {
    first: 'Michael',
    last: 'Jordan'
  },
}
const { title, auther: { last } } = book;
console.log(last);  // Jordan
```

応用3：デフォルト値

```js
const book = {
  title: 'JavaScriptBook',
  price: 9.99,
  auther: {
    first: 'Michael',
    last: 'Jordan'
  },
}
const { title, auther: { last }, publisher = 'NBA' } = book;
console.log(publisher);  // NBA
```

応用4：取得してない値をオブジェクトで取得

```js
const book = {
  title: 'JavaScriptBook',
  price: 9.99,
  auther: {
    first: 'Michael',
    last: 'Jordan'
  },
  isbn: 1234567890,
}
const {
  title,
  auther: { last },
  publisher = 'NBA',
  ...etc
} = book;
console.log(etc);  // {price: 9.99, isbn: 1234567890}
```

応用5:関数パラメータとして使う

```js
const book = {
  title: 'JavaScriptBook',
  price: 9.99,
  auther: {
    first: 'Michael',
    last: 'Jordan'
  },
  isbn: 1234567890,
}
const sayBook = ({
  title,
  price,
  publisher = 'NBA',
  ...etc
}) => {
  console.log(price); 
};
sayBook(book); // 9.99
```

### in演算子

オブジェクトにプロパティがあるか返す演算子。

```js
const book = {
  title: 'JavaScriptBook',
  price: 9.99,
  auther: {
    first: 'Michael',
    last: 'Jordan'
  },
  isbn: 1234567890,
};
console.log('title' in book); // ture
if (book.title !== undefined) console.log(true); // この挙動とほとんど一緒
```

### オプショナルチェインニング

```js
const book = null;
// bookがnull, undefinedなら、undefined
// bookがあれば、値を返す 
console.log(book?.title); // undefined
console.log(book?.()); // 関数オブジェクト：undefined
console.log(book?.['title']); // []の参照：undefined
```

### this

値を自動で割り当てる。

- 一番浅いレキシカル環境でthisを使用した場合、グローバルオブジェクトが呼ばれる。

- 無名関数内でthisを使用した場合、グローバルオブジェクトが呼ばれる。ただし、**use strict** 使用時はundefinedになる。

- メソッドで使用した場合、メソッドのオブジェクトが呼ばれる。ただしアロー関数ではthisはグローバルオブジェクトが呼ばれる。

```js
const car = {
  color: 'red',
  changeColor: function (color) {
    this.color = color;
  }
}
car.changeColor('white');
console.log(car.color);
```

### apply & call

thisの内容を強制的に割り当てる。ただし、アロー関数では使えない。

```js
sayThis = function (a, b) {
  console.log(this, a, b);
}
sayThis.call({ hello: 'hello' }, 1, 2);    // {hello: 'hello'} 1 2
sayThis.apply({ hello: 'hello' }, [1, 2]); // {hello: 'hello'} 1 2
```

### bind

thisの内容を強制的に縛る(call, applyよりも強い)。ただし、アロー関数では使えない。

```js
sayThis = function (a, b) {
  console.log(this, a, b);
};
sayThis = sayThis.bind({ hello: 'hello' }, 1, 2);
sayThis();  // {hello: 'hello'} 1 2
```

### メソッドの省略化

メソッドでは、thisを使いやすいようにアロー関数は使わないようにする。

ただ、毎回functionを書くのは冗長化してしまうため、以下の記載方法がある。

```js
const car = {
  color: 'red',
  changeColor(color) { // キーを書かずにメソッド名から書く
    this.color = color;
  }
}
```
