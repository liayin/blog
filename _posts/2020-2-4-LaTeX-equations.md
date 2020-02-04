---
layout: post
title: LaTeX Equations
---

The format for creating LaTeX equations is usually ```\begin{equation}\end{equation}```. In order to label the equation, the common method is to write ```\label{eq:1}``` and then later refer to it as ```ref{eq:1}```. See code below for an example:

```
Second derivative is:
\begin{align}
\frac{\partial ^2 A(a)}{\partial a^2} &= p_{aa} \delta F + p_a \delta F_a + p_a F_a + p F_{aa} + L_{aa} - p_{aa} L - p_a L_a - p_a L_a - p L_{aa} \\
&= p_{aa}(\delta F - L) + (1 + \delta)p_a F_a + p F_{aa} + (1 - p)L_{aa} - 2 p_a L_a \label{eq:1}
\end{align}
```

The label is not visible in text:
![derivative](/images/derivative.jpg "derivative")

Reference to this equation would be:
```
Based on discussions after Equation \ref{eq:1}, $a_{\delta} < 0$.
```

The text will display as:
![reference](/images/reference.jpg "reference")
