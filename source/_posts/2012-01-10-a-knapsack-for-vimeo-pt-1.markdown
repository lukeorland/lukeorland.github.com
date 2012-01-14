---
layout: post
title: "a knapsack for Vimeo, part 1"
date: 2012-01-10 09:43
comments: true
categories: 
published: false
---

The Vimeo Premium account allows a user to upload up to 5 GB of videos per week. The size of a video cannot be distributed across subsequent weeks. Unused upload space does not roll over to following weeks. My goal is to the most cost-effective use of the Vimeo Premium account by uploading as close to the full 5 GB as possible every week.

As it turns out, selecting a subset of available video files that combine for the maximum fit within a certain limit is an instance of the [0-1 knapsack problem](http://en.wikipedia.org/wiki/Knapsack_problem#0-1_knapsack_problem). I have taken a crack at implementing a solution for this problem. First, I wrote a 0-1 knapsack solver module (in Python) as well as a command-line Python script that utilizes the solver to determine the optimal list of video files to upload for the week.

<!-- TODO: change value-ratio to profit -->

# Search space
To understand how this is a difficult problem to solve, consider the number of possible combinations of files that could comprise an optimal subset (that would fit as tightly as possible within a size limit). Each file is either in the optimal subset or not. That means there are $2^N$ possible combinations of candidate files. For a set of 40 files, there would be $2^40 = 1,099,511,627,776$ from which an exact optimal subset would be identified.

# Solution
My first solution uses a pure branch-and-bound recursive algorithm. The weight and profit of each file is its size in bytes, and the capacity of the knapsack is 5000000000 bytes. This approach is much too inefficient, likely due to repeated evaluations of the same subsets in rearranged order.

# Next step
According to [], branching and bounding is not efficient when the weights and profits are close in value, which is the situation for this problem where each item has the same weight and profit. Alternatively, a dynamic programming algorithm can be employed. [] also state that the dynamic programming approach is best suited for integer values of low magnitude.
