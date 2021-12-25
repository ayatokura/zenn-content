---
title: "VS CodeからTwitterにツイート投稿する方法"
emoji: "👩‍💻"
type: "tech"
topics: ["vscode", "エディタ", "プログラミング"]
published: true
---

こんにちは。職業「戸倉彩」です。

この記事は **「Visual Studio Code Advent Calendar 2021」** の24日目の記事です。

https://qiita.com/advent-calendar/2021/vscode

VS Codeから離れず快適にTwitterにリアルタイムでツイート投稿する方法を見つけましたので、ご紹介いたします。

## Twittter, together
今回は、「Twitter, together」というGitHub Actions機能を活用して、GitHub上のリポジトリのテキストファイルを自動投稿する仕組みを使います。
* 参考リソース: [gr2m/twitter-together: A GitHub action to tweet from a repository](https://github.com/gr2m/twitter-together)

## 利用する技術
* GitHub Actions
* Twitter API - v8バージョン以降
* Visual Studio Code

## 設定方法
1. 利用しているTwitterアカウントを用いて [Twitter Developer](https://developer.twitter.com/en/apps) サイトにアクセスし、Twitterアプリケーションを作成し、認証情報を取得する。※Twitterアカウントをお持ちでない方は、新規アカウント作成が必要です。
  * TWITTER_API_KEY
  * TWITTER_API_SECRET_KEY
  * TWITTER_ACCESS_TOKEN
  * TWITTER_ACCESS_TOKEN_SECRET
2. GitHubにログインし、ツイート投稿用のリポジトリを作成する。
3. リポジトリの **「Secrets」** に先ほど取得した認証情報を登録する。
4. .github/workflows/twitter-together.yml ファイルを作成し、下記の内容を記述して保存する。
```
on: [push, pull_request]
name: Twitter, together!
jobs:
  preview:
    name: Preview
    runs-on: ubuntu-latest
    if: github.event_name == 'pull_request'
    steps:
      - uses: gr2m/twitter-together@v1.x
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
  tweet:
    name: Tweet
    runs-on: ubuntu-latest
    if: github.event_name == 'push' && github.ref == 'refs/heads/main'
    steps:
      - name: checkout main
        uses: actions/checkout@v2
      - name: Tweet
        uses: gr2m/twitter-together@v1.x
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
          TWITTER_ACCESS_TOKEN: ${{ secrets.TWITTER_ACCESS_TOKEN }}
          TWITTER_ACCESS_TOKEN_SECRET: ${{ secrets.TWITTER_ACCESS_TOKEN_SECRET }}
          TWITTER_API_KEY: ${{ secrets.TWITTER_API_KEY }}
          TWITTER_API_SECRET_KEY: ${{ secrets.TWITTER_API_SECRET_KEY }}
```
5. VS Codeを開き、ご自身が作業している対象のGitHubリポジトリ連携する。
6. tweets/test.tweet ファイルを作成し、任意のテキストを記述し保存する。
7. GitHubにプッシュコミットを実行する。
8. 後は、裏側でGitHub Actionsが動き、Twitterにテキスト内容の投稿が行われる。

ローカルにVS Codeをインストールできない環境を用意できない場合には、ご自身のリポジトリのgithub.comの部分をgithub.devに変えてアクセスすることで、WebブラウザベースのVS Code上で作業を行うことができます。

以上になります。もし、他にVS CodeからTwitterにツイート投稿する方法をご存知の方がいらっしゃいましたら是非シェアいただけると嬉しいです。

Happy Coding!

📱 Twitter [@ayatokura](https://twitter.com/ayatokura) で、最新情報も配信していますので、よろしければフォローも是非お願いします。