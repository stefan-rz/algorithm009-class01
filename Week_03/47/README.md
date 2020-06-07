#### [47. 全排列 II](https://leetcode-cn.com/problems/permutations-ii/)

# 描述

给定一个可包含重复数字的序列，返回所有不重复的全排列。

示例:

输入: [1,1,2]
输出:
[
  [1,1,2],
  [1,2,1],
  [2,1,1]
]



# 题解

```python
class Solution:
    def permuteUnique(self, nums: List[int]) -> List[List[int]]:
        def _permute(result, temp, nums):
            if nums == []:
                result += [temp]
            else:
                for i in range(len(nums)):
                    if i > 0 and nums[i] == nums[i-1]:
                        continue
                    _permute(result, temp + [nums[i]], nums[:i] + nums[i+1:])
        if nums is None:
            return []

        if len(nums) == 0:
            return [[]]

        result = []
        _permute(result, [], sorted(nums))
        return result
```