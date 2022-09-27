## Problem : Generate Parentheses

Problem link : https://leetcode.com/problems/generate-parentheses/

### Soluton 

```C++
class Solution {
public:
    vector<string> generateParenthesis(int n) {
        vector<string> ans;
        
        backtrack(ans,n,0,0,"");
        
        return ans;
    }
    
    void backtrack(vector<string>&ans,int n,int open,int close,string str)
    {
        if(str.size() == 2*n)
        {
            ans.push_back(str);
            return;
        }
        
        if(open<n)
        {
            backtrack(ans,n,open+1,close,str+"(");
        }
        
        if(close<open)
        {
            backtrack(ans,n,open,close+1,str+")");
        }
    }
};
```
