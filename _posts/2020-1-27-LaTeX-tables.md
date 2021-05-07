---
layout: post
title: Tables in LaTeX
date: 2020-01-27 17:05:00 --0000
---

### Basic Tables
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

### Adding Notes
If we want to add notes, we could use three part tables. In the header, we could add ```\usepackage{threeparttable}```. In the body of the text, we could use
```
\begin{table}[H]
\caption{Comparing Weapon Percentage between First-Degree and Second-Degree Murder}
\label{tab:gun}
\centering
\begin{threeparttable}
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

Note that we should always put `\label` after `\caption` because counter would only be reset by `\refstepcounter` after a call to `\caption`.

### Importing Tables from another File
With tables generated from software, we can use ```\input{D:/Research/Data/NCVS/perc_def.tex}```. In order to add notes, we could use
```\leftskip=2cm\rightskip=2cm```, and for the rest of the article, we should add ```\leftskip=0cm\rightskip=0cm```

Here is an example:
```
\input{D:/Research/Data/NCVS/perc_def.tex}
\vspace{1mm}
\leftskip=2cm\rightskip=2cm
In the category of something taken, only 3.3\% of crime cases face defense. For harassment/abusive language, 33.2\% of crime cases face defense.
\vspace{6mm}
\leftskip=0cm\rightskip=0cm
```

The resulting table would look like:

![Table3](/images/table3.jpg "Table 3")

[Click link for a good reference.](https://www.overleaf.com/learn/latex/Tables)

[Click here](https://tex.stackexchange.com/questions/28333/continuous-v-per-chapter-section-numbering-of-figures-tables-and-other-docume) if you would like table numbering to follow/unfollow the chapter headings.

### Multirow Table
```
\usepackage{multirow}

\begin{table}[H]\centering
	\caption{Comparison between States With Law and States Without Law (2000-2015)}
	\vspace{1mm}
	\label{sum2}
	\begin{tabular}{c *{5}{c} *{2}{c}}
		\hline\hline
		State and Year & \multicolumn{5}{c}{Summary Statistics} & \multicolumn{2}{c}{Comparison} \\
		 &  Count & Max & Min & Mean & SD & Degrees of Freedom & t \\
		\hline
		Without Law & 575 & 13.25 &        0.62 &        4.19&         2.29&    \multirow{2}{*}{775} & \multirow{2}{*}{-6.47***}    \\
		With Law & 200 & 14.56 & .9 & 5.39 & 2.08 &      &      \\
		\hline
		\multicolumn{8}{l}{\footnotesize \textit{t} statistics in parentheses}\\
		\multicolumn{8}{l}{\footnotesize * \(p<0.10\), ** \(p<0.05\), *** \(p<0.01\)}\\
	\end{tabular}
	\vspace{-4mm}
	\caption*{\footnotesize The average murder rates for state-years without law and with law are statistically significantly different. The average murder rate for state-years without the law is 4.22 and that for state-years with the law is 5.35.}
\end{table}
```

Resulting table:
![Multirow Table](/images/multirow_table.jpg "Multirow Table")

### Multipage Table
```
\usepackage{longtable}
\usepackage{lipsum} % just for dummy text- not needed for a longtable

\begin{document}
\lipsum[1]
\lipsum[1]
\lipsum[1]

%\begin{table}[h] 
%\centering
\begin{longtable}{| p{.20\textwidth} | p{.80\textwidth} |} 
\caption{SYG Law Status for All States\label{tbl: all_states}} \\
\hline
Header \\ \hline
\endhead % all the lines above this will be repeated on every page
foo & bar \\ \hline 
foo & bar \\ \hline
foo & bar \\ \hline
foo & bar \\ \hline
foo & bar \\ \hline
foo & bar \\ \hline
foo & bar \\ \hline
foo & bar \\ \hline
foo & bar \\ \hline
foo & bar \\ \hline
foo & bar \\ \hline
\caption{Your caption here} % needs to go inside longtable environment
\label{tab:myfirstlongtable}
\end{longtable}
%\end{table} 

Table \ref{tab:myfirstlongtable} shows my first longtable.
\end{document}
```

Reference [here](https://tex.stackexchange.com/questions/26462/make-a-table-span-multiple-pages), [here](https://tex.stackexchange.com/questions/11380/how-to-repeat-top-rows-column-headings-on-every-page), and [here](https://tex.stackexchange.com/questions/219138/how-to-have-a-caption-on-top-of-longtable/219145).