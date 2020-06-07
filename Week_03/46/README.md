#### [46. 全排列](https://leetcode-cn.com/problems/permutations/)

# 描述

给定一个 没有重复 数字的序列，返回其所有可能的全排列。

示例:

输入: [1,2,3]
输出:
[
  [1,2,3],
  [1,3,2],
  [2,1,3],
  [2,3,1],
  [3,1,2],
  [3,2,1]
]

# 思路

利用递归回溯算法


# 题解

```python
class Solution:
    def permute(self, nums: List[int]) -> List[List[int]]:
        def _permute(result, temp, nums):
            if nums == []:
                result += [temp]
            else:
                for i in range(len(nums)):
                    _permute(result, temp + [nums[i]], nums[:i] + nums[i+1:])

        if nums is None:
            return []
        
        if nums is []:
            return [[]]

        result = []
        _permute(result, [], sorted(nums))
        return result
```

































题解