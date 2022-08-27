
Problem :  Path Sum (LeetCode)

Problem link : https://leetcode.com/problems/path-sum/

## 1) Solution

```C++
class Solution {
public:
    
    bool fun(TreeNode* root,int sum,int target)
    {
        if(root == NULL) return false;
        
        sum += root->val;
        
        if(root->left == NULL && root->right == NULL && sum == target) 
             return true;
        
        bool left = fun(root->left,sum,target);
        bool right = fun(root->right,sum,target);
        
        return left || right;
    }
    
    bool hasPathSum(TreeNode* root, int targetSum) {
        
        
        return fun(root,0,targetSum);
    }
};
```
