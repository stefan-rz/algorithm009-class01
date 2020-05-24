# [15. 三数之和](https://leetcode-cn.com/problems/3sum/)

## 描述

给你一个包含 n 个整数的数组 nums，判断 nums 中是否存在三个元素 a，b，c ，使得 a + b + c = 0 ？请你找出所有满足条件且不重复的三元组。

注意：答案中不可以包含重复的三元组。

 

示例：

给定数组 nums = [-1, 0, 1, 2, -1, -4]，

满足要求的三元组集合为：
[
  [-1, 0, 1],
  [-1, -1, 2]
]

## 思路

把3sum的问题转化为“2sum"的问题，也就是说把 b + c 当成一个黑盒，交给2sum的函数去解决。也就是枚举a + 2 sum的结果、

如此通过a去遍历整个数组和比较2sum计算出的a+b的数值来找出所有满足条件的的三元组

时间复杂度= 排序数组（nlogn) + 枚举(a + (b + c)) 的结果$$O(n^2)$$ = $$O(n^2)$$

## 题解

### Python3

```python
class Solution:
    def threeSum(self, nums: List[int]) -> List[List[int]]:
        # write your code here
        nums.sort()
        results = []
        length = len(nums)
        for i in range(0, length - 2):
            if i > 0 and nums[i] == nums[i - 1]:
                continue
            self.find_two_sum(nums, i + 1, length - 1, -nums[i], results)
        return results

    def find_two_sum(self, nums, left, right, target, results):
        while left < right:
            if nums[left] + nums[right] == target:
                results.append([-target, nums[left], nums[right]])
                right -= 1
                left += 1
                while left < right and nums[left] == nums[left - 1]:
                    left += 1
                while left < right and nums[right] == nums[right + 1]:
                    right -= 1
            elif nums[left] + nums[right] > target:
                right -= 1
            else:
                left += 1
```

