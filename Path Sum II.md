Problem : Path Sum II (LeetCode)

Problem link : https://leetcode.com/problems/path-sum-ii/

## 1) Solution

```C++
class Solution {
public:
    
    void fun(TreeNode* root,int sum,int target,vector<int>path,vector<vector<int>> &vec)
    {
        if(root == NULL) return ;
        
        sum += root->val;
        
        path.push_back(root->val);
        
        if(root->left == NULL && root->right == NULL && sum == target) 
        {
            vec.push_back(path);
            return;
        }
        
        fun(root->left,sum,target,path,vec);
        fun(root->right,sum,target,path,vec);
        
        return ;
    }
    
    vector<vector<int>> pathSum(TreeNode* root, int target) {
        
        vector<vector<int>> vec;
        vector<int>path;
        
        fun(root,0,target,path,vec);
            
        return vec;
    }
};
```
