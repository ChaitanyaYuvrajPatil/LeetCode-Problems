
## Problem : Zigzag Conversion

Problem link : https://leetcode.com/problems/zigzag-conversion/

### Code 

```C++

class Solution {
public:
    string convert(string s, int numRows) {
        
        vector<string> mat(numRows,"");
        string ans = "";
        int n = s.size();
        int i=0;
        
        while(i<n)
        {
            for(int j=0;j<numRows && i<n ;j++)
            {
                mat[j] += s[i];
                i++;
            }
            
            for(int j=numRows-2;j>0 && i<n ;j--)
            {
                mat[j] += s[i];
                i++;
            }
        }
        
        for(auto it : mat) 
            ans+=it;
        
        return ans;
    }
};
```
