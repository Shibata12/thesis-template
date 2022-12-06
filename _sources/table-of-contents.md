# 目次（図表も含む）を作る
図表も含む目次は`\tableofcontents, \listoffigures, \listoftables`を`main.tex`に追加するだけで作成されます．
````{grid-item-card}
`main.tex`
^^^^^^^^^^^^^
```latex
\RequirePackage{plautopatch}
\RequirePackage[l2tabu, orthodox]{nag}

\documentclass[
  platex,           % 使用するコンパイラ（2022年11月現在のCloud LaTeXではplatexがデフォルトで使用されている）
  dvipdfmx,         % ドライバ
  fontsize=10pt,    % 欧文フォントサイズの指定
  jafontsize=10pt,  % 和文フォントサイズの指定
  titlepage,        % タイトルページを独立させて表示させる
  book,             % bookクラスを選択
]{jlreq}

\input{contents/preamble.tex}

\begin{document}
\input{contents/front-cover.tex}  % タイトル情報
\frontmatter                      % 概要，目次部分（ページ番号がローマ数字で記載）
\input{contents/0abstract.tex}    % 概要（日本語，英語）
\tableofcontents                  % 目次
\newpage
\listoffigures                    % 図目次
\newpage
\listoftables                     % 表目次
\end{document}

```
````