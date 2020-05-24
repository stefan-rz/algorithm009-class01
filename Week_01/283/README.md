# [283. 移动零](https://leetcode-cn.com/problems/move-zeroes/)

## 描述

给定一个数组 nums，编写一个函数将所有 0 移动到数组的末尾，同时保持非零元素的相对顺序。

示例:

输入: [0,1,0,3,12]
输出: [1,3,12,0,0]
说明:

必须在原数组上操作，不能拷贝额外的数组。
尽量减少操作次数。

## 思路

题目要求必须在原数组上操作，所以双指针是必然的选择，只要定义好双指针的含义，就能解决这道题目

fast 指针：当遇到0元素的时候，继续向前移动，当遇到1元素的时候，与slow指针指向的位置作交换，slow 和 fast都各自移动一步

slow指针： 记录下一个非0元素的要放的位置，【0，slow） 代表非0数

下面的示意图粗略的画出了一次完整的操作：

输入: [0,1,0,3,12]
输出: [1,3,12,0,0]

![算法-2](https://i.loli.net/2020/05/24/7FrpQPtxLqA1kZj.jpg)

![算法-3](https://i.loli.net/2020/05/24/k9doQihxuLOnWz5.jpg)

## 题解

### Python3

```python
class Solution:
    def moveZeroes(self, nums: List[int]) -> None:
        """
        Do not return anything, modify nums in-place instead.
        """
        left, right = 0, 0
        while right < len(nums):
            if nums[right] != 0:
                if left != right:
                    nums[right], nums[left] = nums[left], nums[right]
                left += 1
            right += 1
```

