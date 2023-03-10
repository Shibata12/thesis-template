# 参考文献を作る
参考文献は`references.bib`というbibファイルに書き込みます．例えば，[LaTeX超入門　ゼロからはじめる理系の文書作成術](https://bookclub.kodansha.co.jp/product?item=0000343850)をbib形式で`references.bib`に以下のように書き込みます．
bibファイルの書き方は，[このサイト](http://www.yamamo10.jp/yamamoto/comp/latex/bibtex/bibtex.html)がわかりやすいです．

````{grid-item-card}
`references.bib`
^^^^^^^^^^^^^
```latex
@book{latex,
  author = "水谷 正大",
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
\phantomsection
\addcontentsline{toc}{chapter}{謝辞}
\section*{謝辞}
謝辞を書く．
\LaTeX は\cite{latex}を参考にしました．
```
````

`main.tex`には

* `\phantomsection`
* `\addcontentsline{toc}{chapter}{参考文献}`
* `\bibliographystyle{junsrt}`
* `\bibliography{contents/references.bib}`

を書き込みます．

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
\input{contents/2figure-table.tex}

\input{contents/acknowledgments.tex} % 謝辞

\newpage
\phantomsection
\addcontentsline{toc}{chapter}{参考文献}  % 目次に参考文献を追加
\bibliographystyle{junsrt}                % 参考文献のスタイル
\bibliography{contents/references.bib}    % 参考文献を表示
\end{document}
```
````

すると，下の画像のように（小さくて見づらいですが）参考文献が自動で作成されます．
![references](images/references.png)