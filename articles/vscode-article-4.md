---
title: "VS Codeでブラケットペアの範囲を可視化する方法"
emoji: "👩‍💻"
type: "tech"
topics: ["vscode", "エディタ", "プログラミング"]
published: true
---

こんにちは。職業「戸倉彩」です。

VS Codeでプログラミングをしている際に、ブラケットペアをもう少し分かりやすく表示させて作業効率化がはかれたら良いなと感じたことはありませんか。今回は、VS Codeでブラケットペアの範囲を可視化する方法の紹介です。

## VS Code 1.62 新機能 - 改良されたブラケットペアガイド
VS Codeバージョン1.62の変更点の一つとして、ブラケットペアをガイドする機能が改良されました。
> 参考情報: [VS Code 1.62 リリースノート (October 2021)](https://code.visualstudio.com/updates/v1_62)  
Editor - Improved bracket pair guides  
<img src="https://code.visualstudio.com/assets/updates/1_62/bracket-pair-guides.gif" width="400">

## 設定方法
1. VS Codeを起動する
2. 画面左下の「管理」アイコン(歯車アイコン)をクリックする
3. **[設定]** ページ内の検索ボックスで **[editor.guides.bracketPairs]** を検索する
4. **Editor > Guides: Bracket Pairs** 項目がデフォルトではオフ **[false]** になっているので、ドロップダウンメニューで下記のいづれかに変更する。
    * **active**: アクティブなブラケットペアに対してのみ有効にする
    * **true**: ブラケットペアガイドを有効にする  
![](/images/2021-11-07-1.png)    

今回は以上です 🙌

📱 Twitter [@ayatokura](https://twitter.com/ayatokura) で、最新情報も配信していますので、よろしければフォローも是非お願いします。