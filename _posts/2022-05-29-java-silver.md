---
layout: post
title: Java Silver
author: taku
date: 2022-05-29 17:00
last_modified_at: 2022-06-01 15:33
tags: [Java, Certification]
toc:  true
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