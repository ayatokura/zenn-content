---
title: "VS Codeのツリー表示をピクセル単位でカスタマイズする方法"
emoji: "👩‍💻"
type: "tech"
topics: ["vscode", "エディタ", "プログラミング"]
published: true
---

こんにちは。職業「戸倉彩」です。
今回は、VS Codeでエクスプローラーを開いた時に、ディレクトリーの階層が深くなった場合に見やすくするための、設定方法のTipsをご紹介します。

## 設定方法
1. VS Codeを起動し、画面左下の **管理** アイコン(歯車アイコン)をクリックする
2. 表示されたメニューから **設定** を選択する
3. **[設定の検索]** ボックスで `workbench.tree.indent` を入力する
   >settingsファイルを直接編集する場合は下記を記述し、値は好みで指定しておく
   ```
   "workbench.tree.indent": 8,
   ```
4. 検索結果から **Workbench > Tree: Indent** セクションの数値を変更する
5. 設定が反映され、VS Codeの **エクスプローラー** 画面でツリーのインデント表示が変更されたことを確認する。

デフォルトでは`8`が設定されていますが、`20`くらいに設定しておくとより見やすくなりそうです。個人差がある部分なので、お好みで調整してみてください。
![](/images/2022-01-23-19-59-42.png)

### 参考情報
* Visual Studio Code 公式ドキュメント(英語) - [Visual Studio Code User and Workspace Settings](https://code.visualstudio.com/docs/getstarted/settings)

Happy Coding!

📱 Twitter [@ayatokura](https://twitter.com/ayatokura) で、最新情報も配信していますので、よろしければフォローも是非お願いします。