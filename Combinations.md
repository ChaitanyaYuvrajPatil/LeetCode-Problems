## Problem : Combinations

Problem link : https://leetcode.com/problems/combinations/description/

### Solution :

```C++
class Solution {
public:

    void subset(int start,int n,int k,vector<int>curr,vector<vector<int>> &ans)
    {
        if(curr.size() == k)
        {
            ans.push_back(curr);
            return;
        }

        for(int i=start;i<=n;i++)
        {
            curr.push_back(i);
            subset(i+1,n,k,curr,ans);
            curr.pop_back();
        }
    }

    vector<vector<int>> combine(int n, int k) {
        
         vector<vector<int>> ans;
         vector<int>curr;
         subset(1,n,k,curr,ans);

         return ans;
    }
};
```
