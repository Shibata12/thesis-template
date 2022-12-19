# 概要を作る
表紙の次は概要(abstract)です．概要は日本語と英語で書きます．ファイルの構成と最終的な仕上がりは下の画像のようになります．
![abstract](images/abstract.png)
概要の内容は`0abstract.tex`に書き込みます．
````{grid-item-card}
`0abstract.tex`
^^^^^^^^^
```latex
% 日本語-------------------------
\begin{center}
  \textbf{
    {\LARGE ここに修士論文のタイトル\\}
  }
  \vspace{7mm}
  {\large 茨城大学大学院理工学研究科機械システム工学専攻\\
  柴田 侃汰\\}
  \vspace{7mm}
  {\large 概要}
\end{center}

ここに本文．ここに本文．ここに本文．ここに本文．ここに本文．ここに本文．ここに本文．ここに本文．ここに本文．
\newpage

% 英語-------------------------
\begin{center}
  \textbf{
   {\LARGE Master's thesis title here\\}
  }
  \vspace{7mm}
  {\large Major in Mechanical Systems Engineering,\\ Graduate School of Science and Engineering, Ibaraki University\\
  Kanta SHIBATA\\}
  \vspace{7mm}
  {\large Abstract}
\end{center}

Here is text. Here is text. Here is text. Here is text. Here is text. Here is text. Here is text. Here is text. Here is text.
```
````

`main.tex`では文書クラスのオプション（`\documentclass[]{}`の`[]`部分）も指定しました．

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
  openany,          % 章が変わったときの空白ページ自動挿入をしない
]{jlreq}

\input{contents/preamble.tex}

\begin{document}
\input{contents/front-cover.tex}  % タイトル情報
\frontmatter                      % 概要，目次部分（ページ番号がローマ数字で記載）
\input{contents/0abstract.tex}    % 概要（日本語，英語）
\end{document}

```
````