---
layout: post
title: LaTeX Basics
date: 2021-04-15 18:06:00 --0000
permalink: /posts/latex-basics/
---

-------------------
Table of contents

* TOC
{:toc}

-------------------

## Sections and Subsections

### Changing the numbering of sections and subsections to letters
In appendices, researchers usually number their sections and subsections with letters rather than numbers. See [link](https://latex.org/forum/viewtopic.php?t=32632) for more information.

### Changing the numbering of tables and figures to correspond to sections
Some journals require tables and figures to be numbered in accordance with section numbers. For example, instead of being called Figure 16, the figure would be called Figure 4.3. See [link](https://tex.stackexchange.com/questions/85776/change-figure-numbering-for-appendix) for more information.

## Font
[Font size](https://texblog.org/2012/08/29/changing-the-font-size-in-latex/)

### Text color
```latex
\textcolor{red}{(how large)}
```

## Hyperlinks
[Reference](https://tex.stackexchange.com/questions/3033/forcing-linebreaks-in-url)
```
\PassOptionsToPackage{hyphens}{url}\usepackage{hyperref}
```

## Appendix
```LaTeX
\appendix

\section{Appendix}
```

## Lists

### Checklists
```LaTeX
\newlist{todolist}{itemize}{2}
\setlist[todolist]{label=$\square$}
\usepackage{pifont}
\newcommand{\cmark}{\ding{51}}%
\newcommand{\xmark}{\ding{55}}%
\newcommand{\done}{\rlap{$\square$}{\raisebox{2pt}{\large\hspace{1pt}\cmark}}%
\hspace{-2.5pt}}
\newcommand{\wontfix}{\rlap{$\square$}{\large\hspace{1pt}\xmark}}
% usage:
% \begin{todolist}
%   \item[\done] Frame the problem
%   \item Write solution
%   \item[\wontfix] profit
%   \end{todolist}
```