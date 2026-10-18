## 01. Convert to Mirror Tree

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/mirror-tree/1)

### Problem Description

**Task:** Given a binary tree, modify it so that it becomes its mirror. Mirror of a Binary Tree is obtained by interchanging left and right children of all non-leaf nodes.

> **Note:** Changes should be done in-place and need not to return anything.

#### Examples

##### Example 1

- **Input:**
```text
root = [1, 2, 3, N, N, 4]
```
- **Output:**
```text
[1, 3, 2, N, 4]
```
- **Explanation:** In the inverted tree, every non-leaf node has its left and right child interchanged.

##### Example 2

- **Input:**
```text
root = [1, 2, 3, 4, 5]
```
- **Output:**
```text
[1, 3, 2, N, N, 5, 4]
```
- **Explanation:** In the inverted tree, every non-leaf node has its left and right child interchanged.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(n)

### Accepted Solutions (1)

#### Solution 1 (C++)

- **Submitted:** 2026-10-18 11:12:19
- **Status:** Correct
- **Marks:** 2

```cpp
/* Structure of Binary Tree Node
class Node {
  public:
    int data;
    Node *left;
    Node *right;
    Node(int val) {
        data = val;
        left = right = nullptr;
    }
};*/

class Solution {
  public:
  void helper(Node* root){
      if(root==NULL) return ;
      Node *temp=root->left;
      root->left=root->right;
      root->right=temp;
      helper(root->left);
      helper(root->right);
  }
    void mirror(Node* root) {
     helper(root);
   //  return root;
        
    }
};
```

*Generated on: 18/10/2026, 11:12:38 am*