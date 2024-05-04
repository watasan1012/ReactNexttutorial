# ReactNext-tutorial

uchiさんのReactNext.js入門に参加

45分　集中 10分休憩　ポモドーロ　テックニックを使ったやり方

## 第一回目次

* Next.jsとは
* 開発環境について
* デプロイするための環境構築する
* Next.jsに触れる
* プロフィールページの作成
* デブロイをしてみよう!
* Todoアプリ作成
* (おまけ)今後に向けて

## Next.jsとは

Vercel社が開発したWebアプリを構築できる React Framework
React Components を使用してUIを構築できる

## 機能特徴

ルーティング：ページのルーティング機能
レンダリング：SSR、SSGなどのレンダリング機能
データの取得：サーバサイドコンポーネントのデータフェッチ機能
スタイリング：Tailwind CSS、CSS-in-JS等のサポート機能
etc…

【参考】
[https://nextjs.org/docs#how-to-use-these-docs](https://nextjs.org/docs#how-to-use-these-docs)

### 開発で使用する言語

* HTML
 * HTML(HyperText Markup Language、ハイパーテキスト・マークアップランゲージ)は、ウェブサイトのコンテンツの構造を作るために使うコード。ページ内の表示を作る。
 * 【参考リンク】　[https://creatorquest.jp/lessons/html/](https://creatorquest.jp/lessons/html/)
* CSS
 * CSS (Casgading Style Sheets)は、ウェブページのスタイルを設定するコード。ページ内のデザインを作る。
 * 【参考リンク】 [https://creatorquest.jp/lessons/css/css-intro/](https://creatorquest.jp/lessons/css/css-intro/)
 * 【参考リンク】 [https://www.webcreatorbox.com/tech/css-flexbox-cheat-sheet](https://www.webcreatorbox.com/tech/css-flexbox-cheat-sheet)
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
  * 【参考リンク】 [https://github.com/signup](https://github.com/signup)
  * 事前にGitHubアカウントを作成してください。

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
v20.12.2

Latest LTS Version: v20.12.2

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
% nodenv install 20.12.0
```

パッケージの更新

```sh
% nodenv rehash
```

インストールしたnode.jsのバージョンを確認する

```sh
% nodenv versions
```

利用するnode.jsのバージョンを指定する

```sh
% nodenv global 20.12.0
```

ダウンロードしたNode.jsのバージョンを確認する

```sh
% nodenv versions
```

不要なnode.jsのバージョンを削除する

```sh
% nodenv uninstall 20.11.1
```
nodenv: remove /Users/hirotaka/.nodenv/versions/18.18.0? [yN] 

yキーエンター

## 環境構築が終わったか確認する

```sh
% node -v
```
v20.12.2

```sh
% npm -v
```
10.5.0

```sh
% npx -v
```
10.5.0

## デプロイするための環境構築する

### Vercel とは

フロントエンド開発のプラットフォームで、デプロイ環境を提供する。

[参考サイト](https://dev-harry-next.com/infrastructure/vercel-detail)

### Vercelのアカウントを作成する

[Vercelsignup](https://vercel.com/signup) をブラウザーから開く。

タイトル　Create Your Vercel Account　が表示されたら、Plan Type を選択します。

```
Plan Type
├── Hobby  
     I'm working on personal projects  
     Hobby plan  
     無料　(従量課金なし)  
└── Pro  
     I'm working on commercial projects  
     Pro plan  
     $20  
```

Plan Type　から Hobby を選択します。

Your Name → あだ名でもOK あだ名を入れて

Continue ボタンをクリックします。

・ Let's connect your Git provider 画面が表示

Continue with　GitHub　ボタンをクリックします。

・ Authorize Vercel 画面が表示

Vercel by Vercel would like permission to:
GitHubへのアクセス許可が求められるので、問題なければ 

緑色の　Authorize Vercel　ボタンをクリックします。

Authenticating - Vercel 

Verification

Please enter your phone number to verify your login. You will receive a single use code to submit.

ログインを確認するために電話番号を入力してください。1回だけ使用できるコードが送信されます。

自身が所有する電話番号を入力して

一度、日本を選びます。そのあと、自動で入力された81を消して自分の電話番号を入力する

Continue ボタンをクリックしてください。

Verification 画面が表示されます。

A code has been sent to +81 000 1234 5678.
Enter it below to complete your sign up.

入力した電話番号に4桁の数字がSMSで届くので入力する。

Vercelのアカウントが作成されました。

左側上部のVercel　ロゴをクリックするかVercelにログインする

[https://vercel.com/login](https://vercel.com/login)

## Next.jsに触れる

### プロプロジェクトの作成 1

- ターミナルを起動し、以下のコマンドを実行する

```sh
% npx create-next-app@latest
```

```result
Need to install the following packages:
create-next-app@14.2.3
Ok to proceed? (y) 
```

y キー　エンターキーの順にクリック

```result
? What is your project named? › my-app
```

my-app の部分に、作成するプロジェクトの名前を入力する

sample-next-project

### ? TypeScriptを使いたいですか？いいえ / はい

```sh
? Would you like to use TypeScript? › No / Yes
```

矢印キーでカーソルを変更できます。アンダースコアがあるほうが選択状態です。
enterキーで確定です。

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

```
? Would you like to use App Router? (recommended) › No / Yes
```

Yes

```
? Would you like to customize the default import alias (@/*)? › No / Yes
```

No

プロジェクトの作成が起動する

```
Success! Created sample-next-project at /Users/ユーザーディレクトリ/作業ディレクトリ/sample-next-project
```

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

[http://localhost:3000/](http://localhost:3000/)

### Hello world を表示してみよう！

sample-next-project ディレクトリを VS Code で表示する

sample-next-project/src/app にある、page.tsx　ファイルを編集する

```
sample-next-project/src/app
├── favicon.ico
├── globals.css
├── layout.tsx
└── page.tsx
```

32行目から39行目を削除し、「Hello world」とします。

```
      <div className="relative z-[-1] ">
        <Image
          className="relative dark:drop-shadow-[0_0_0.3rem_#ffffff70] dark:invert"
          src="/next.svg"
          alt="Next.js Logo"
          width={180}
          height={37}
          priority
        />
      </div>
```

以下に変更

```
<div className="relative クラス名は多いので記述上省略>
Hello world
</div>
```

### 各ファイルの説明

```
sample-next-project/src/app
├── favicon.ico
├── globals.css
├── layout.tsx
└── page.tsx
```

globals.css 全体のデザイン設定を行うファイル。

layout.tsx　複数のページで共有されるUIコンポーネント。

page.tsx ルートーページの固有なUIコンポーネント

 * 【参考リンク】 [https://nextjs.org/docs/app/building-your-application/routing/pages-and-layouts](https://nextjs.org/docs/app/building-your-application/routing/pages-and-layouts)

### (補足)TailwindCSSについて

メリット
  ・ CSSのクラス名を考えなくてよい
  ・ CSSの管理が楽になる

デメリット
  ・ CSSのコーディングを忘れてしまう
  ・　クラス名が長くなり、可読性が下がってしまう

* 【参考リンク】　【公式ドキュメント】　[https://tailwindcss.com/docs/installation](https://tailwindcss.com/docs/installation)
* 【参考リンク】　[https://reffect.co.jp/html/tailwindcss-for-beginners](https://reffect.co.jp/html/tailwindcss-for-beginners)

## 再度ローカルサーバーを起動してhello worldを確認する

ターミナルから

```sh
% npm run dev
```

ブラウザーから、[http://localhost:3000/](http://localhost:3000/) を開いて確認する。

Hello world　が表示されたら完了です。

## Vercelでデブロイをしてみよう!

### デプロイ手順

1. プロジェクトをGithubにpushする
2. Vercelにログインする
3. Vercelからプロジェクトを選択してDeployする










ログインしていた場合は、 左上のアカウント名 projects をクリックします。

Deploy your first project　画面が表示されます。

Start with one of our templates or create something new.

私たちのテンプレートのいずれかを使用して開始するか、新しい何かを作成します。

リストから、Next.js App and a Serverless Function API 横の Deploy をクリックします。

Create Git Repository　 画面

To ensure you can easily update your project after deploying it, a Git repository must be created. Every push to that Git repository will be deployed automatically.

デプロイ後にプロジェクトを簡単に更新できるようにするには、Git リポジトリを作成する必要があります。そのGitリポジトリへのプッシュはすべて自動的にデプロイされます。

Git Scope の Select Git Scope というセレクトボックス　を選択して Select Git Scope から　Add GitHub Account　を選択します。

Install Vercel　画面が表示されるので

Where do you want to install Vercel?

インストール先のGitHubアカウントを選択します。

Install Vercel 画面が表示されるので

Install on your personal account 

インストール先　アカウント名 を確認して

VercelからアクセスできるGitHubのリポジトリを指定する

すべてのリポジトリへのアクセスを許可する場合は、「All repositories」を選択する。

選択したリポジトリへのアクセスのみ許可する場合は、「Only select repositories」を選択する。

今回は、作成したGithubにある、Next.jsのリポジトリを指定するので。自分は、Only select repositories を選択して、プロジェクトのリポジトリを指定しました。

アカウント名/リモートリポジトリ名　が選択されればOKです。

緑色のInstall ボタンをクリックします。

Confirm access 画面が表示されます？

アクセス確認画面　が表示されるのでGitHubのPasswordを入力します。

緑色のConfirm　ボタンをクリックします。

GitHub Installation Completed　画面が表示されます。

再度、Create Git Repository　画面に遷移するので、

Repository Name に、ローカルリポジトリ名 sample-next-project を入力してCreate　ボタンをクリックします。


### Vercelのアカウントが作成できたのでデプロイしてみましょう

- sample-next-project　プロジェクトをGithubにpushする
- sample-next-project　プロジェクト　をVercelで選択し、Deployする















## Gitでバージョン管理してみよう！


① sample-next-project　プロジェクトをGithubにPushする

1. ローカルのプロジェクトをGithubへアップロードする
Nuxt.jsでは、自動でGitのローカルリポジトリを作成しています。

ターミナルより、sample-next-project プロジェクトルートディレクトリに移動する

- Gitのトラッキングの対象外のファイルを指定する

```sh
% echo '.DS_Store' >> .gitignore
```

- 現在のGitの状態を確認しましょう

Gitのユーザー名、メールアドレスを確認する

```sh
% git config --global --list
```

user.name=
user.email=


表示されなかったらGithubと同じアカウントを登録する

ユーザー名を登録する

<username> はここで変更してください

```
% git config --global user.name <username>
```

メールアドレスを登録する

<emailaddress>　はemailを登録してください

```
% git config --global user.email <emailaddress>
```

git branch コマンドで現在のブランチを確認します。

```
% git branch
```

* main

現在のブランチに*がついています。

sample-next-project プロジェクトルートディレクトリ の状態を確認する

```sh
% git status
```

modified:   src/app/page.tsx

リポジトリと違いがあることがわかります。

ステージエリアにファイルを追加する

```sh
% git add .
```

modified:   src/app/page.tsx

git commitでスナップショットをコミットする

```sh
% git commit -m "hello world add"
```

nothing to commit, working tree clean

- ローカルリポジトリの内容をリモートリポジトリに反映

Githubにログインし、Githubダッシュボードより、リモートリポジトリを作成します。

右上の[+]　ボタンをクリックし、[New repository] をクリック

Create a new repository 画面が表示されたら、

Repository name → sample-next-project　

ローカルのリポジトリ名と　Githubのリモートリポジトリ名を一緒にする

Public 公開 Private 非公開を選択する

Create repository ボタンをクリックします。

sample-next-project　リモートリポジトリのホーム画面が表示されます。

```sh
% git remote add origin git@github.com:Githubname/RemoteRipository.git
```

ローカルリポジトリの内容をリモートリポジトリにPush(アップロード)します。

```sh
% git push -u origin main
```
