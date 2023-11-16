---
title: "VS Codeで全角スペースを表示または非表示に設定する方法"
emoji: "👩‍💻"
type: "tech"
topics: ["vscode", "エディタ", "プログラミング"]
published: true
---

こんにちは。職業「戸倉彩」です。

VS Codeの最新バージョンにアップデートしたら、全角スペースがデフォルトで黄色い四角で表示されるようになったことに驚いた方はいらっしゃっしゃいませんか。

これまではVS Codeの設定で半角スペースの表示の有無を指定することができましたが、今回は全角対応したかっこうとなり、エディタ編集の際に半角か全角スペースを見分けたり、意識して作業を行いたいユーザーにとっては便利な機能の一つとなったと言えます。

しかしながら、利用しないユーザーにとってはノイズのように思えるかもしれません。VS Code設定でこの機能を有効化にするかどうか設定ができますので、今回はその設定方法を共有いたします。

## VS Code 1.63 新機能 - Unicodeハイライト表示
VS Codeバージョン1.63の変更点の一つとして、全角スペースを表示する機能が追加されました。正確にお伝えすると、ソースコード内に一般的でない非表示の文字(スペース)がデフォルトで強調表示されるようになりました。さらにASCII文字と混同される可能性のある文字(スペース)も強調表示されます。
> 参考情報: [VS Code 1.63 リリースノート (November 2021)](https://code.visualstudio.com/updates/v1_63)  
Unicode highlighting 
![](https://code.visualstudio.com/assets/updates/1_63/unicode-highlighting-invisible.png)

## 表示または非表示の設定方法
1. VS Codeを起動する
2. 画面左下の「管理」アイコン(歯車アイコン)をクリックする
3. **[設定]** ページ内の検索ボックスで **[Unicode Highlight]** を検索する
4. 下記の設定をカスタマイズする
* **Editor > Unicode Highlight: Ambiguous Characters**  
現在のユーザーロケールで一般的な文字を除き、基本的なASCII文字と混合される可能性のある文字を強調表示するかどうかを制御します。デフォルトでオンになっているので、表示したくない場合にはチェックボックスでチェックを外します。
* **Editor > Unicode Highlight: Include Comments**    
コメントないの文字をUnicode強調表示の体表にするかどうかを制御します。  
  * inUntrustedWorkspace (規定)
  * true (制御したい場合)
  * false (制御したくない場合)
* **Editor > Unicode Highlight: Invisible Characters**  
スペースを予約するだけの文字または幅がまったくない文字を強調表示するかどうかを制御します。デフォルトでオンになっているので、表示したくない場合にはチェックボックスでチェックを外す。
* **Editor > Unicode Highlight: Non Basic ASCII**    
基本以外のすべてのASCII文字を強調表示するかどうかを制御します。U+0020からU+007Eの間の文字、Tab、改行コード、行頭復帰のみが基本ASCIIと見なされます。  
  * inUntrustedWorkspace (規定)
  * true (制御したい場合)
  * false (制御したくない場合)
![](/images/2021-12-12-01.png)   

いかがでしたでしょうか。より詳細な設定を行いたい場合には、settings.jsonで記述をすることで設定もできますので、冒頭にご紹介した公式サイトで公開されている情報を参考にしてください。

もし、周りに困っている方がいらっしゃったら、こちらの情報を教えてあげてください。今回は以上です 🙌

📱 Twitter [@ayatokura](https://twitter.com/ayatokura) で、最新情報も配信していますので、よろしければフォローも是非お願いします。
