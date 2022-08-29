Problem : Target Sum

Problem Link : https://leetcode.com/problems/target-sum/

## Solution

```C++
class Solution {
public:
    
    int fun(int ind,int tar, vector<int>& nums,vector<vector<int>> &dp)
    {
        if(ind == 0)
        {
            if(nums[0] ==0 && tar ==0) return 2;
            if(tar == 0 || nums[0] == tar) return 1;
            return 0;
        }
        
        if(dp[ind][tar] != -1) return dp[ind][tar];
            
        int not_take = fun(ind-1,tar,nums,dp);
        int take = 0;
        
        if(tar>=nums[ind])
            take = fun(ind-1,tar-nums[ind],nums,dp);
        
        return dp[ind][tar] = take + not_take;
    }
    
    int ways(vector<int>& nums, int tar)
    {
        int n = nums.size();
        
        vector<vector<int>> dp(n,vector<int>(tar+1,-1));
        
        return fun(n-1,tar,nums,dp);
    }
    
    int findTargetSumWays(vector<int>& nums, int d) {
        
        int total = 0;
        
        for(auto it : nums) total+= it;
        
        if(total - d <0 || (total - d)%2) return 0;
        
        return ways(nums,(total-d)/2);
    }
};
```
