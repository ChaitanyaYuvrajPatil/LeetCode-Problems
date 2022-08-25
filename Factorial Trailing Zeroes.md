Problem :  Factorial Trailing Zeroes (LeetCode)

Problem link : https://leetcode.com/problems/factorial-trailing-zeroes/

## 1) Solution

```C++
class Solution {
public:
    int trailingZeroes(int n) {
        
        int ans = 0;
        
        for(int i=5;i<=n;i*=5)
        {
            ans += floor(n/i);
        }
        
        return ans;
    }
};
```
