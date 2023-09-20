[Problem Link](https://leetcode.com/problems/climbing-stairs/description/)

[NeetCode Editorial](https://www.google.com/search?q=leetcode+climbing+stairs&oq=leetcode+climbing+s&gs_lcrp=EgZjaHJvbWUqCQgAECMYJxiKBTIJCAAQIxgnGIoFMgYIARBFGDkyDAgCEAAYFBiHAhiABDIHCAMQABiABDIHCAQQABiABDIGCAUQRRg8MgYIBhBFGDwyBggHEEUYPNIBCDMyNDRqMGo3qAIAsAIA&sourceid=chrome&ie=UTF-8#fpstate=ive&vld=cid:39cba2ef,vid:Y0lT9Fck7qI,st:0)

### Things to Note: 
1. start from bottom, work ur way up -> bottom up DP
2. **base case**: last slot is always **1** bc it's at the goal <br>
    NOTE: 2nd-to-last slots could only be 1 as well bc only 1 step to goal (else out of bound)
3. **recurrence**: how many options can you reach the goal from step 2? <br>
    num options from step 3 + num options from step 4

<img width="500" alt="image" src="https://github.com/seliiin-na/LeetCode/assets/89162258/d22e6ebc-eb79-4ca1-b968-1574e0b47072">

```python
class Solution:
    def climbStairs(self, n: int) -> int:
        if n == 0 or n == 1:
            return 1

        # create memo with n + 1 slots
        # initialize a list w/ (n + 1) slots
        dp = [0] * (n + 1)
        dp[0] = dp[1] = 1

        # DP: result at each step depends on prev 2 sub-Ps
        for i in range (2, n + 1):
            dp[i] = dp[i - 1] + dp[i - 2]

        return dp[n]
```
