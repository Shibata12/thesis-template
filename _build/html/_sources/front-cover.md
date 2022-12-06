# 表紙を作る
まずは，表紙から作っていきます．表紙に載せる項目は要項に従います．ファイルの構成と最終的な仕上がりは下の画像のようになります．
![front-cover](images/front-cover.png)
表紙に載せる情報は`front-cover.tex`に書き込みます．その後，`front-cover.tex`を`main.tex`で読み込みます．
````{grid-item-card}
`front-cover.tex`
^^^^^^^^^
```latex
\begin{titlepage}
  \begin{center}
    \vspace*{20mm} % *を付けるとページ頭・ページ末でも空白が出力される．
    {\LARGE 修　士　学　位　論　文\\}
    \vfill
    \textbf{
      {\huge ここに修士論文のタイトル}
    }
    \vfill
    {\LARGE 令和　４　年度\\}
    \vfill
    {\LARGE 茨城大学大学院理工学研究科\\}
    \vfill
    {\LARGE 機械システム工学専攻\\}
    {\LARGE 柴田 侃汰\\}
    \vspace*{20mm}
  \end{center}
\end{titlepage}
```
````

````{grid-item-card}
`main.tex`
^^^^^^^^^^^^^
```latex
\RequirePackage{plautopatch}
\RequirePackage[l2tabu, orthodox]{nag}

\documentclass[]{jlreq}

\input{contents/preamble.tex}

\begin{document}
\input{contents/front-cover.tex}  % タイトル情報
\end{document}
```
````