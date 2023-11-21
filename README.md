<p align="center" style="font-size: 3rem; line-height: 1;">
LaraFlowBoilerplate
</p>

## 概要

Laravelを使用した社内向け業務管理ツールのテンプレート。

特定のメールアドレスを所有する人だけがユーザー登録をして操作することが出来るアプリ開発を出来る基本的なユーザー管理を目的としたボイラープレートです。

- 社内向け業務管理
- 限定されたチーム内の作業効率化
- 学内向けアプリケーション

等々でお使いいただけます。

このリポジトリをcloneして各自必要な機能を開発していくのを目的としています。

- Jetstream
- Livewire
- TailwindCSS
- Alphin.js

が既にセットアップ済みです。

データベースはsqlite、メール送信はsendmailを使用しているので、一般的なレンタルサーバー(共有サーバー)に設置する事が出来るように組まれています。

## 使用方法

    git clone git@github.com:soramugi/lara-flow-boilerplate.git
    mv lara-flow-boilerplate/ example-project/
    cd example-project
    cp .env.example .env
    composer install
    npm install
    php artisan key:generate
    touch database/database.sqlite
    php artisan migrate
    php artisan optimize:clear
    npm run build
    php artisan serve

こちらのURLにアクセス出来るようになります。 http://127.0.0.1:8000/

## 登録ユーザーを限定する

app/Actions/Fortify/CreateNewUser.php

```
                // 'regex:/(.*)@example\.com/i', // TODO: 会員登録ができるメールアドレスを指定
```

上記のコメントアウトを外し、社内向けメールアドレスのドメインを指定することで登録できるユーザーを限定することができます。

## 公開方法

apacheが稼働しているサーバーであればドキュメントルート配下に丸ごと置く事で公開できるように `.htaccess` を用意しています。

公開環境の必要ライブラリ等は `composer.json` 等に準じます。

## License

The Laravel framework is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).
