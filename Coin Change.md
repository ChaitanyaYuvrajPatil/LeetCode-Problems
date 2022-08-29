
Problem : Coin Change (LeetCode)

Problem link : https://leetcode.com/problems/coin-change/

## Solution

```C++
class Solution {
public:

    int fun(int ind,int tar,vector<int>& coins,vector<vector<int>> &dp)
    {
        if(ind == 0)
        {
            if(tar % coins[0] == 0) return tar/coins[0];
            return 1e9;
        }
        
        if(dp[ind][tar] != -1) return dp[ind][tar];
        
        int not_take = fun(ind-1,tar,coins,dp);
        
        int take = 1e9;
        
        if(tar >= coins[ind])
            take = 1 + fun(ind,tar-coins[ind],coins,dp);
        
        return dp[ind][tar] = min(not_take,take);
    }
    
    int coinChange(vector<int>& coins, int amount) {
        
        
        int n = coins.size();
        vector<vector<int>> dp(n+1,vector<int>(amount+2,-1));
        
        int m = fun(n-1,amount,coins,dp);
        
        if(m==1e9) return -1;
        
        return m;
    }
};
```
