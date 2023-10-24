[Problem Link](https://leetcode.com/problems/greatest-common-divisor-of-strings/description/?envType=study-plan-v2&envId=leetcode-75)

<img width="500" alt="image" src="https://github.com/seliiin-na/LeetCode/assets/89162258/4fca5636-98ae-48fb-adc5-613d70d963be">

### Things to Note:
1. GCD of string = a substring that, when repeated 1 or more times, make up another string
2. Check if the concatenation of str1 & str2 in both orders are the same: if not, NO divisible strings
3. If there are divisible strings, find the gcd of the lengths

```py
class Solution:
    def gcdOfStrings(self, str1: str, str2: str) -> str:
        # if concatenation of 2 strings are not the same 
        if str1 + str2 != str2 + str1:
            return ""

        # get GCD of the lengths of str1 and str2
        len_gcd = gcd(len(str1), len(str2))
        return str1[:len_gcd]
```
