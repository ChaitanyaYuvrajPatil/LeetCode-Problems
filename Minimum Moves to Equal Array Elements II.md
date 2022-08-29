
Problem : Minimum Moves to Equal Array Elements II (LeetCode)

Problem link : https://leetcode.com/problems/minimum-moves-to-equal-array-elements-ii/

## Solution

```C++
class Solution {
public:
    int minMoves2(vector<int>& nums) {
        
        int n = nums.size();
        int ans = 0;
        sort(nums.begin(),nums.end());
        
        int median = nums[n/2];
        
        for(auto it : nums)
            ans += abs(it-median);
        
        return ans;
    }
};
```
