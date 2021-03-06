### 1580.Put-Boxes-Into-the-Warehouse-II

此题的本质是贪心法。我们首先需要有这样一个概念，在最终的排列中，高的箱子会摆放在靠两边的位置。越高的箱子会摆得越靠边。

于是我们从高到低遍历每一个箱子，查看是否能fit仓库的第一个或者最后一个。如果两个都fit，那我们挑一个较矮的仓库。于是我们就把这个箱子安置好了。于是我们将指向仓库两头的指针做必要的移动，将其中一个挪开已经放置箱子的位置朝中间进发。

然后我们考察下一个箱子。因为这个箱子比刚才的矮，所以必然可以穿越之前那个箱子所在的仓库，等价于忽略掉warehouse的一个边缘元素。于是我们又面对一样的问题，此时的箱子能否fit仓库的第一个或者最后一个？如果两个都fit，那么我们再挑一个较矮的仓库。于是双指针中的一个又可以往中间移动。每移动一次就代表安置了一个箱子。

当箱子都遍历结束，或者双指针i>j的时候，就完成了探索。
