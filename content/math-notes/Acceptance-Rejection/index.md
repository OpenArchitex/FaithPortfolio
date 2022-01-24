---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "Acceptance Rejection Sampling"
subtitle: ""
summary: "Review of acceptance rejection sampling"
authors: []
tags: []
categories: []
date: 2022-01-21T17:46:29-04:00
lastmod: 2021-01-21-02T17:46:29-04:00
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

There are many distributions for which the inverse-transform method will not give us the required random variable (ie inversing the CDF of some distribution to get a r.v). Let's call such a distribution $f$, which is the target density. Suppose there exists another distribution $g$ for which we know the ratio of $f/g$ is bounded by M for all values in the support of the two functions and the support of both distributions are compatible ($f(x)>0$ when $g(x)>0$). 

Then X can be drawn as follows: 
1. Generate a $U\sim U(0,1)$ r.v. 
2. Generate a Y coming from the g. 
3. If \begin{equation} U \leq (1/M) (f(Y)/g(Y)) \end{equation}, we accept this value of Y as our value for X. 

Exercise 2.5 The probability of accepting Y is 1/M. 

\begin{equation}
P(U \leq \frac{f(Y)}{Mg(Y)}) =  \int_0^{\frac{f(Y)}{Mg(Y)}}\int_{-\infty}^{\infty} g(y) du dy
\end{equation}
\begin{equation}= \int_{-\infty}^{\infty} \int_0^{\frac{f(Y)}{Mg(Y)}} du g(y) dy
= \frac{1}{M} \int_{-\infty}^{\infty} f(y) dy
= \frac{1}{M}
\end{equation}

The Y is a random variable here, hence the double integrals. U is a uniform r.v. 





References:

Introduction to Monte Carlo Methods with R

