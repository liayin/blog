---
layout: post
title: LaTeX Beamer
date: 2022-12-9 1:22:01 --0000
permalink: /posts/latex-beamer/
---

Do you know that LaTeX can be used to make presentation slides? The document class for presentation slides is "beamer". In PowerPoint, everything is point and click. In LaTeX beamer, everything is controlled by code, so there is possibly a learning curve. However, once you know the basics, the process of creating slides is very pleasant. In this sense, using LaTeX beamer to create slides is similar to using LaTeX to create documents. 

This article assumes that you have a basic understanding of LaTeX beamer. It contains tips for using more advanced techniques in LaTeX beamer. It is written by me as notes to refer back to. Hope they are helpful to you as well.

## Hyperlinks
Hyperlinks can be used to jump from one slide to another. It is very useful if you have some optional slides that you wish to have on hand in case audience members ask you for more details. You would like to jump to the optional slide and back. Here is an example of two slides that are linked to each other to-and-back.

```LaTeX
\usepackage{hyperref}

\begin{frame}{Data}\label{data}
\hyperlink{victim_segment}{\beamerbutton{Details}}
\end{frame}

\begin{frame}{Victim Segment}\label{victim_segment}
\hyperlink{data}{\beamerbutton{Back}}
\end{frame}
```