# Binary Tree Traversal

## Pre-order traversal - Iterative solution
------------------------

_https://leetcode.com/explore/learn/card/data-structure-tree/134/traverse-a-tree/928/_

```
vector<int> preorderTraversal(TreeNode* root) {
      vector<int>res;
        
        stack<TreeNode*> st;
        if(root == nullptr) return res;
        
        st.push(root);
        
        while(!st.empty())
        {
            TreeNode* curr = st.top();
            if(curr != nullptr)
            {
                res.push_back(curr->val);
            }
            
            st.pop();
            
            if(root->right != nullptr)
            {
                st.push(root->right);
            }
            
            if(root->left != nullptr)
            {
                st.push(root->left);
            }
            
            if(! st.empty()) root = st.top();
        }
        
        return res;
    }
```
