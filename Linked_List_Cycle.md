```
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode(int x) : val(x), next(NULL) {}
 * };
 */
class Solution {
public:
    bool hasCycle(ListNode *head) {
        unordered_map<ListNode*, bool> m;

        ListNode* node = head;
        while(node != NULL){
            if(m.find(node) != m.end())
                return true;
            
            m[node] = true;
            node = node->next;
        }
        return false;
        
    }
};
```
