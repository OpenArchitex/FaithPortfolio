---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "Statistical Learning Theory (for own reference)"
subtitle: ""
summary: ""
authors: []
tags: []
categories: []
date: 2018-06-18T21:33:32-08:00
lastmod: 2018-06-18T21:33:32-08:00
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---

For my own reference:

Given $X \in R^{p}$ as the real-valued random input vector and $Y \in R^{p}$ is a real valued quantitative output, our objective is to seek a function f(x) for which we can predict the output based on the input. To do this, we would need a loss function and find f(x) such that this loss function is minimized.

The squared error loss function is the obvious choice. ie. Penalize ($ (Y-f(x)^2)$
To see what we will choose f, let EPE(f) be the expected prediction error from f(x).
$ EPE(f)  = E(Y-f(x))^2) \\ = E_X E_{Y|X}((Y-f(x))^2|X) $
Given X = x, $ E_X (E_{Y|X}(Y-f(x))^2|X = x) = E_{Y|X}((Y-f(x))^2|X = x)$. From here, we see that it suffices to minimize the function pointwise (because it has a quadratic form). If we expand $ E_{Y|X}((Y-f(x))^2|X = x)$ out and let f(x) = c, then we see that we have a quadratic function : $ E_{Y|X}((Y-c)^2|X = x) \\ = E(Y^2|X = x ) - 2c E(Y|X = x) + c^2$. Under the quadratic form of $ ax^2 + bx + c$, we have $ a  = E(Y^2|X = x) $, $ b = E(Y|X = x)$ and the minimum of c is given by $ c = -b/2a = E(Y|X=x)$.
This conditional expectation is the regression function.
