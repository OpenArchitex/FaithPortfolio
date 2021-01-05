---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "QuickSort (and the Dutch National Flag problem)"
subtitle: ""
summary: ""
authors: []
tags: []
categories: []
date: 2020-08-08T21:33:32-08:00
lastmod: 2020-08-08T21:33:32-08:00
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

I am currently taking Thompson River’s Data Structures and Algorithms course. To help me with my understanding, I am also doing [Algorithmic Toolbox](https://www.coursera.org/learn/algorithmic-toolbox/home/welcome) course on Coursera simultaneously. Short summary of this Coursera course: Insight into different algorithm design paradigm (something which I am weak at), for example, Greedy Algorithms, Dynamic Programming, Divide and Conquer, etc.

One of the famous sorting algorithms is the Quick Sort.

In the quick sort algorithm, we choose a pivot value. A partition function is used to return the correct position of this pivot value in the unsorted array. We have two sublists coming out of this: elements less than or equal to the pivot value; elements greater than the pivot value.

We do this process recursively until all the elements are sorted. On average, we have $O(nlogn)$ running time. That’s assuming that each partition splits the arrays into two equal halves. The choice of pivot is important and in the worst case, complexity of quicksort is $O(n^2)$ where the list is already sorted but the last element is chosen as a pivot.

When an array has few unique elements (many repeated elements), quick sort exhibits poor performance.

Why?

![dutch flag](https://images.unsplash.com/photo-1588680977516-def5c55965be?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=668&q=80)

Assume all equal elements in the array. Then the partition will have empty sublist on one side, and $n-1$ on the other. We will take $O(n^2)$ to sort this array of equal values.

The solution was to replace a 2-way partition with a 3-way partition with the following segments: elements less than pivot value; elements equal to the pivot value and elements greater than the pivot value. This is also called Dutch national flag problem.

The gist of the code:

It uses three pointers to keep track of the elements which are less than pivot (Left) value, more than pivot value (Right) and the current element with which we are examining $(i)$.

At any point in time, if the element that is examined is less than the pivot value, a swap is performed with the element at the position Left. And Left is incremented as more elements less than the pivot into this section. The same follows for element greater than pivot value in that a swap is performed with the element at position Right, expanding the territory of elements greater than pivot as it goes along. At the end Left and Right are indices which indicate where to partition on, where we will do divide and conquer from 0 to Left and Right to End while ignoring the elements within Left and Right.

I have written the code as part of this assignment [here](https://github.com/faithghlee/DataStructuresAndAlgorithms/blob/master/QuickSort/Sorting.java).

Well explained resource [here](https://algs4.cs.princeton.edu/23quicksort/). 
