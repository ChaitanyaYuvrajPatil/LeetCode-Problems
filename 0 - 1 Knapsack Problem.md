Problem :  0 - 1 Knapsack Problem (LeetCode)

Problem link : https://practice.geeksforgeeks.org/problems/0-1-knapsack-problem0945/1

## 1) Solution

```C++
class Solution
{
    public:
    
    int fun(int ind,int w,int wt[], int val[],vector<vector<int>> &dp)
    {
        
        if(ind == 0)
        {
            if(w>=wt[0]) return val[0];
            return 0;
        }
        
        if(dp[ind][w] != -1) return dp[ind][w];
        
        int not_take = fun(ind-1,w,wt,val,dp);
        
        int take = 0;
        
        if(wt[ind] <= w)
           take = val[ind] + fun(ind-1,w-wt[ind],wt,val,dp);
           
        return dp[ind][w] = max(take,not_take);
    }
    
    int knapSack(int W, int wt[], int val[], int n) 
    { 
       vector<vector<int>> dp(n,vector<int>(W+1,-1));
       
       return fun(n-1,W,wt,val,dp);
    }
};
```
