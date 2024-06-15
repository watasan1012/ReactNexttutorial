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

## 0. Next.jsとは

Next.jsは、Vercel社が開発したReactフレームワークで、以下の特徴を持ちます。

1. Reactベース: Next.jsはReactをベースにしており、Reactコンポーネントを使用してUIを構築できます。
2. サーバーサイドレンダリング(SSR):初期レンダリングをサーバーサイドで行うことができ、SEOやパフォーマンスの向上に役立ちます。
3. 静的サイト生成(SSG): ビルド時に静的なHTMLファイルを生成し、高速なページ読み込みを実現します。
4. APIルート: 内臓のAPIルートを使用して、簡単にバックエンド機能を実装できます。
5. 画像最適化: ビルドインの画像最適化機能を提供し、パフォーマンスの向上に貢献します。
6. ルーティング: フォルダ構造に基づいた自動的なページのルーティング機能を提供します。
7. サーバーサイドコンポーネントのデータフェッチ機能により、サーバー側でのデータ取得が簡単に行えます。
8. スタイリング：Tailwind CSS、CSS-in-JS等のスタイリング手法をサポートし、柔軟なデザイン実装が可能です。

【参考】
[https://nextjs.org/docs#how-to-use-these-docs](https://nextjs.org/docs#how-to-use-these-docs)

## 1. Next.jsアプリ開発で使用する言語

1. HTML
   * HTML(HyperText Markup Language、ハイパーテキスト・マークアップランゲージ)は、ウェブサイトのコンテンツの構造を作るために使うコードであり、ページ内の表示を作ります。
   * 【参考リンク htmlの基本】　[https://creatorquest.jp/lessons/html/](https://creatorquest.jp/lessons/html/)
2. CSS
   * CSS (Casgading Style Sheets)は、ウェブページのスタイルを設定するコードであり、ページ内のデザインを作ります。
   * 【参考リンク CSSの基本】 [https://creatorquest.jp/lessons/css/css-intro/](https://creatorquest.jp/lessons/css/css-intro/)
   * 【参考リンク CSS Flexbox チートシート】 [https://www.webcreatorbox.com/tech/css-flexbox-cheat-sheet](https://www.webcreatorbox.com/tech/css-flexbox-cheat-sheet)
3. JavaScript
   * JavaScriptは、ウェブページの動作や処理を作るためのプログラミング言語です。
4. Typescript
   * Typescript は、JavaScript に基づいて構築された厳密に型指定されたプログラミング言語であり、コードの信頼性と保守性を向上させます。
  * 【参考リンク TypeScript公式サイト】 [https://www.typescriptlang.org/](https://www.typescriptlang.org/)
  * 【参考リンク TypeScriptのリファレンス】 [https://typescriptbook.jp/reference](https://typescriptbook.jp/reference)

Next.jsを使った開発では、これらの言語と技術を組み合わせて、効率的にWebアプリケーションを構築することができます。
 
## 2. Next.jsアプリ開発の環境について

Next.jsアプリを作成するために必要なツールや環境について、以下のようにまとめることができます。

### Windowsにインストールする手順

Tools:

* Windows Terminal: コマンドラインツールやシェルをインターフェースで管理できるアプリケーションです。
* VSCode(Visual Studio Code): コードエディタです。

アプリケーション:

* Volta: Node.jsバージョン管理ツールでNode.jsをインストールします。
[公式サイト](https://docs.volta.sh/guide/getting-started)から「download and run the Windows installer」をクリックしてインストーラをダウンロードします。

### 手順:

1. Windowsの開発者モードを有効にする
   * 検索ボックスに「開発者」と入力し、「開発者向け設定」を起動します。
   * 開発者モードを「オン」にして閉じます。

2. Voltaをインストールします
   * ダウンロードしたインストーラーを起動し、画面の指示に従ってVoltaをインストールします。

3. voltaのバージョンを確認します

Windows Terminalを開き、以下のコマンドを実行します。

```sh
volta -v
```

4. Node.jsのインストール

  * 最新バージョン（LTS）をインストールします。

```sh
volta install node
```

5. Node.jsのバージョン確認

```sh
node -v
```

6. npmのバージョンを確認

   * Node.jsと共にnpmもインストールされているか確認します。

```sh
npm -v
```

7. npmがインストールされていなかった場合

以下のコマンドでnpmをインストールします。

```sh
volta install npm
```

8. voltaでインストールしたバージョンを確認
    
    * 以下のコマンドでVoltaで管理されている全てのバージョンを確認します。

```sh
volta list all
```

以上がNode.jsをWindowsにインストールする手順ででした。

### macOSにインストールする手順

Tools:

Terminal: コマンドラインツールやシェルをインターフェースで管理できるアプリケーションです。macOSでは既存の状態でターミナルがインストールされています。

VSCode(Visual Studio Code): コードエディタです。

アプリケーション:

* Volta: Node.jsバージョン管理ツールでNode.jsをインストールします。

### 手順:

1. Voltaをインストールする

```sh
curl https://get.volta.sh | bash
```

2. Voltaのバージョン確認する

```sh
volta -v
```

3. Node.jsのインストールする

実際にNode.jsのバージョン管理を行う方法について詳しく見ていきましょう。

4. Node.jsのバージョンを最新のLTS（長期サポート版）をインストール

```sh
volta install node
```

5. Node.jsが入ってるか確認する

```sh
node -v
```

6. npmの確認

```sh
npm -v
```

これでmacOSにNode.jsをインストールする手順は完了です。

## GitHub　のアカウントを作成する

Vercelは、GitHubアカウントが必要です。

* すでにGithubアカウントを持っている場合
GitHubアカウントを所持している場合は、[GitHubのサインイン画面](https://github.com/login)よりログインしてください。

* 新規Githubアカウントを作成する
  
  1. [Githubサインアップ画面](https://github.com/signup)を開きます。
 
  2. Enter your email*
     入力欄に メールアドレスを入力して`Continue`ボタンをクリックする。

  3. Create a password*
     GitHubにログインするためのパスワードを入力します。`Continue`ボタンをクリックします。

  4. Enter a username*
     GitHubのアカウント名を入力します(あだ名でOKです)。`Continue` ボタンをクリックします。

  5. Email preferences GitHub
     GitHubに関するメールを受信する場合はチェックを入れます。

  6. Verify your account
     アカウント保護のため、質問に回答してあなたがロボットではないことを証明してください。`検証する`ボタンをクリックします。

  7. `送信ボタン`をクリックします。

  8. We sent a launch code to 登録メールアドレス Enter code*
     登録メールアドレスに送られた確認コードを入力し`enter キー`を入力します。

  9. ログイン画面が表示されるのでログインします。

  10. GitHubの利用設定 How many team members will be working with you?
　　　チームメンバーは何人ですか？`Just me`(私だけ)を選択します。

  12. Are you a student or teacher?
      あなたは学生ですか、それとも教師ですか？
      `N/A`(該当なし)を選択し、`Continue`　ボタンをクリックします。

  13. What specific features are you interested in using?
      使用したい機能を選択します。該当するものにチェックを入れ、`Continue`　ボタンをクリックします。

  14. Where teams collaborate and ship.
      価格プランを設定します。`Free`を選択し、`Continue for free`　ボタンをクリックします。

以上でGitHubアカウントの作成が完了です。お疲れ様でした！

## 3. Next.jsに触れてみる! 

###  vercelで公開する

  * フロントエンドの環境を提供するホスティングのPaaS(Platform as a Service)です。
  * Githubなどのリポジトリと連携させるだけで、簡単にデプロイできます。
  * [参考リンク-vercel](https://vercel.com/)

### Supabase
  * バックエンド側の環境を提供することができるデータベースであり、Bass(Backend as a Service)です。

## Vercel でデプロイする

フロントエンド開発のプラットフォームで、デプロイ環境を提供する。

[参考サイト](https://dev-harry-next.com/infrastructure/vercel-detail)

## Vercel　の　アカウントを作成する

Vercelアカウントを所持している場合は、[Vercel](https://vercel.com/login)のサインイン画面よりログインしてください。

[Create Your Vercel Account]([url](https://vercel.com/signup)をブラウザーから開く。

### Create Your Vercel Account 画面が表示されたら Plan Type を選択します

![Vercel_SignUp_1](画像のURL "画像タイトル")

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

Plan Type から Hobby を選択します。

Your Name を入力します。

Your Name  
あだ名でも大丈夫です。
英数字を入力します。

Continue ボタンをクリックします。

### Let's connect your Git provider 画面を表示します

![Vercel_SignUp_2](画像のURL "画像タイトル")

Continue with　GitHub　ボタンをクリックします。

### Vercel by Vercel would like permission to: 画面

![Vercel_SignUp_3](画像のURL "画像タイトル")

Vercel would like permission to: GitHubアカウント

GitHubアカウントにVercelは、GitHubアカウントに接続の許可を求めています。

Authorize Vercel ボタンをクリックします。

Vercel　アカウントが作成されました。

### 電話番号認証が表示される場合がある

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

## Vercel　にログインする

左側上部のVercel　ロゴをクリックするかVercelにログインする

[https://vercel.com/login](https://vercel.com/login)

Log in to Vercel 画面より

Continue with Github をクリックします。

## Next.jsプロジェクトを作成する

Vercelのテンプレートを使用してプロジェクトを作成し公開する方法と、localにNext.jsのプロジェクトを作成してGitHubにアップロードしてVercelにデプロイします。

- ターミナルを起動し、以下のコマンドを実行する

対話的に新しいプロジェクトを作成できます。

```sh
% npx create-next-app@latest
```

```
Need to install the following packages:
create-next-app@14.2.4
Ok to proceed? (y)
```

```result
? What is your project named? › my-app
```

my-app の部分に、作成するプロジェクトの名前を入力します。

sample-next-project

```sh
? Would you like to use TypeScript? › No / Yes
```

? TypeScriptを使いたいですか？いいえ / はい

矢印キーでカーソルを変更できます。アンダースコアがあるほうが選択状態です。
enterキーで確定です。

Yes

```sh
? Would you like to use ESLint? › No / Yes
```

? ESLintを使用しますか？いいえ / はい

Yes

```
? Would you like to use Tailwind CSS? › No / Yes
```

? Tailwind CSSを使用しますか？いいえ / はい

Yes

```
? Would you like to use `src/` directory? › No / Yes
```

? このプロジェクトでsrc/`ディレクトリを使用しますか？いいえ / はい

Yes

```
? Would you like to use App Router? (recommended) › No / Yes
```

? App Routerを使用しますか？ (推奨）いいえ / はい

Yes

```
? Would you like to customize the default import alias (@/*)? › No / Yes
```

? デフォルトのインポートエイリアス（@/*）をカスタマイズしますか？いいえ / はい

No

## プロジェクトの作成が起動する

```
Success! Created sample-next-project at /Users/ユーザーディレクトリ/作業ディレクトリ/sample-next-project
```

が表示されたら完成です。

## 動作確認

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

#### sample-next-project　を Githubと紐付ける

- 現在のGitの状態を確認しましょう

Gitのユーザー名、メールアドレスを確認する

```sh
% git config --global --list
```

user.name=
user.email=

表示されなかったり、違ったらGithubと同じアカウントを登録する

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

- GitHubのSSH接続を設定する

### 公開鍵・秘密鍵を作成する

#### 鍵を入れるフォルダに移動しましょう

```
% cd ~/.ssh
```

#### 次のコマンドで鍵を生成します

```sh
% ssh-keygen -t rsa
```

Enter file in which to save the key (/Users/ユーザー名/.ssh/id_rsa): 

Enter キーをクリックする

/Users/ユーザー名/.ssh/id_rsa already exists.
Overwrite (y/n)?

y キーの次に　enter キー

Enter passphrase (empty for no passphrase):

enter キー

Enter same passphrase again: 

enter キー

#### 公開鍵をGitHubにアップする

[https://github.com/settings/ssh](https://github.com/settings/ssh/new)

Add new SSH Key 画面が表示されたら、

Title　なんでもいい

Key　先ほど作成した公開鍵を貼り付ける

なお、鍵の中身のクリップボードへのコピーは

Mac
```
$ pbcopy < ~/.ssh/id_rsa.pub
```

windows
```sh
$ clip < ~/.ssh/id_rsa.pub
```

Add SSH key ボタンをクリックする

#### 接続確認

```sh
% ssh -T git@github.com
```

Hi Githubアカウント名! You've successfully authenticated, but GitHub does not provide shell access.

#### config ファイルを作成する

~/.ssh/configを作成しその中に

```
Host github.com.sub
  HostName github.com
  User git
  Port 22
  IdentityFile ~/.ssh/id_rsa
  TCPKeepAlive yes
  IdentitiesOnly yes
```

#### Githubにリモートリポジトリを作成する

[https://github.com/new](https://github.com/new)

Repository name → sample-next-project

公開設定は Public Private どちらでも大丈夫です。

Create repository ボタンをクリックする

sample-next-project プロジェクトのルートディレクトリより

```sh
% git status
```

```sh
% git add .
```

```sh
% git commit -m "Hello world"
```

```sh
%　git remote add origin git@github.com:Githubアカウント名/sample-next-project.git
```

```sh
% git branch -M main
```

```sh
% git push -u origin main
```

fatal: The current branch main has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin main

To have this happen automatically for branches without a tracking
upstream, see 'push.autoSetupRemote' in 'git help config'.

と表示されたら指示通り、実行してみる

```sh
% git push --set-upstream origin main
```

fatal　や　error　が表示されたら、HTTPS 接続か、SSH接続を疑う

現在登録されているリモートのリポジトリを確認する

```
% git remote -v
```

origin	git@github.com:Githubアカウント名/sample-next-project.git (fetch)
origin	git@github.com:Githubアカウント名/sample-next-project.git (push)

Github登録時の　SSHキーと同じであることを確認する

git@github.com:Githubアカウント名/sample-next-project.git

-> remoteがaddされていることを確認

#### 違う場合は　git remote set-url origin コマンドで修正する

```sh
git remote set-url origin https://github.com/Githubアカウント名/sample-next-project.git
```

### Vercel にログイン

ログインしていた場合は、 左上のアカウント名 projects をクリックします。

### Deploy your first project　画面
Start with one of our templates or create something new.

私たちのテンプレートのいずれかを使用して開始するか、新しい何かを作成します。

リストから、Next.js App and a Serverless Function API 横の Deploy をクリックします。

### Create Git Repository　 画面

To ensure you can easily update your project after deploying it, a Git repository must be created. Every push to that Git repository will be deployed automatically.

デプロイ後にプロジェクトを簡単に更新できるようにするには、Git リポジトリを作成する必要があります。そのGitリポジトリへのプッシュはすべて自動的にデプロイされます。

Git Scope の Select Git Scope というセレクトボックス　を選択して Select Git Scope から　Add GitHub Account　を選択します。

###  Install Vercel　画面が表示されるので

Where do you want to install Vercel?

インストール先のGitHubアカウントを選択します。

### Install Vercel 画面が表示されるので

Install on your personal account Github　アカウントロゴ

for these repositories:

- All repositories

This applies to all current and future repositories owned by the resource owner.

Also includes public repositories (read-only).

全てのリポジトリに適用されます。

パブリックリポジトリ(読み取り専用)も含まれます。

- Only select repositories
Select at least one repository.

Also includes public repositories (read-only).

リポジトリを選択する

どちら選択する

Only select repositories　をチェックを入れると

Select repositories のプルダウンから、作成した、Githubアカウント名/sample-next-project を選択します。

Install ボタンをクリックします。

### Confirm access 画面

Passkey
When you are ready, authenticate using the button below.

パスキー
準備ができましたら、下のボタンで認証してください。

Use passkey ボタンをクリックします。

Google Chrome 画面が表示されたら

パスワードを使用...をクリックします。

macを起動する時のパスワードを入れて完了です。

### 確認

確認してcreate ボタンをクリックします。

### Deploy 画面が表示されます


Deployment started 53s ago...

デブロイ　が開始されます。

### Congratulations!　画面が表示

You just deployed a new Project to Vercel.

Congratulations!　の下にある画像をクリックするとデブロイ結果に画面遷移して確認できます。



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


Vercel












## Gitでバージョン管理してみよう！


① sample-next-project　プロジェクトをGithubにPushする

1. ローカルのプロジェクトをGithubへアップロードする
Nuxt.jsでは、自動でGitのローカルリポジトリを作成しています。

ターミナルより、sample-next-project プロジェクトルートディレクトリに移動する

- Gitのトラッキングの対象外のファイルを指定する

```sh
% echo '.DS_Store' >> .gitignore
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
