---
title: "Hugoでサイトを作成してみた"
date: 2022-06-26T13:43:48+09:00
summary: "本サイトを作成した背景やメモです。本サイトはHugoを用いて作成しGitHub Actionsによる自動デプロイを行っています。"
tags: ["動作環境あり", "Hugo", "GitHub Actions"]
---

## 作成時期
2022年7月

## 背景
これまで、個人ブログの中で趣味で作成したものも投稿をしていました。  
今後軽い内容のブログの投稿を増やそうと思うにあたり、ものづくりをしたものは別で管理したほうがよいと考え、本サイトを作成しました。

## 作成物
[本サイト](https://portfolio.bellshun.com/)です。

## 実現方法
ブログ同様、Hugoを利用しました。  
一方これまではコンテナ内にHugo環境を作成していたことから、ブログ投稿するたびにコンテナを立ち上げるなどの手間がありました。  
そこでローカル環境に用意し、GitHub Actionsを利用して、デプロイを自動化しました。

## 環境
- Hugo： v0.101.0
- Hugo Theme： [GitHub Style](https://github.com/MeiK2333/github-style)

## 導入
### Hugo
[Hugoインストール](https://gohugo.io/getting-started/installing/)  
WSL内のUbuntuを利用しているため、上記ページのDebian and Ubuntuを参照。  
最新のバージョンを取得するために、[公式](https://github.com/gohugoio/hugo/releases)のLatestバージョンのdebパッケージをダウンロードしてインストールしました。

```shell
$ wget https://github.com/gohugoio/hugo/releases/download/v0.101.0/hugo_0.101.0_Linux-64bit.deb
$ sudo apt install ./hugo_0.101.0_Linux-64bit.deb
```

### GitHub Actions
[こちら](https://github.com/peaceiris/actions-hugo)にすでにHugo用のGitHub Actionsが用意されていたので、記載の通りに設定しました。  
行ったことは以下のみです。
- プロジェクト直下に`.github/workflows/gh-pages.yml`を作成
- mainブランチが対象だったので、masterブランチをmainブランチに名称変更
- リポジトリのSettingからGitHub PagesのSourceブランチを`gh-pages`に変更する
{{< figure src="/images/hugo/source-branch.png" width="400" height="80">}}