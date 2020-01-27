---
layout: post
title: Tables in LaTeX
---

The contents of a table usually start with an alignment. I usually use ```\begin{table}```. And then ```\begin{tabular}{}``` where I can specify how many columns there are and what their alignments are. The common ones I use are ```{l c c}``` if there are three columns or ```{l *{5}{c} m{4cm}}``` if there are seven. I usually add a ```\caption{}``` after ```\end{tabular}``` to add notes to the table.
