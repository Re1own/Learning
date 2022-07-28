### 0x01 数组中两个数相加等于目标数字

[Two Sum](https://leetcode.com/problems/two-sum/)

**Example 1:**

```
Input: nums = [2,7,11,15], target = 9
Output: [0,1]
Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].
```

**Example 2:**

```
Input: nums = [3,2,4], target = 6
Output: [1,2]
```

**Example 3:**

```
Input: nums = [3,3], target = 6
Output: [0,1]
```

**Code：**

```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        Map<Integer, Integer> map = new HashMap<>();
        for (int i = 0; i < nums.length; i++) {
            int complement = target - nums[i];
            if (map.containsKey(complement)) {
                return new int[] { map.get(complement), i};
      i      }
            map.put(nums[i], i);
        }
        return null;
    }
}
```

### 0x02 回文数a判断：

[Palindrome Number](https://leetcode.com/problems/palindrome-number/)

**Example 1:**

```
Input: x = 121
Output: true
Explanation: 121 reads as 121 from left to right and from right to left.
```

**Example 2:**

```
Input: x = -121
Output: false
Explanation: From left to right, it reads -121. From right to left, it becomes 121-. Therefore it is not a palindrome.
```

**Example 3:**

```
Input: x = 10
Output: false
Explanation: Reads 01 from right to left. Therefore it is not a palindrome.
```

**Code：**

```python
class Solution:
    def isPalindrome(self, x: int) -> bool:
        return str(x) == str(x)[::-1]
```

### 0x03 罗马数字转化为整数

[Roman to Integer](https://leetcode.com/problems/palindrome-number/)

**Example 1:**

```
Input: s = "III"
Output: 3
Explanation: III = 3.
```

**Example 2:**

```
Input: s = "LVIII"
Output: 58
Explanation: L = 50, V= 5, III = 3.
```

**Example 3:**

```
Input: s = "MCMXCIV"
Output: 1994
Explanation: M = 1000, CM = 900, XC = 90 and IV = 4.
```

**Code**:

```python
class Solution:
    def romanToInt(self, s: str) -> int:
        values = { "I":1, "V":5, "X":10, "L":50, "C":100, "D":500, "M":1000}
        result = values[s[len(s)-1]]
        for i in range(len(s)-2, -1, -1):
            if values[s[i]] >= values[s[i+1]]:
                result += values[s[i]]
            else:
                result -= values[s[i]]
        return result
```

### 0x04 Longest Common Prefix

**Example 1:**

```
Input: strs = ["flower","flow","flight"]
Output: "fl"
```

**Example 2:**

```
Input: strs = ["dog","racecar","car"]
Output: ""
Explanation: There is no common prefix among the input strings.
```



**Reference**

[最长公共子串（Longest Common SubString）](https://blog.csdn.net/u013309870/article/details/69479488)