# 描述
给定一个字符串数组，将字母异位词组合在一起。字母异位词指字母相同，但排列不同的字符串。

示例:

输入: ["eat", "tea", "tan", "ate", "nat", "bat"]
输出:
[
  ["ate","eat","tea"],
  ["nat","tan"],
  ["bat"]
]

# 思路
1. 排序
2. 计数

# 题解
```python
# 思路 排序
def groupAnagrams(self, strs: List[str]) -> List[List[str]]:
        ans = collections.defaultdict(list)
        for s in strs:
            ans[tuple(sorted(s))].append(s)
        return list(ans.values())
```
**复杂度分析**
时间复杂度：O(NKlogK)，其中 NN 是 strs 的长度，而 KK 是 strs 中字符串的最大长度。当我们遍历每个字符串时，外部循环具有的复杂度为 O(N)。然后，我们在 O(KlogK) 的时间内对每个字符串排序。

空间复杂度：O(NK)，排序存储在 ans 中的全部信息内容。

``` python
# 思路 计数
def groupAnagrams(self, strs: List[str]) -> List[List[str]]:
        ans = collections.defaultdict(list)
        for s in strs:
            count = [0] * 26
            for c in s:
                count[ord(c) - ord('a')] += 1
            ans[tuple(count)].append(s)
        return list(ans.values())
```

**复杂度分析**

时间复杂度：O(NK)，其中 NN 是 strs 的长度，而 KK 是 strs 中字符串的最大长度。计算每个字符串的字符串大小是线性的，我们统计每个字符串。

空间复杂度：O(NK)，排序存储在 ans 中的全部信息内容。