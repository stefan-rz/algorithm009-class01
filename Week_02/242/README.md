# 描述

给定两个字符串 s 和 t ，编写一个函数来判断 t 是否是 s 的字母异位词。

示例 1:

输入: s = "anagram", t = "nagaram"
输出: true
示例 2:

输入: s = "rat", t = "car"
输出: false
说明:
你可以假设字符串只包含小写字母。

进阶:
如果输入字符串包含 unicode 字符怎么办？你能否调整你的解法来应对这种情况？



# 思路

1. 先排序，后判断两字符串是否相等
2. 通过map来记录每个字符的频次

# 题解

```python
# 思路：手动模拟hashtable，将字符串”a-z“的ASCII码作key，计数求差异    
   def  isAnagram(self, s: str, t: str) -> bool:
        arr1, arr2 = [0]*26, [0]*26
        for i in s:
            arr1[ord(i) - ord('a')] += 1
        for i in t:
            arr2[ord(i) - ord('a')] += 1
        return arr1 == arr2
```

```python
# 思路：map计数，对比计数差异
    def isAnagram(self, s: str, t: str) -> bool:
        dict1, dict2 = {}, {}
        for item in s:
            dict1[item] = dict1.get(item,0) + 1
        for item in t:
            dict2[item] = dict2.get(item,0) + 1
        return dict1 == dict2
```

```python
# 思路：数组排序后比较差异
    def isAnagram(self, s: str, t: str) -> bool:
        return sorted(s) == sorted(t)
```

