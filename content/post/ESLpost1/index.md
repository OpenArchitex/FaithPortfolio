---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "ESL Statistical Learning Theory (for own reference)"
subtitle: ""
summary: ""
authors: []
tags: []
categories: []
date: 2018-06-14T21:33:32-08:00
lastmod: 2018-06-14T21:33:32-08:00
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

From Page 11 of Elements of Statistical Learning

The linear model is given by

$\hat{Y} = \hat{\beta_0} + \sum_{j = 1}^{p}X_j \hat{\beta}_j$

and if we include the intercept (known as bias in machine learning) into the matrix of input vectors (X) (as a constant variable 1), then the linear model can be written in the vector form of inner product :

$\hat{Y} = X^{T} \hat{\beta}$.

"If the constant is included in X, then the hyperplane $(X , \hat{Y})$ includes the origin and is a subspace; if not it is an affine set cutting the Y-axis at the point (0, $ \hat{\beta}_0$)".

I just want to recap on some linear algebra in this post for myself.

A subspace of a vector space V is a subset H of V and satisfies the following conditions(or axioms):

a) The zero vector of V is in H

b) Closure under addition (ie. $u, v \in H ==> u + v \in H $)

c) Closure under multiplication (ie. $u \in H ==> \textbf{c}u \in H$ for some scalar c)

If the above is satisfied, H is itself a vector space.

If u, v are in vector space V, then the span by the two vectors (ie  W = span(u,v) ) is also a subspace of V.

Meaning of affine : A set $A \subset X$ is affine if for $x,y \in A$, $(1-t)x + ty \in A$ for some $t \in \textbf{R}$.

Full interpretation of the statement:

"If the constant is included in X, then the hyperplane $ (X , \hat{Y})$ includes (not pass through) the origin and is a subspace". Origin is (0,0). Then when a vector (or matrix of zeros) is multiplied by p+1 vector of coefficients, $\hat{Y}  = 0 $.  As such, the hyperplane includes the origin under the (p+2)th dimension (p+2 : Y is 1 dim, X is p + 1 after accounting for the constant) .
If the constant is not included, we can think of it as having the form of Y = mX + C (and therefore affine). When (X = 0, Y = 0) it passes through C. Think of it as when the plane passes through the origin, it intersects at C.
