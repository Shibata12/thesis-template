# LaTeXを使用するための準備
```{margin} TeX Live
LaTeXをローカルで利用するためには，TeX Liveをインストールすることが簡単です．ですが，インストールに数時間かかりますし，空き容量も10GB近く必要であり，手間がかかります．
```
はじめてLaTeXを使用する場合は，[Cloud LaTeX](https://cloudlatex.io/)をお勧めします．Cloud LaTeXはローカルに環境構築する手間がなく，オンラインでLaTeXを利用することができます．LaTeXを利用できるように環境を整えることは非常に手間がかかるので，便利なサービスです．Cloud LaTeXを使用するには，アカウントの登録が必要です（[Cloud LaTeX の登録の仕方・使い方](https://cloudlatex.io/how-to-use-cl)）．アカウントを登録したら，空のプロジェクトを作成してみましょう．

## 空のプロジェクトを作成
まず，下の画像のマイページ（<font color="red">赤枠</font>で囲んだ部分）をクリックして開いてください．
![home](images/home.png)

マイページを開いたら，新規プロジェクトをクリックしてください．
![mypage](images/mypage.png)

空のプロジェクトを作成します．プロジェクト名は任意の名前にしてください（この例ではthesis-demo）．
![project](images/project.png)

作成したプロジェクトを開くと，下の画面と同じものが表示されます．
![first-view](images/first-view.png)
## LaTeXのHello world
ここでは，LaTeXで文書を作成するための最小単位を紹介します．まず，下の画像の<font color="red">①</font>部分(`main.tex`)をクリックします．次に，<font color="red">②</font>部分に下の内容を書き込みます．
````{grid-item-card}
`main.tex`
^^^^^^^^^^^^^
```latex
\documentclass[]{jlreq}

\begin{document}
Hello \LaTeX!
\end{document}
```
````
最後に<font color="red">③</font>部分のコンパイルをクリックすると，pdfファイルが出力されます．
![hello-LaTeX](images/hello-LaTeX.png)

`main.tex`に書き込んだ内容について，簡単に説明します．
* `documentclass[]{jlreq}`
<br>文書クラスを指定します．文書クラスは文書のレイアウトや形式（書籍や論文等）を形作ります．ここでは`jlreq`を指定しました．`[]`内ではオプションを指定します．ここではオプションを指定していません（[表紙を作る](front-cover.md)ときに指定します）．
* `begin{document}`と`\begin{document}`
<br>`begin{document}`と`\begin{document}`は`document`環境を指定します．`begin{document}`と`\begin{document}`の間に本文を書き込みます．ここでは，`Hello \LaTeX!`を書き込みました．

以降，Cloud LaTeXを使用して，修士論文のテンプレートを作成していきます．