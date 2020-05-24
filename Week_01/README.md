# LeetCode

| #                                                            | 题目                           | 标签        | 难度 | 时间       |
| ------------------------------------------------------------ | ------------------------------ | ----------- | ---- | ---------- |
| [283](https://leetcode-cn.com/problems/move-zeroes/)         | [移动零](283/README.md)        | 数组 双指针 | 简单 | 2020-05-24 |
| [11](https://leetcode-cn.com/problems/container-with-most-water/) | [盛最多水的容器](11/README.md) | 数组 双指针 | 中等 | 2020-05-24 |
| [70](https://leetcode-cn.com/problems/climbing-stairs/)      | [爬楼梯](70/README.md)         | 动态规划    | 简单 | 2020-05-24 |
| [15](https://leetcode-cn.com/problems/3sum/)                 | [三数之和](15/README.md)       | 数组 双指针 | 中等 | 2020-05-24 |



# 数据结构

## Common Data Structure Operations

![image-20200524233729758](https://i.loli.net/2020/05/24/Xkyf3YnCVsGPhpO.png)

## Array Sorting Algorithms

![image-20200524233838821](https://i.loli.net/2020/05/24/4QqPkKEmyNvFZdz.png)

https://algs4.cs.princeton.edu/cheatsheet/

## Sorting.

 The table below summarizes the number of compares for a variety of sorting algorithms, as implemented in this textbook. It includes leading constants but ignores lower-order terms.



> | ALGORITHM          | CODE                                                         | IN PLACE | STABLE | BEST         | AVERAGE      | WORST        | REMARKS                                                  |
> | ------------------ | ------------------------------------------------------------ | -------- | ------ | ------------ | ------------ | ------------ | -------------------------------------------------------- |
> | **selection sort** | [Selection.java](https://algs4.cs.princeton.edu/21elementary/Selection.java.html) | ✔        |        | ½ *n* 2      | ½ *n* 2      | ½ *n* 2      | *n* exchanges; quadratic in best case                    |
> | **insertion sort** | [Insertion.java](https://algs4.cs.princeton.edu/21elementary/Insertion.java.html) | ✔        | ✔      | *n*          | ¼ *n* 2      | ½ *n* 2      | use for small or partially-sorted arrays                 |
> | **bubble sort**    | [Bubble.java](https://algs4.cs.princeton.edu/21elementary/Bubble.java.html) | ✔        | ✔      | *n*          | ½ *n* 2      | ½ *n* 2      | rarely useful; use insertion sort instead                |
> | **shellsort**      | [Shell.java](https://algs4.cs.princeton.edu/21elementary/Shell.java.html) | ✔        |        | *n* log3 *n* | unknown      | c *n* 3/2    | tight code; subquadratic                                 |
> | **mergesort**      | [Merge.java](https://algs4.cs.princeton.edu/22mergesort/Merge.java.html) |          | ✔      | ½ *n* lg *n* | *n* lg *n*   | *n* lg *n*   | *n* log *n* guarantee; stable                            |
> | **quicksort**      | [Quick.java](https://algs4.cs.princeton.edu/23quicksort/Quick.java.html) | ✔        |        | *n* lg *n*   | 2 *n* ln *n* | ½ *n* 2      | *n* log *n* probabilistic guarantee; fastest in practice |
> | **heapsort**       | [Heap.java](https://algs4.cs.princeton.edu/24pq/Heap.java.html) | ✔        |        | *n* †        | 2 *n* lg *n* | 2 *n* lg *n* | *n* log *n* guarantee; in place                          |

​                                                                                                                                                                              † *n* lg *n* if all keys are distinct

## Priority queues.

 The table below summarizes the order of growth of the running time of operations for a variety of priority queues, as implemented in this textbook. It ignores leading constants and lower-order terms. Except as noted, all running times are worst-case running times.



> | DATA STRUCTURE     | CODE                                                         | INSERT     | DEL-MIN        | MIN  | DEC-KEY    | DELETE         | MERGE   |
> | ------------------ | ------------------------------------------------------------ | ---------- | -------------- | ---- | ---------- | -------------- | ------- |
> | **array**          | [BruteIndexMinPQ.java](https://algs4.cs.princeton.edu/24pq/BruteIndexMinPQ.java.html) | 1          | *n*            | *n*  | 1          | 1              | *n*     |
> | **binary heap**    | [IndexMinPQ.java](https://algs4.cs.princeton.edu/24pq/IndexMinPQ.java.html) | log *n*    | log *n*        | 1    | log *n*    | log *n*        | *n*     |
> | ***d\*-way heap**  | [IndexMultiwayMinPQ.java](https://algs4.cs.princeton.edu/99misc/IndexMultiwayMinPQ.java.html) | log*d* *n* | *d* log*d* *n* | 1    | log*d* *n* | *d* log*d* *n* | *n*     |
> | **binomial heap**  | [IndexBinomialMinPQ.java](https://algs4.cs.princeton.edu/99misc/IndexBinomialMinPQ.java.html) | 1          | log *n*        | 1    | log *n*    | log *n*        | log *n* |
> | **Fibonacci heap** | [IndexFibonacciMinPQ.java](https://algs4.cs.princeton.edu/99misc/IndexFibonacciMinPQ.java.html) | 1          | log *n* †      | 1    | 1 †        | log *n* †      | 1       |

​                                                                                                                                                                                         † amortized guarantee

