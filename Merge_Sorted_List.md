
// https://leetcode.com/problems/merge-two-sorted-lists/solutions/1826666/c-easy-to-understand-2-approaches-recursive-iterative
// solution by r4jiv
```
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
    ListNode* mergeTwoLists(ListNode* list1, ListNode* list2) {
        ListNode* dummy = new ListNode();
        ListNode* tail = dummy;

        while(list1 && list2){
            if(list1->val < list2->val){
                tail->next = list1;
                list1 = list1->next;
            }
            else{
                tail->next = list2;
                list2 = list2->next;
            }
            tail = tail->next; // tail needs to move up
        }
     // exited the while loop so one is nullptr
        if(list1) tail->next = list1;
        if(list2) tail->next = list2;

        // dummy is empty so we point to the head which equals dummy->next
        return dummy->next;   
    }
};
```
