# [11. 盛最多水的容器](https://leetcode-cn.com/problems/container-with-most-water/)

## 描述

给你 n 个非负整数 a1，a2，...，an，每个数代表坐标中的一个点 (i, ai) 。在坐标内画 n 条垂直线，垂直线 i 的两个端点分别为 (i, ai) 和 (i, 0)。找出其中的两条线，使得它们与 x 轴共同构成的容器可以容纳最多的水。

说明：你不能倾斜容器，且 n 的值至少为 2。

 

![img](https://i.loli.net/2020/05/24/NklyiFzwhcERIW3.jpg)

图中垂直线代表输入数组 [1,8,6,2,5,4,8,3,7]。在此情况下，容器能够容纳水（表示为蓝色部分）的最大值为 49。

 

示例：

输入：[1,8,6,2,5,4,8,3,7]
输出：49

## 思路

问题从盛最多水 可以转化为求最大面积，也就是 x轴距（左右边界的距离）* min(左边界垂直线的高度, 右边界垂直线的高度)

1. 枚举左右边界-时间复杂度是$$O(n^2)$$ - 也就是两个指针同向而行
2. 两个指针左右逼近 -时间复杂度是O(n)

## 题解

### Python3

```python
class Solution:
    def maxArea(self, height: List[int]) -> int:
        res = 0
        i, j = 0, len(height) - 1
        while i < j:
            minHeight = min(height[i], height[j])
            res = max(res, (j - i) * minHeight)
            if height[i] < height[j]:
                i += 1 
            else:
                j -= 1
        return res
```

