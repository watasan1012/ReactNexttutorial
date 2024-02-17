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

## 環境構築が終わったか確認する

```sh
% node -v
```
v20.11.1

```sh
% npm -v
```
10.2.4

```sh
% npx -v
```
10.2.4



## Next.jsに触れる



1. プロジェクトの作成

- ターミナルを起動し、以下のコマンドを実行する


```sh
$ npx create-next-app@latest
```

```
create-next-app@14.1.0
Ok to proceed? (y)
```

y キー　エンターキーの順にクリック

```
? What is your project named? › my-app
```

作成するプロジェクトの名前を入力する

sample-next-project

```sh
? Would you like to use TypeScript? › No / Yes
```

Yes

```sh
? Would you like to use ESLint? › No / Yes
```

Yes

```
? Would you like to use Tailwind CSS? › No / Yes
```

Yes

```
? Would you like to use `src/` directory? › No / Yes
```

Yes

本業　css in js

```
? Would you like to use App Router? (recommended) › No / Yes
```

Yes

```
? Would you like to customize the default import alias (@/*)? › No / Yes
```

No

プロジェクトの作成が起動する

Success! Created sample-next-project at /Users/ユーザーディレクトリ/作業ディレクトリ/sample-next-project

が表示されたら完成です。

作業ディレクトリに移動します。

```sh
% cd sample-next-project
```

サーバーを起動する

```sh
 % npm run dev
```

ブラウザーからプロジェクトができたか確認する

以下リンクを表示する
```
http://localhost:3000/
```

## Hello world を表示してみよう！

sample-next-project ディレクトリをVS Code で表示する

sample-next-project/src/app にある、page.tsx　ファイルを編集する

32行目から39行目を削除し、「Hello world」とします。

```
        <Image
          className="relative dark:drop-shadow-[0_0_0.3rem_#ffffff70] dark:invert"
          src="/next.svg"
          alt="Next.js Logo"
          width={180}
          height={37}
          priority
        />
```

以下に変更

```
<div className="relative クラス名は多いので記述上省略>
Hello world
</div>
```

/src/app
├── favicon.ico
├── globals.css
├── layout.tsx
└── page.tsx

globals.css 全体のデザイン設定を行うファイル。

layout.tsx　複数のページで共有されるUIコンポーネント。

page.tsx ルートーページの固有なUIコンポーネント

 * 【参考リンク】[https://nextjs.org/docs/app/building-your-application/routing/pages-and-layouts](https://nextjs.org/docs/app/building-your-application/routing/pages-and-layouts)

(補足)TailwindCSSについて

メリット
  ・ CSSのクラス名を考えなくてよい
  ・ CSSの管理が楽になる

デメリット
  ・ CSSのコーディングを忘れてしまう
  ・　クラス名が長くなり、可読性が下がってしまう

* 【参考リンク】　【公式ドキュメント】　[https://tailwindcss.com/docs/installation](https://tailwindcss.com/docs/installation)
* 【参考リンク】　[https://reffect.co.jp/html/tailwindcss-for-beginners](https://reffect.co.jp/html/tailwindcss-for-beginners)


