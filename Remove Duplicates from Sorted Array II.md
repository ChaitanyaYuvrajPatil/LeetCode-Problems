## Problem : Remove Duplicates from Sorted Array II

Problem link : https://leetcode.com/problems/remove-duplicates-from-sorted-array-ii/description/

### Solution :

```C++
class Solution {
public:
    int removeDuplicates(vector<int>& nums) {
        map<int,int>mpp;
        int i =0;
        int cnt = 0;
        for(auto it :nums) mpp[it]++;

        for(auto it :mpp)
        {
            if(it.second >=2)
            {
                nums[i++] = it.first;
                nums[i++] = it.first;
                cnt+=2;
            }
            else
            {
                nums[i++] = it.first;
                cnt++;
            }
        }
        return cnt;
    }
};
```
