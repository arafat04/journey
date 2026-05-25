### How to build 2-d range tree and time and space complexity of the build:

The question range query solves: 

We have a scatter plot in 2-d dimension and bunch of points are scattered all over the place. Now if some asks, **"Hey I want to find all the points that fall in this rectangular box - between $x_1$ and $x_2$ on the $x$-axis and, and between $y_1$ and $y_2$ on the $y$ axis."**

**How to build the data strucuture to solve this query:**

*The core idea: apply divide and conquer in Two Dimensions.* 

We can not build a 1D range tree over $x$ coordinates only as we have to filter by the $y$ coordinates as well. This can be done by building a **1D range tree inside another 1D range tree.** This is done by doing this:

1. First, we organize by $x$-coordinate. We build a binary search tree where we split points down the middle by their x-value. This is called the $x$-tree. Each node in this tree represents a vertical band of space.
2. Then, for *each band*, we organize by $y$-coordinate. We build a separate sorted list (or tree) of **all the points in that band**, sorted by their y values. This is the y-tree for that band.


Let's walk through an example:
we have a tree containing
