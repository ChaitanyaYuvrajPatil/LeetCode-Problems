## Remove Duplicates from Sorted List

Problem Link : https://leetcode.com/problems/remove-duplicates-from-sorted-list/description/

### Solution : 

```C++
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode() : val(0), next(nullptr) {}
 *     ListNode(int x) : val(x), next(nullptr) {}
 *     ListNode(int x, ListNode *next) : val(x), next(next) {}
 * };
 */
class Solution {
public:
    ListNode* deleteDuplicates(ListNode* head) {

        if(head==NULL || head->next ==NULL) return head;
        map<int,int>mpp;
        ListNode* temp = head;

        while(temp)
        {
            mpp[temp->val]++;
            temp = temp->next;
        }

        ListNode* temp2 = head;
        for(auto it : mpp)
        {
            temp2->val = it.first;
            temp = temp2;
            temp2 = temp2->next;
        }
        temp->next = NULL;
        return head;
    }
};
```
