---
layout: post
title: Tables in LaTeX
---

In order to create a table, I usually use ```\begin{table}```. And then ```\begin{tabular}{}``` where I can specify how many columns there are and what their alignments are. The common ones I use are ```{l c c}``` if there are three columns or ```{l *{5}{c} m{4cm}}``` if there are seven. In order to add notes to the table, ```\multicolumn``` is helpful. Below is an example:
```
\begin{table}
\begin{tabular}{l *{5}{c} m{4cm}}
\hline
\textbf{Code} & \textbf{States} & \textbf{DtR} & \textbf{CD} & \textbf{Signed} & \textbf{Enacted} & \textbf{Law Stipulations} \\
\hline
03 & Arkansas & yes (wp) & yes (wp) & & no & \\
\hline
\multicolumn{7}{l}{\footnotesize DtR: Duty to Retreat} \\
\end{tabular}
\end{table}
```
The end result is displayed as below:
{{ site.baseurl }}/images/config.png
