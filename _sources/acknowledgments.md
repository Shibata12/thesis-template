# 謝辞を作る
謝辞は`acknowledgments.tex`に書き込みます．
![](images/acknowledgments.png)
````{grid-item-card}
`acknowledgments.tex`
^^^^^^^^^^^^^
```latex
\newpage
\phantomsection
\addcontentsline{toc}{chapter}{謝辞}
\section*{謝辞}
謝辞を書く．
```
````

`main.tex`は省略（`\input{contents/acknowledgments.tex}`を`\input{contents/2figure-table.tex}`の次の行に書き込むだけです）．