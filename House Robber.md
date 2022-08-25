
Problem :  House Robber (LeetCode)

Problem link : https://leetcode.com/problems/house-robber/

## 1) Using Memoization 

```C++
class Solution {
public:
    
    int fun(int ind,vector<int>& nums,vector<int> &dp)
    {
        if(ind == 0) return nums[0];
        
        if(ind < 0) return 0;
        
        if(dp[ind] != -1) return dp[ind];
        
        int peak = nums[ind] + fun(ind-2,nums,dp);
        
        int non_peak = 0 + fun(ind-1,nums,dp);
        
        return dp[ind] = max(peak,non_peak);
    }
    
    int rob(vector<int>& nums) {
        
        int n = nums.size();
        
        vector<int> dp(n,-1);
        
        return fun(n-1,nums,dp);
    }
};
```

## 2) Using Tabulation

```C++
int rob(vector<int>& nums) {
        
        int n = nums.size();
        
        vector<int> dp(n,-1);
        
        dp[0] = nums[0];
        
        for(int ind=1;ind<n;ind++)
        {
            int peak = nums[ind];
            
            if(ind>1)
               peak += dp[ind-2];
        
            int non_peak = 0 + dp[ind-1];
        
            dp[ind] = max(peak,non_peak);
        }
        
        return dp[n-1];
    }
```

## 3) Using Space Optimization

```C++
int rob(vector<int>& nums) {
        
        int n = nums.size();
        
        vector<int> dp(n,-1);
        
        int prev1 = nums[0];
        int prev2 = 0;
        
        for(int ind=1;ind<n;ind++)
        {
            int peak = nums[ind];
            
            if(ind>1)
               peak += prev2;
        
            int non_peak = 0 + prev1;
        
            int curr = max(peak,non_peak);
            
            prev2 = prev1;
            prev1 = curr;
        }
        
        return prev1;
    }

```
