# README

## セットアップ

サイト作成

```shell
hugo new site hugo-swift
```

レポジトリ初期化

```shell
cd hugo-swift
git init
echo '*~' >> .gitignore
echo '*.bak' >> .gitignore
echo '*.orig' >> .gitignore
echo '.env' >> .gitignore
echo 'public' >> .gitignore
echo 'resources' >> .gitignore
```

テーマ設定

```shell
git submodule add https://github.com/onweru/hugo-swift-theme.git themes/swift
```

サイト設定

```shell
cp -pr themes/hugo-swift-theme/exampleSite/{content,data,config.toml} .
```

config.toml

```toml
baseURL = "https://higebobo.github.io/hugo-swift/"
languageCode = "en-us"
defaultContentLanguage = "ja"
title = "Hugo Swift"
theme = "hugo-swift-theme"
```

> github pagesやnetlifyで使う場合はbaseURLのプロトコルはhttpsにすること

起動確認(http://localhost:1313)

```shell
cp /path/to/someplace/Makefile .
make run
```

Githubレポジトリ作成後

```shell
cp -pr /path/to/someplace/.github .
git remote add origin git@github.com:higebobo/hugo-swift.git
git add .
git commit -m 'init'
git push -u origin master
```

## Github Actionsの利用

* .github/workflows/gh-pages.yamlを作成
    * ソースはmasterブランチ
    * 出力はpublicフォルダの内容をgh-pagesブランチ

```shell
make deploy
```

* Github>Settings>Gighub Pages>Source>gh-pages branchに設定する
* しばらく時間がかかる

## 既存のレポジトリからクローンする場合

```shell
git clone git@github.com:higebobo/hugo-swift.git higebobo-swift
cd higebobo-swift
git submodule update --init --recursive
```

## 使い方

### 投稿

新規投稿

```shell
hugo new post/hello.md
content/post/hello.md created
```

編集

```shell
vi content/posts/hello.md
```

## Link

* [Hugo Swift Theme \| Hugo Themes](https://themes.gohugo.io/hugo-swift-theme/)
