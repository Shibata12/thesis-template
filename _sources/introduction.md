# 序論を作る
序論から本文を書いていきます．
ここでは，章(`\chapter{}`)，節(`\section{}`)，小節(`\subsection{}`)の書き方を確認します．
ファイルの構成と最終的な仕上がりは下の画像のようになります．
ちなみに，序論で始まったら，結論で終わります（最後の章は結論にしてください）．
![introduction](images/introduction.png)
````{grid-item-card}
`1introduction.tex`
^^^^^^^^^
```latex
\chapter{序論}
\section{背景}
ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．
\subsection{背景1}
ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．
\subsection{背景2}
ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．
\section{目的}
ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．
\section{構成}
ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．ここに文．
```
````

`main.tex`では`\pagenumbering{arabic}`と`\input{contents/1introduction.tex}`を追加します．

````{grid-item-card}
`main.tex`
^^^^^^^^^^^^^
```latex
\RequirePackage{plautopatch}
\RequirePackage[l2tabu, orthodox]{nag}

\documentclass[
  platex,           % 使用するコンパイラ（2023年2月時点のCloud LaTeXではplatexがデフォルトで使用されている）
  dvipdfmx,         % ドライバ
  fontsize=10pt,    % 欧文フォントサイズの指定
  jafontsize=10pt,  % 和文フォントサイズの指定
  book,             % bookクラスを選択
  openany,          % 章が変わったときの空白ページ自動挿入をしない
]{jlreq}

\input{contents/preamble.tex}

\begin{document}
\input{contents/front-cover.tex}  % タイトル情報
\pagenumbering{roman}             % ページ番号をローマ数字で記載
\input{contents/0abstract.tex}    % 要旨（日本語，英語）
\tableofcontents                  % 目次
\newpage
\listoffigures                    % 図目次
\newpage
\listoftables                     % 表目次
\newpage

\pagenumbering{arabic}            % ページ番号をアラビア数字
\input{contents/1introduction.tex}
\end{document}
```
````