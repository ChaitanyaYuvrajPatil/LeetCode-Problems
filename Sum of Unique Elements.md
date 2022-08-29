
Problem : Sum of Unique Elements (LeetCode)

Problem link : https://leetcode.com/problems/sum-of-unique-elements/

## Solution

```C++
class Solution {
public:
    int sumOfUnique(vector<int>& nums) {
        
        map<int,int>mpp;
        int ans = 0;
        
        for(auto it : nums) mpp[it]++;
        
        for(auto it : nums)
        {
            if(mpp[it] == 1) ans += it;
        }
        
        return ans;
    }
};
```
