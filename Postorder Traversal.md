## 01. Postorder Traversal

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/postorder-traversal/1)

### Problem Description

**Task:** Given the root of a Binary Tree, return its Postorder Traversal.

> **Note:** A postorder traversal first visits the left child (including its entire subtree), then visits the right child (including its entire subtree), and finally visits the node itself.

#### Examples

##### Example 1

- **Input:**
```text
root = [19, 10, 8, 11, 13]
```
- **Output:**
```text
[11, 13, 10, 8, 19]Explanation: The postorder traversal of the given binary tree is [11, 13, 10, 8, 19].
```

##### Example 2

- **Input:**
```text
root = [11, 15, N, 7]
```
- **Output:**
```text
[7, 15, 11]Explanation: The postorder traversal of the given binary tree is [7, 15, 11].
```

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (C++)

- **Submitted:** 2026-10-18 16:17:20
- **Status:** Correct
- **Marks:** 2

```cpp
/* Structure of Binary Tree Node
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
  void postorder(Node* root,vector<int>& ans){
      if(root==NULL) return;
      postorder(root->left,ans);
      postorder(root->right,ans);
      ans.push_back(root->data);
  }
    vector<int> postOrder(Node* root) {
        // code here
        vector<int> ans;
        postorder(root,ans);
        return ans;
        
    }
};
```

*Generated on: 18/10/2026, 4:17:34 pm*