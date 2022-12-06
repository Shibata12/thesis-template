# 参考文献を作る
参考文献は`references.bib`というbibファイルに書き込みます．例えば，[LaTeX超入門　ゼロからはじめる理系の文書作成術](https://bookclub.kodansha.co.jp/product?item=0000343850)をbib形式で`references.bib`に以下のように書き込みます．

````{grid-item-card}
`references.bib`
^^^^^^^^^^^^^
```latex
@book{latex,
  author = "水谷, 正大",
  title = "LaTeX超入門 : ゼロからはじめる理系の文書作成術",
  year = "2020",
  publisher = "講談社",
}
```
````

これを例えば以下のように`\cite{latex}`で参照することができます．

````{grid-item-card}
`acknowledgments.tex`
^^^^^^^^^^^^^
```latex
\newpage
\section*{謝辞}
\LaTeX は\cite{latex}を参考にしました．
\addcontentsline{toc}{chapter}{謝辞} % 目次に謝辞を追加
\newpage
```
````

`main.tex`には`\bibliographystyle{junsrt}`と`\bibliography{contents/references.bib}`を書き込みます．

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

\mainmatter                       % 以下，本文（ページ番号がアラビック数字で記載される）
\input{contents/1introduction.tex}
\input{contents/2figure-table.tex}
\input{contents/acknowledgments.tex}  % 謝辞
\bibliographystyle{junsrt}                % 参考文献のスタイル
\bibliography{contents/references.bib}    % 参考文献を表示
\addcontentsline{toc}{chapter}{参考文献}  % 目次に参考文献を追加
\end{document}
```
````

すると，下の画像のように（小さくて見づらいですが）参考文献が自動で作成されます．
![references](images/references.png)