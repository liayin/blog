---
layout: post
title: Citations in LaTeX
date: 2020-04-03 17:06:00 --0000
permalink: /posts/latex-citations/
---

There are multiple ways to incorporate citation information in LaTeX. One of them is BibTeX and another one is BibLaTeX.

First, store bibliography items in .bib file. Google Scholars will generate BibTeX style citations.

* TOC
{:toc}


## BibTeX

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

### AEA style
If you are going with the AEA style, you can write:

```
\bibliographystyle{aea}
```

Of course, you would have downloaded the *aea.bst* file from the AEA website.

### Cite webpages
Citation of webpages in natbib should be the following format ([ref](https://tex.stackexchange.com/questions/157291/natbib-and-website-citation)):
```r
@Misc{Tho98w,
  Author = "Len Thomas",
  Title  = "\emph{Statistical power analysis software}",
  Note   = "\url{http://www.forestry.ubc.ca/conservation/power/}
           [Accessed: Whenever]",
  year = 1998,
}
```

### Abbreviations for author names
```LaTeX
% use abbreviation for author name
\newcommand\mycitep[1]{\citepalias[\citeyear{#1}]{#1}}
\newcommand\mycitet[1]{\citetalias{#1} (\citeyear{#1})}  
\defcitealias{aurora1994summary}{Aurora PD}
\defcitealias{fbi2012convert}{FBI}
```

## BibLaTeX

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

# Law Citations

Citing statutes:
```
\footnote{}
```