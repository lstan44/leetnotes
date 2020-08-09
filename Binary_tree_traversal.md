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

## Pre-order Traversal - Recursive Solution
----------------------------------

```
class Solution {
private:
    vector<int>res;
public:
    vector<int> preorderTraversal(TreeNode* root) {
        if(root == nullptr)
        {
            return res;
        }
       
        res.push_back(root->val);
        
        preorderTraversal(root->left);
        preorderTraversal(root->right);
        
        return res;
    }
};

```

## In-order Traversal - Iterative solution
--------------------------

```
 vector<int> inorderTraversal(TreeNode* root) {
        stack<TreeNode*> st;
        vector<int>res;
        
        TreeNode* curr = root;
        
        while(!st.empty() || curr != nullptr)
        {
            if(curr != nullptr)
            {
                st.push(curr);
                curr = curr->left;
            }
            else
            {
                curr = st.top();
                st.pop();
                res.push_back(curr->val);
                
                curr = curr->right;
            }
        }
        return res;
    }
```

## In-order Traversal - Recursive Solution
---------------------

```
class Solution {
private:
    vector<int>res;
public:
    vector<int> inorderTraversal(TreeNode* root) {
        if(root == nullptr)
        {
            return res;
        }
        if(root->left != nullptr)
        {
            inorderTraversal(root->left);
        }
        res.push_back(root->val);
        
        if(root->right != nullptr)
        {
            inorderTraversal(root->right);
        }
        return res;
    }
};
```

## Post-order Traversal - Recursive Solution
----------------------------

```
class Solution {
private:
    vector<int>res;
public:
    vector<int> postorderTraversal(TreeNode* root) {
        
        if(root == nullptr)
        {
            return res;
        }
        
        if(root->left != nullptr)
        {
            postorderTraversal(root->left);
        }
            
        if(root->right != nullptr)
        {
            postorderTraversal(root->right);
        }
            
        res.push_back(root->val);
        
        return res;
    }
};
```

## Post-order Traversal - Iterative solution
---------------------

```
 vector < int > postorderTraversal(TreeNode * root) 
 {
   vector < int > res;
   stack < TreeNode * > st;
   if (root == nullptr) 
   {
     return res;
   }
   TreeNode * pre = nullptr;
   while (root != nullptr || !st.empty()) 
   {
     if (root != nullptr) 
     {
       st.push(root);
       root = root -> left;
     } 
     else 
     {
       root = st.top();
       if (root -> right == nullptr || root -> right == pre) 
       {
         res.push_back(root -> val);
         st.pop();
         pre = root;
         root = nullptr;
       } 
       else 
       {
         root = root -> right;
       }
     }
   }
   return res;
 }

 ```
 