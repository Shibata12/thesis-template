# パッケージの利用
LaTeXには様々なパッケージがあります．例えば，図や画像を張り込むためのパッケージ(`graphicx`)や，しおりを作るためのパッケージ(`hyperref`)などがあります．ここでは，パッケージの読み込み方法を示します．

## パッケージの読み込み
```{admonition} パッケージを読み込む前に
パッケージ間の互換性には複雑な問題があるそうです．これを解決するために`\RequirePackage{plautopatch}`と`\RequirePackage[l2tabu, orthodox]{nag}`を`\documentclass[]{}`の前に置きます．これは，パッケージ間の互換性に問題がある場合に適切な処理を行うパッチと，警告を行うパッケージです．詳しくは，[日本語 LaTeX の新常識 2021 - Qiita](https://qiita.com/wtsnjp/items/76557b1598445a1fc9da)と[古いコマンドやパッケージを確認する](https://blog.goo.ne.jp/superspeed1963/e/4500867fef0c7711fb46f66cc093361b)を確認してください．
```
パッケージの読み込みは`\documentclass[]{}`と`\begin{document}`の間に書き込みます．この間の部分はプリアンブル部(preamble)といいます．

```{margin}
`%`でコメントアウトできます．
```

````{grid-item-card}
`main.tex`
^^^^^^^^^^^^^
```latex
\RequirePackage{plautopatch}
\RequirePackage[l2tabu, orthodox]{nag}

\documentclass[]{jlreq}
% プリアンブル部
% ここでパッケージを読み込む
\begin{document}
Hello \LaTeX!
\end{document}
```
````

パッケージの読み込みは`preamble.tex`の中で行い，このファイルを読み込むことで行います．回りくどいように見えますがこれからファイルを色々追加していくので，フォルダ分けを行いファイルを整理します．まず，下の画像のように左上の＋をクリックして新規ファイルを作成します．ファイル名は`preamble.tex`にします．
![preamble](images/preamble.png)
同様にして，新規フォルダ`contents`を作成します（上記と同じような操作なので画像で示しません）．その後，ドラッグアンドドロップで`preamble.tex`を`contents`フォルダに移動します．最終的に，下の画像のようにフォルダとファイルが構成されていればOKです．
![create-contents](images/create-contents.png)
さて，`preamble.tex`に以下のように書き込みます．パッケージは`\usepackage[]{}`で読み込みます．`[]`部分はオプションを，`{}`部分はパッケージ名を指定します．

```{margin}
修士論文のフォーマットは，令和３（２０２１）年度茨城大学大学院理工学研究科履修要項p.37（以降，要項）によると，上下右左の余白がすべて20 mmと指定されています．
```

````{grid-item-card}
`preamble.tex`
^^^^^^^^^^^^^
```latex
\usepackage[top=20truemm,bottom=20truemm,left=20truemm,right=20truemm]{geometry} % 余白設定
\usepackage{graphicx}              % 図や画像などのグラフィックを扱う
\usepackage{booktabs}              % 論文に使用されるような表を出力
\usepackage{amsmath, amssymb}      % 数式表現パッケージ
\usepackage[dvipdfmx]{hyperref}    % しおりを作成
\usepackage{pxjahyper}             % 日本語のしおりを作成
```
````

`preamble.tex`の読み込みは，`main.tex`内で`\input{}`を使用して行います．

````{grid-item-card}
`main.tex`
^^^^^^^^^^^^^
```latex
\RequirePackage{plautopatch}
\RequirePackage[l2tabu, orthodox]{nag}

\documentclass[]{jlreq}

\input{contents/preamble.tex}

\begin{document}
Hello \LaTeX!
\end{document}
```
````