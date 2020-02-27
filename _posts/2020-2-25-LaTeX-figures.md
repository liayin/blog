---
layout: post
title: Figures in LaTeX
---

Here is an example of how figures should be embedded into LaTeX:

```
\begin{figure}[H]
\caption{States that Passed the Stand Your Ground Law}
\includegraphics[scale=0.8, center]{D:/Dropbox/StandYourGroundLawWriteup/figures_tables/model1} 
\ref{fig:1}
\end{figure}
```

Note that the `\ref{fig:1}` part should be added at the end, directly above the line that says `\end{figure}`.
