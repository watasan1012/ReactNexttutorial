# ReactNext-tutorial

uchiさんのReactNext入門に参加

## 第一回目次

* Next.jsとは
* 開発環境について
* Next.jsに触れる
* デプロイをしよう
* プロフィールページの作成
* Todoアプリ作成
* (おまけ)今後に向けて

## Next.jsとは

Vercel社が開発したWeb アプリを構築できる React Framework
React Components を使用してUIを構築できる

## 機能特徴

ルーティング：ページのルーティング機能
レンダリング：SSR、SSGなどのレンダリング機能
データの取得：サーバサイドコンポーネントのデータフェッチ機能
スタイリング：Tailwind CSS、CSS-in-JS等のサポート機能
etc…

【参考】
[https://nextjs.org/docs#how-to-use-these-docs](https://nextjs.org/docs#how-to-use-these-docs)

## 開発で使用する言語

* HTML
 * 【参考リンク】　[https://creatorquest.jp/lessons/html/](https://creatorquest.jp/lessons/html/) 
* CSS
 * 【参考リンク】[https://creatorquest.jp/lessons/css/css-intro/](https://creatorquest.jp/lessons/css/css-intro/)
* JavaScript
  * Typescript TypeScript は、JavaScript に基づいて構築された厳密に型指定されたプログラミング言語。ページ内の動作、処理を作る。
  * 【参考リンク】　[https://www.typescriptlang.org/](https://www.typescriptlang.org/)
  * 【参考リンク】　[https://typescriptbook.jp/reference](https://typescriptbook.jp/reference)
 
## 開発環境について

パソコンに環境を構築する

 * Node.jsのインストール
  * Windows 
   * 【参考リンク】 React.jsの環境構築・windows編　[https://zenn.dev/kagetugu/articles/eec07c364f9153](https://zenn.dev/kagetugu/articles/eec07c364f9153)
  * macOS
   * 【参考リンク】 nodebrewを使ってReact環境構築 [https://zenn.dev/shohei_1010/articles/f1ef4454202da7](https://zenn.dev/shohei_1010/articles/f1ef4454202da7)

 * GitHub
  * 【参考リンク】[https://github.com/signup](https://github.com/signup)

 * vercel
  * vercelとは、ホスティングのPaaSです。
  * Github等のリポジトリと連携させるだけで、簡単にデプロイできます。
  * 【参考リンク】　[https://vercel.com/](https://vercel.com/)

 * Supabase
  * Supabaseとは、データベースでBassです。

## 開発環境を確認する

Node.js

```sh
% node -v
```
v18.18.0

Latest LTS Version: 20.11.1

```sh
% brew upgrade
```

問題を確認する

```sh
% brew doctor
```

homebrewでインストールしたパッケージを確認する

```sh
% brew list
```
nodenvでnode.jsをインストールしたことがわかります。

インストール可能なnodeの一覧を表示する

```sh
% nodenv install --list
```

Node.jsをインストールする

```sh
% nodenv install 20.11.1
```

パッケージの更新

```
% nodenv rehash
```

インストールしたnode.jsのバージョンを確認する

```sh
% nodenv versions
```

利用するnode.jsのバージョンを指定する

```sh
% nodenv global 20.11.1
```

ダウンロードしたNode.jsのバージョンを確認する

```sh
% nodenv versions
```

不要なnode.jsのバージョンを削除する

```sh
% nodenv uninstall 18.18.0
```
nodenv: remove /Users/hirotaka/.nodenv/versions/18.18.0? [yN] 

yキーエンター


## Next.jsに触れる



1. プロジェクトの作成

- ターミナルを起動し、以下のコマンドを実行する


```sh
$ npx create-next-app@latest
```


3. 

