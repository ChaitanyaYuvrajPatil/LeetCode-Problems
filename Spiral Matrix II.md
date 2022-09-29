## Spiral Matrix II

Problem link : https://leetcode.com/problems/spiral-matrix-ii/

### Program :

```C++

class Solution {
public:
    vector<vector<int>> generateMatrix(int n) {
        
        int row = n,col = n;
        int left = 0,top = 0, bottom=row-1, right = col-1;
        int k = 1;
        
        vector<vector<int>>ans(n,vector<int>(n,0));
        
        while(top<=bottom && left<=right)
        {
            for(int i = left;i<=right;i++)
            {
                ans[top][i] = k;
                k++;
            }
            
            top++;
            
            for(int i= top;i<=bottom;i++)
            {
                ans[i][right] = k;
                k++;
            }
            
            right--;
            
            if(top<=bottom)
            {
                for(int i= right; i>=left; i--)
                {
                    ans[bottom][i] = k;
                    k++;
                }
            
                bottom--;
            }
            
            if(left <= right)
            {
                 for(int i= bottom; i>=top; i--)
                 {
                    ans[i][left] = k;
                     k++;
                 }
                 
                left++;
            }
        }
        
        return ans;
    }
};
```
