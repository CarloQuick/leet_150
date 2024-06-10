//https://www.geeksforgeeks.org/dfs-traversal-of-a-tree-using-recursion/
// https://www.geeksforgeeks.org/find-the-maximum-depth-or-height-of-a-tree/
```
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode() : val(0), left(nullptr), right(nullptr) {}
 *     TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
 *     TreeNode(int x, TreeNode *left, TreeNode *right) : val(x), left(left), right(right) {}
 * };
 */
class Solution {
public:
    int maxDepth(TreeNode* root) {
        if(root == NULL)
            return 0;
        
        int lmax = maxDepth(root->left);
        int rmax = maxDepth(root->right);

        return max(lmax, rmax) + 1;
   
    }
};
```
