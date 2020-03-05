---
layout: post
title: Figures in LaTeX
---

Here is an example of how figures should be embedded into LaTeX:

```
\usepackage[capposition=top]{floatrow}
```

```
\begin{figure}[H]
  \caption{States that Passed the Stand Your Ground Law}
  \includegraphics[scale=0.8, center]{D:/Dropbox/StandYourGroundLawWriteup/figures_tables/model1} 
  \label{fig:1}
  \floatfoot{A note}
\end{figure}
```

Note that the `\label{fig:1}` part should be added after the line with `\includegraphics`.

The package `floatrow` can facilitate adding a note to the figure at the end.

![Figure](/images/figure.jpg "Figure")
