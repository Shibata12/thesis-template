# 謝辞を作る
謝辞は`acknowledgments.tex`に書き込みます．
````{grid-item-card}
`acknowledgments.tex`
^^^^^^^^^^^^^
```latex
\newpage
\section*{謝辞}
謝辞
\addcontentsline{toc}{chapter}{謝辞} % 目次に謝辞を追加
\newpage
```
````

`main.tex`は省略（`\input{contents/acknowledgments.tex}`を書き込むだけです）．