Problem :  Jump Game II (LeetCode)

Problem link : https://leetcode.com/problems/jump-game-ii/

## 1) Using Memoization 

```C++
class Solution {
public:
    
    int fun(int ind,vector<int>& nums,vector<int>&dp)
    {
        if(ind == nums.size()-1) return 0;
        
        if(dp[ind] != -1) return dp[ind];
        
        int mn = 1e9;
        
        for(int i=1;i<=nums[ind];i++)
        {
            if(ind+i < nums.size())
                mn = min(mn,1 + fun(ind+i,nums,dp));
        }
        
        return dp[ind] = mn;
    }
    
    int jump(vector<int>& nums) {
        
        int n = nums.size();
        
        vector<int>dp(n,-1);
        
        return fun(0,nums,dp);
    }
};
```

## 2) Using Tabulation

```C++
class Solution {
public:
    int jump(vector<int>& nums) {
        
        int n = nums.size();
        
        vector<int>dp(n,0);
        
        for(int ind = n-2;ind >=0; ind--)
        {
            int mn = 1e9;
        
            for(int i=1;i<=nums[ind];i++)
            {
               if(ind+i < nums.size())
                    mn = min(mn,1 + dp[ind+i]);
            }
        
            dp[ind] = mn;
        }
        
        return dp[0];
    }
};
```
