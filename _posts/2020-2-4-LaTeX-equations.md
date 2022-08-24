---
layout: post
title: LaTeX Equations
date: 2020-02-04 17:05:00 --0000
permalink: /posts/latex-equations/
---

Table of Contents
* TOC
{:toc}

# Multiline Parentheses/Brackets
```
\usepackage{amsmath}
\begin{align}
    V^*_i = X_i \beta_i &+ \varepsilon_{1, i}, Victim_i = 1(V^*_i > 0) \\
    O^*_i = X_i \beta_i &+ \varepsilon_{2, i}, Offender_i = 1(O^*_i > 0) \\
    \begin{pmatrix}
        \varepsilon_1 \\
        \varepsilon_2
    \end{pmatrix} &\sim N \begin{bmatrix} \begin{pmatrix}
        0 \\
        0
    \end{pmatrix}, \begin{pmatrix}
        1 & \rho \\
        \rho & 1
    \end{pmatrix} \end{bmatrix}
\end{align}
``` 

Output is below:
![Multiline Parentheses](/images/multiline_parentheses.jpg/)

# Labeling Equations
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

# Bold Font in Math Mode
The `\mathbf` command can only be used for non-italic math content, but the `\bm` command from the package `bm` provides a good alternative. It also helps with applying bold font to Greek letters. `\boldsymbol{\beta}` gives us $$\boldsymbol{\beta}$$. See details [here](https://tex.stackexchange.com/questions/22643/how-to-write-letters-in-bold-in-the-math-mode).

# Large bracket
```
begin{cases}
\\
end{cases}
```