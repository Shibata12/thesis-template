# 図表を載せる
ここでは，図表の載せ方を確認します．
図は`figures`フォルダにまとめます．
図として読み込むことが可能な形式は`.png, .jpg, .jpeg, .pdf, .eps`です．
ファイルの構成と最終的な仕上がりは下の画像のようになります．
![figure-table](images/figure-table.png)
````{grid-item-card}
`2figure-table.tex`
^^^^^^^^^
```latex
\chapter{図表を載せる}
図\ref{fig:sin}のように参照できる．
同様に表\ref{tab:demo}のように参照できる．

\begin{figure}[h]
\includegraphics[scale=0.8]{figures/sample-figure.pdf}
\centering
\caption{正弦波}
\label{fig:sin}
\end{figure}

\begin{table}[h]
\centering
\caption{サンプル}
\label{tab:demo}
\begin{tabular}{@{}llr@{}}
\toprule
\multicolumn{2}{c}{Item} &            \\ \cmidrule(r){1-2}
Animal     & Description & Price (\$) \\ \midrule
Gnat       & per gram    & 13.65      \\
           & each        & 0.01       \\
Gnu        & stuffed     & 92.50      \\
Emu        & stuffed     & 33.33      \\
Armadillo  & frozen      & 8.99       \\ \bottomrule
\end{tabular}
\end{table}

```
````

`main.tex`は省略（`\input{contents/2figure-table.tex}`を`\input{contents/1introduction.tex}`の次の行に書き込むだけです）．

私が利用した図や表を作るツール
* 図の作成→[Inkscape](https://inkscape.org/ja/) インストールが必要です．オープンソースのベクター画像編集ソフトウェアです．
* 表の作成→[TablesGenerator.com](https://www.tablesgenerator.com/) インストール不要です．Web上でLaTeX用の表を作成できます．