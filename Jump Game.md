Problem :  Jump Game (LeetCode)

Problem link : https://leetcode.com/problems/jump-game/

## 1) Using Memoization 

```C++
class Solution {
public:
    
    bool fun(int ind,vector<int>& nums,vector<int>&dp)
    {
       if(ind == nums.size()-1) return true;
        
       if(dp[ind] != -1) return dp[ind];
       
       int reach = false;
        
       for(int i=1;i<=nums[ind];i++)
       {
           if(fun(ind+i,nums,dp))
               return dp[ind] = true;
       }
        
       return dp[ind] = reach;
    }
    
    bool canJump(vector<int>& nums) {
        
        int n = nums.size();
        vector<int>dp(n,-1);
        
        return fun(0,nums,dp);
    }
};
```
## 2) Using Tabulation
```C++

```
