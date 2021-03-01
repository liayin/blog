---
layout: post
title: Citations in LaTeX
date: 2020-04-03 17:06:00 --0000
---

There are multiple ways to incorporate citation information in LaTeX. One of them is BibTeX and another one is BibLaTeX.

First, store bibliography items in .bib file. Google Scholars will generate BibTeX style citations.

#### BibTeX

In the header of the file, add
```
\usepackage{natbib}
```

Add the following commands in the LaTeX document, usually at the end of the file:
```
\bibliography{bibfilename}
\bibliographystyle{bstfilename}
```

The usual bibliography style is "plain".

My own setup is:
```
\bibliography{D:/OneDrive/SYG Writeup/References}
\bibliographystyle{plain}
```

If you are going with the AEA style, you can write:

```
\bibliographystyle{aea}
```

Of course, you would have downloaded the *aea.bst* file from the AEA website.

#### BibLaTeX

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

My own setup is as follows:
```
\usepackage[authordate, backend = biber, sorting=nyt]{biblatex-chicago}
\addbibresource{D:/Dropbox/StandYourGroundLawWriteup/references.bib}
```
