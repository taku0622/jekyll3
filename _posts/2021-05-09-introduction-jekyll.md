---
layout: post
title: jekyllテーマを使ってWebサイトを簡単に構築する(メモ)
date: 2021-05-09 16:00
tags: [jekyll theme, jekyll, tutorial]
toc:  true
---

こんにちは

今回はRubyの静的webサイト作成ジェネレーター **「Jekyll」** の使い方を紹介する。
[この記事](https://qiita.com/madoreenu/items/b47833bf785562c77819)が見れない場合こちらを参考にしてほしい。

## jeykllテーマを見つける

以下のリンクなどから、自分が作りたいものに合うテーマを探す。

- [jamstackthemes.dev](https://jamstackthemes.dev/ssg/jekyll/)
- [jekyllthemes.org](http://jekyllthemes.org/)
- [jekyllthemes.io](https://jekyllthemes.io/)
- [jekyll-themes.com](https://jekyll-themes.com/)

見つけたら、ダウンロードし展開。自分が置きたいフォルダに展開したファイルを置いておく。

## githubでレポジトリ作成

題のまんまだが、githubにて新規レポジトリを作る。その際、注意してほしいことがある。

githubのレポジトリ名はここで作る静的サイトのurlに含まれるので、より短く、用途に合った名前が好ましい。。

また、ブランチはmasterで作業してよい。以前はgh-pagesとか必要だったとかなかったとか。

## (省略可)bunder jekyllの導入

はじめて作る場合は、rubyに以下のgemをインストールする必要がある。

```
$ gem install jekyll bundler
```

## セットアップ(レポジトリ作成の前にやってもいいよ)

テーマを決め、レポジトリを作成しgithubの設定を行ったら、セットアップできるか確認。

```
$ bundle install
```

をし、サイトをローカルで立ち上げる。

```
$ bundle exec jekyll serve
```

ここで出力されているリンクを開くことで確認できる。

もし表示されない等の不具合があれば、テーマを変更した方が良いよ。いっぱいテーマあるから。。

## github pagesで確認

github pagesでテーマを観ることができるか確認する。

githubのレポジトリページに行き(以下のリンクを参考に)、ブランチをmasterに設定する。

リンク例：

***https://github.com/taku0622/(レポジトリ名)/settings/pages***

設定し終わって、数分したら、確認する

リンク例：

***https://taku0622.github.io/(レポジトリ名)***

これで確認できたら、内容を変更していく。あとは、どんな感じで変更できるかは、テーマによって違うが、直感的に理解できると思われる。

また、これで、確認できない場合は、先ほど同じように、テーマを変更した方が良いと思う。

## 最後に

ということで、今回はJekyllの導入方法をざっくり紹介しました。