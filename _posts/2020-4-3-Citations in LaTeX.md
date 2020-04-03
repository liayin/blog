---
layout: post
title: Citations in LaTeX
---

There are multiple ways to incorporate citation information in LaTeX. One of them is BibTeX and another one is BibLaTeX.

BibTeX

Store bibliography items in .bib file.

Add the following commands in the LaTeX document:
```
\bibliography{bibfilename}
\bibliographystyle{bstfilename}
```

The usual bibliography style is "plain".


BibLaTeX

```
\usepackage{biblatex}
\addbibresource{database.bib}
\begin{document}
\printbibliography
\end{document}
```

If you're using TeXstudio to edit LaTeX files, make sure to change the configurations to allow Biber to compile bibliography rather than BibTeX. The way to do it is as follows:

Options -> Configure TeXstudio -> Build -> Default Bibliography Tool -> Biber

The compiling process goes like this:

Compile
Bibliography
Compile
