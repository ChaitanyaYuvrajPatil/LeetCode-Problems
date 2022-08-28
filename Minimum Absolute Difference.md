Problem :  Minimum Absolute Difference (LeetCode)

Problem link : https://leetcode.com/problems/minimum-absolute-difference/

## 1) Solution

```C++
class Solution {
public:
    vector<vector<int>> minimumAbsDifference(vector<int>& arr) {
        
        int n = arr.size();
        vector<vector<int>> ans;
        
        sort(arr.begin(),arr.end());
        
        int min_diff = 1e9;
        
        for(int i=1;i<n;i++)
        {
            min_diff = min(min_diff,arr[i]-arr[i-1]);
        }
        
        for(int i=1;i<n;i++)
        {
            if(arr[i]-arr[i-1] == min_diff)
            {
                ans.push_back({arr[i-1],arr[i]});
            }
        }
        
        return ans;
    }
};
```
