---
layout: post
title: Citation in LaTex
---

I use biber for citation. In the header file, I have 
```
\usepackage[authordate, backend = biber, sorting = nyt]{biblatex-chicago}
\addbibresource{D:/Dropbox/StandYourGroundLawWriteup/references.bib}
```
and then at the end of the file, before ```\end{document}``` I have ```\printbibliography```

In order to enter bibliography items in the footnote, I write ```\footnote{\cite{bobo2007}}```
