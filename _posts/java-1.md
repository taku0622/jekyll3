---
layout: post
title: Java
author: taku
date: 2021-04-04 18:30
tags: [Java]
---

## HelloWorld.javaの実行の流れ

- 1.ソースプログラム
テキストエディタ等でプログラムを書く
HelloWorld.java

```java
public class HelloWorld {
    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        // TODO code application logic here
        System.out.println("hello world");
    }
}
```

- 2.コンパイル
コンパイラ(javac)を起動する
javac Hello