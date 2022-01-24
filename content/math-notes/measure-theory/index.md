---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "Riemann Integrals"
subtitle: ""
summary: "Notes on Riemann Integrals"
authors: []
tags: []
categories: []
date: 2021-04-02T17:46:29-04:00
lastmod: 2021-04-02T17:46:29-04:00
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.

image: 
  placement: 1
  caption: "ff"
  focal_point: ""
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---
# Setup


Let $f[a,b] \rightarrow$ R be a bounded real function. Partition the interval [a,b] into 
\begin{equation}
a = a_0 < a_1 < ... < a_n = b
\end{equation}

Call such a partition P. For each subinterval $[x_{i-1}, x_i]$ of this P, 

Define the lower and upper Riemman sum as follows: 

\begin{equation}
L(P, f) = \sum_{i=1}^n m_i*(x_i-x_{i-1}), \\
U(P,f) = \sum_{i=1}^n M_i*(x_i-x_{i-1}) \\ 
\end{equation}

where $m_i = \\{ \inf f(x) : x \in [x_{i-1}, x_i] \\}$, $M_i = \\{\sup f(x) : x \in [x_{i-1}, x_i]\\}$


## Refinement of partition 
Definition 7.2.2 (As in reference) A partition Q is a refinement of a partition P if Q contains all of the points of P; that is $ P \subseteq Q $. 



References:

Abbott, S. (2015). Understanding Analysis. Springer New York. https://doi.org/10.1007/978-1-4939-2712-8
