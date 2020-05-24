https://leetcode-cn.com/problems/remove-duplicates-from-sorted-array/
https://leetcode-cn.com/problems/rotate-array/
https://leetcode-cn.com/problems/merge-two-sorted-lists/
https://leetcode-cn.com/problems/merge-sorted-array/
https://leetcode-cn.com/problems/two-sum/
https://leetcode-cn.com/problems/move-zeroes/
https://leetcode-cn.com/problems/plus-one/

https://leetcode.com/problems/design-circular-deque
https://leetcode.com/problems/trapping-rain-water/
用add first或add last这套新的API改写Deque的代码
分析Queue和Priority Queue的源码

改写代码和分析源码这两项作业，需要在你的本周学习总结中一并提交。







# [283. 移动零](https://leetcode-cn.com/problems/move-zeroes/)

**标签：数组，双指针**

给定一个数组 nums，编写一个函数将所有 0 移动到数组的末尾，同时保持非零元素的相对顺序。

示例:

输入: [0,1,0,3,12]
输出: [1,3,12,0,0]
说明:

必须在原数组上操作，不能拷贝额外的数组。
尽量减少操作次数。

## 思路

题目要求必须在原数组上操作，所以双指针是必然的选择，只要定义好双指针的含义，就能解决这道题目

fast 指针： 探索未知领域区间（fast, 数组len)， 区间[slow, fast]之间代表是0

slow指针： 【0，slow] 代表非0数

下面的示意图粗略的画出了一次完整的操作：

输入: [0,1,0,3,12]
输出: [1,3,12,0,0]

![算法-2](https://i.loli.net/2020/05/24/7FrpQPtxLqA1kZj.jpg)

![算法-3](https://i.loli.net/2020/05/24/k9doQihxuLOnWz5.jpg)

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

