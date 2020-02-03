---
layout: post
title: Tables in LaTeX
---

In order to create a table, the most common way is to use ```\begin{table}```. And then ```\begin{tabular}{}``` where we can specify how many columns there are and what their alignments are. The common ones used are ```{l c c}``` if there are three columns or ```{l *{5}{c} m{4cm}}``` if there are seven. In order to add notes to the table, ```\multicolumn``` is helpful. Below is an example:
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
![Table](/images/table.jpg "Table")

If we want to add notes, we could use three part tables. In the header, we could add ```\usepackage{threeparttable}```. In the body of the text, we could use
```
\begin{table}[H]
\label{tab:gun}
\centering
\begin{threeparttable}
\caption{Comparing Weapon Percentage between First-Degree and Second-Degree Murder}
	\begin{tabular}{*{3}{c}}
		\hline \hline
		First-Degree Murder & Second-Degree Murder & P-Value (One-Sided) \\
		\hline
		12.93\% & 15.28\% & .0269 \\
		\hline \hline
	\end{tabular}
\begin{tablenotes}[flushleft]
\small
\item	12.93\% of First-Degree Murder victims have a weapon compared to 15.28\% of Second-Degree Murder victims. If we hypothesize that the percentage for a Second-Degree Murder is higher, the p-value for the one-sided test comparing the two groups is .0269.
\end{tablenotes}
\end{threeparttable}
\end{table}
```

The resulting table would look like:

![Table2](/images/table2.jpg "Table 2")

With tables generated from software, we can use ```\input{D:/Research/Data/NCVS/perc_def.tex}```. In order to add notes, we could use 
```\leftskip=2cm\rightskip=2cm```, and for the rest of the article, we should add ```\leftskip=0cm\rightskip=0cm```

Here is an example:
```
\input{D:/Research/Data/NCVS/perc_def.tex}
\vspace{1mm}
\leftskip=2cm\rightskip=2cm
In the category of something taken, only 3.3\% of crime cases face defense. For harassment/abusive language, 33.2\% of crime cases face defense.
\vspace{6mm}
```

The resulting table would look like:

![Table3](/images/table3.jpg "Table 3")
