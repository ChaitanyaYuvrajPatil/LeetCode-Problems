## Problem : Integer to Roman

Problem link : https://leetcode.com/problems/integer-to-roman/

### Code :

```C++

class Solution {
public:
    string intToRoman(int num) {
        
        string ans = "";
        
        vector<int> intiger = {1000,900,500,400,100,90,50,40,10,9,5,4,1};
        vector<string> roman = {"M","CM","D","CD","C","XC","L","XL","X","IX","V","IV","I"};
        
        for(int i=0;i<intiger.size();i++)
        {
            while(num>=intiger[i])
            {
                num = num - intiger[i];
                ans += roman[i];
            }
        }
        
        return ans;
    }
};
```
