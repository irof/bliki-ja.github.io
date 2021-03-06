---
layout: pofeaa
title: フロントコントローラ
---

原文: http://www.martinfowler.com/eaaCatalog/frontController.html

*Webサイトへの全てのリクエストを扱うコントローラ*

解説の全文は『PofEAA』 **344** ページを参照。

![](http:img/frontController-sketch.gif)

複雑なWebサイトでリクエストを扱うとき、よく似たことを何度も行う必要がある。
セキュリティだったり、国際化だったり、ユーザー別のビュー作成だったり。
インプット
コントローラの振る舞いがあちこちのオブジェクトに散らばっていたら、
こういった処理は重複してしまう。
それに、実行時に処理を変更するということが難しくなる。

FrontControllerでは、
ハンドラーオブジェクトをひとつ使ってリクエストを送り届ることで、
全てのリクエストを取り扱う。
このオブジェクトは共通の振る舞いを実行する。
この振る舞いは、デコレータを使うことで実行時に変更が可能だ。
ハンドラーはコマンド
オブジェクトにディスパッチして、リクエストごとの処理を行わせる。
