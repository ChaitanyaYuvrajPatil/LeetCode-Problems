
Problem : Subset with sum divisible by m (GFG)

Problem link : https://practice.geeksforgeeks.org/problems/subset-with-sum-divisible-by-m2546/1

## Solution

```C++
    class Solution{
	public:
	
	    bool fun(int ind,int sum,int m,vector<int>nums,vector<vector<int>> &dp)
	    {
	        if(sum!=0 && sum %m == 0) return 1;
	        
	        if(ind < 0)
	        {
	            return 0;
	        }
	        
	        if(dp[ind][sum] != -1) return dp[ind][sum];
	        
	        int not_take = fun(ind-1,sum,m,nums,dp);
	        
	        int take = fun(ind-1,sum+nums[ind],m,nums,dp);
	        
	        return dp[ind][sum] = not_take || take;
	    }
		int DivisibleByM(vector<int>nums, int m){
		    
		    int n = nums.size();
		    
		    int sum=0;
		    for(int i=0;i<n;i++){
		        sum+=nums[i];
		    }

		    
		    vector<vector<int>> dp(n,vector<int>(sum+1,-1));
		    
		    return fun(n-1,0,m,nums,dp);
		}
};
```
