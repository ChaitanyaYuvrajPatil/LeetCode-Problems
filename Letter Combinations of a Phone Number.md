
## Problem : Letter Combinations of a Phone Number

Problem link : https://leetcode.com/problems/letter-combinations-of-a-phone-number/

### Code :

```C++

unordered_map<char, string> mpp({{'2',"abc"},{'3',"def"},{'4',"ghi"},
    {'5',"jkl"},{'6',"mno"},{'7',"pqrs"},{'8',"tuv"},{'9',"wxyz"}});

class Solution {
public:
    
    void backtract(int i,int &n,string &digit,vector<string>&ans,string temp)
    {
        if(i == n)
        {
            ans.push_back(temp);
        }
        else
        {
            string letters = mpp[digit[i]];
            
            for(int j = 0; j < letters.size(); j++)
                backtract(i+1,n,digit,ans,temp+letters[j]);
           
        }
    }
    
    vector<string> letterCombinations(string digit) {
        
        vector<string>ans;
        int n = digit.size();
        
        if(n) backtract(0,n,digit,ans,"");
        
        return ans;
    }
};
```



