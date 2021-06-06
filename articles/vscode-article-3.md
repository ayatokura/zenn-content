---
title: "VS Codeに関するセキュリティの脆弱性のお話"
emoji: "👩‍💻"
type: "tech"
topics: ["vscode", "エディタ", "セキュリティ"]
published: true
---

こんにちは。職業「戸倉彩」です。

VS Codeを使っていて、セキュリティ周りで気になったことはありませんか。今回は、VS Code自体の脆弱性にまつわる話を少しだけしてみたいと思います。

VS Codeは、マイクロソフトが主導して開発が行われているオープンソースなコードエディタです。GitHubを通じて、ユーザーからの改善案やフィードバックが活発に行われており、開発チームがユーザーコミュニティと共により良いエディタ作りに取り組むスタンスで展開されています。

しかし、残念ながらソフトウェアに不具合や脆弱性はつきものです。そのため、脆弱性が発見されると、マイクロソフトが公式に原因の特定や問題の対処を行い、最新版のVS Codeでセキュリティを強化する機能の提供などが行われています。

VS Codeがリリースした当初からStable(通常版)は、ほぼ毎月バージョン更新が行われています。個人的には最新のものを利用することをお勧めしています。

## VS Codeの脆弱性に関する最新情報
マイクロソフト製品やサービスに影響がありセキュリティの脆弱性に関する情報について知りたい場合は、**Microsoft Security Response Center(MSRC)** サイト(https://msrc.microsoft.com/update-guide/)にアクセスすると最新情報を得ることができます。

**Security Update Guide** の中で [**Vulnerabilities**(脆弱性)] タブをクリックし、検索ボックスで `Visual Studio Code` を入力して検索すると、指定されている期間内で公開されたCVE(Common Vulnerabilities and Exposuresの略、共通脆弱性識別子のことで、簡単に言うとソフトウェアの脆弱性のリストのことです)を絞り込むことができます。

それぞれの **CVE Number** をクリックすることで、詳細内容や最新の対応状況などについて確認することができます。

![](https://storage.googleapis.com/zenn-user-upload/4feb3061d02841572b4624e2.jpg)

## VS Codeに関する問題を発見した/問題が解決されない場合
### VS Code公式にレポートを  
GitHubのアカウントをお持ちでない方は、事前にGitHubのページ (https://github.com/) にアクセスして、アカウント作成(Sign up)しておきましょう。
* VS Codeエディタからレポートする  
VS Codeの[ヘルプ]メニューから[Report Issue]を選択し、表示された画面に必要事項を入力し、[GitHubで作成]ボタンをクリックして、問題の報告を行います。できるだけ英語で書いておくようにしましょう。また、報告するのがVS Code自体の脆弱性に関する内容の場合には、項目は下記を指定しておくのが良いと思います。
    * これは **[バグ報告]**
    * 記録 **[Visual Studio Code]**
![](https://storage.googleapis.com/zenn-user-upload/822ce69770ea9c95cf8ffa21.jpg)

* VS Code GitHubから直接Issueをあげる  
マイクロソフトが公開しているVS CodeリポジトリでIssueをあげることができます。※ここでは操作方法の解説は割愛させていただきます。基本的に、通常のGitHubでIssueをあげる方法と同じと考えていただいて問題ないです。
https://github.com/microsoft/vscode/issues

![](https://storage.googleapis.com/zenn-user-upload/df6647d0e6777e82691537c2.jpg)

### MSRCサイトから問題を報告する
MSRC Researcher Portal (https://msrc.microsoft.com/create-report?c=uhf) にアクセスし、画面に表示された案内を理解した上で、[Sign in to report your vulnerability]ボタンからサインイン後に、画面に従って問題を報告してください。

![](https://storage.googleapis.com/zenn-user-upload/4bc3b2544061e17201457473.jpg)

今回は以上です 🙌

📱 Twitter [@ayatokura](https://twitter.com/ayatokura) で、最新情報も配信していますので、よろしければフォローも是非お願いします。