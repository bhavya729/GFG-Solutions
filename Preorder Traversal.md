## 01. Preorder Traversal

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/preorder-traversal/1)

### Problem Description

**Task:** Given the root of a binary tree, return its preorder traversal. A preorder traversal first visits the node, then visits the left child (including its entire subtree), and finally visits the right child (including its entire subtree).

#### Examples

##### Example 1

- **Input:**
```text
root = [1, 4, N, 4, 2]
```
- **Output:**
```text
[1, 4, 4, 2]Explanation: The preorder traversal of the given binary tree is [1, 4, 4, 2]
```

##### Example 2

- **Input:**
```text
root = [6, 3, 2, N, 1, 2, N]
```
- **Output:**
```text
[6, 3, 1, 2, 2] Explanation: The preorder traversal of the given binary tree is [6, 3, 1, 2, 2]
```

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (C++)

- **Submitted:** 2026-10-18 15:55:42
- **Status:** Correct
- **Marks:** 1

```cpp
/* Structure of Tree Node
class Node {
  public:
    int data;
    Node* left;
    Node* right;

    Node(int val) {
        data = val;
        left = nullptr;
        right = nullptr;
    }
};*/

class Solution {
  public:
  void preorder(Node*root,vector<int>& ans){
      if (root==NULL) return;
      ans.push_back(root->data);
      preorder(root->left,ans);
      preorder(root->right,ans);
  }
    vector<int> preOrder(Node* root) {
        vector<int> ans;
        preorder(root,ans);\
        return ans;
        
    }
};
```

*Generated on: 18/10/2026, 3:56:03 pm*