
Problem : Minimum Moves to Equal Array Elements (Code studio)

Problem link : https://leetcode.com/problems/minimum-moves-to-equal-array-elements/

## Solution

```C++
class Solution {
public:
    int minMoves(vector<int>& nums) {
        
        int mn = 1e9;
        int ans = 0;
        
        for(auto it : nums) mn = min(mn,it);
        
        for(auto it : nums) ans += (it-mn);
        
        return ans;
    }
};
```
