## 01. LCA in Binary Tree

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/lowest-common-ancestor-in-a-binary-tree/1)

### Problem Description

**Task:** Given the root of a binary tree with all unique values and two nodes value, n1 and n2. Find the lowest common ancestor of the given two nodes. Both node values are always present in the Binary Tree.Note: LCA is the first common ancestor of both the nodes n1 and n2 from bottom of tree.Examples:Input: root = [1, 2, 3, 4, 5, 6, 7], n1 = 4, n2 = 5 Output: 2

#### Examples

##### Example 1

- **Output:**
```text
3
```
- **Explanation:** LCA of 7 and 8 is 3.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(n)

### Accepted Solutions (1)

#### Solution 1 (C++)

- **Submitted:** 2026-10-18 12:29:25
- **Status:** Correct
- **Marks:** 4

```cpp
/* Structure of binary tree node
class Node {
public:
    int data;
    Node* left;
    Node* right;

    Node(int val) {
        data = val;
        left = right = nullptr;
    }
};*/

class Solution {
  public:
  bool exist(Node* root ,int target){
         if(root==NULL) return false;
      if(root->data==target) return true;
     // if(root==NULL) return false;
      return exist(root->left,target)|| exist(root->right,target);
      
        }
    Node* lca(Node* root, int n1, int n2) {
        if(root->data==n1 || root->data==n2) return root;
       else if (exist(root->left,n1)&& exist(root->right,n2)) return root;
       else if (!exist(root->left,n1)&& !exist(root->right,n2)) return root;
       else if (exist(root->left,n1)&& !exist(root->right,n2)) return lca(root->left,n1,n2);
       else if (!exist(root->left,n1)&& exist(root->right,n2)) return lca(root->right,n1,n2);
        
    }
};
```

*Generated on: 18/10/2026, 12:29:42 pm*