---
title: "しりとりアプリを作ってみた"
date: 2022-04-02T08:40:42Z
summary: "Nuxt.js×Docker×Herokuで複数人で楽しめるしりとりアプリを作りました。リモート飲み会などで気軽に楽しむことができます。"
tags: ["動作環境あり", "スライドあり", "Nuxt", "Docker"]
---

## 作成時期
2022年3月

## 背景
Nuxt.jsの学習の一環で作成しました。  
ついでに身内のリモート飲み会などで気軽にちょっとした遊びができたらいいなという思いもあり作成しました。

## 当初想定していた構成図や機能について
[スライド](https://shiritori.bellshun.com)を作成しています。  
※ ExpressをAPIとして利用していなかったり、DBや辞書判定部分が未実装という点で差異があります。

## 成果物
[しりとりWebアプリ](https://shiritori-front.herokuapp.com/chat)  
※ herokuの無料枠の為、接続が不安定なことがあります。また、初回起動時に立ち上がるまでに時間がかかります。  
{{< figure src="/images/shiritori/shiritori-demo.png" class="center" >}}

## 今後やりたいこと
時間があれば以下もやってみたいと思っています。
- TypeScriptによる静的型付け
- Vue3(Composition API)を使った記法にリファクタリング
- 辞書判定機能の追加