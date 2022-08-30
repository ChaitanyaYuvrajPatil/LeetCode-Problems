
Problem : Longest Common Substring (GFG)

Problem link : https://practice.geeksforgeeks.org/problems/longest-common-substring1452/1

## Solution

```C++
    public:
    
    int longestCommonSubstr (string s1, string s2, int n, int m)
    {
        vector<vector<int>> dp(n+1,vector<int>(m+1,0));
        int mx = 0;
        
        for(int i=1;i<=n;i++)
        {
            for(int j=1;j<=m;j++)
            {
                if(s1[i-1] == s2[j-1])
                {
                    dp[i][j] = 1 + dp[i-1][j-1];
                    mx = max(mx,dp[i][j]);
                }
            
            }
        }
        
        return mx;
    }
};
```
