---
layout: post
title: "a knapsack for Vimeo"
date: 2012-01-10 09:43
comments: true
categories: 
published: true
---

The Vimeo Premium account allows a user to upload up to 5 GiB of videos per week. The size of a video cannot be distributed across subsequent weeks. Unused upload space does not roll over to following weeks. My goal is to make the most cost-effective use of the Vimeo Premium account by uploading as close to the full 5 GiB as possible every week.

As it turns out, selecting a subset of available video files that combine for the maximum fit within a certain limit is an instance of the [0-1 knapsack problem](http://en.wikipedia.org/wiki/Knapsack_problem#0-1_knapsack_problem). I wrote a 0-1 knapsack solver module (in Python) as well as a command-line Python script that utilizes the solver to determine the optimal list of video files to upload for the week.

## Search space
To understand how this is a difficult problem to solve, consider the number of possible combinations of files that could comprise a unique subset. Each file is either in each subset or not. That means there are 2^N possible combinations of candidate files. For a set of 40 files, there would be 2^40 = 1,099,511,627,776 from which an exact optimal subset would be identified.

# Solver
My first solution uses a pure branch-and-bound recursive algorithm. The weight and profit of each file is its size in bytes, and the capacity of the knapsack is 5&times;2^30 = 5,368,709,120 bytes. This approach is much too inefficient, likely due to repeated evaluations of the same subsets in rearranged order.

## Next step
Alternatively, a well-known dynamic programming algorithm can be employed. I implemented this method, which indeed finds the exact solution much more quickly, in O(nW) time and O(W) space, where n is the number of candidate files, and W is the size limit.

The code I have written can be found at [github.com/lukeorland/maxfit](https://github.com/lukeorland/maxfit).

*edited Fri Jan 27 13:59:37 EST 2012*
