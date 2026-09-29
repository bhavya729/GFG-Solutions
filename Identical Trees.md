## 01. Identical Trees

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/determine-if-two-trees-are-identical/1)

### Problem Description

**Task:** Given two binary trees with their root nodes r1 and r2, return true if both of them are identical, otherwise return false.Note: Two trees are identical when they have the same data and the arrangement of the data is also same.Examples:Input: r1 = [1, 2, 3, 4], r2 = [1, 2, 3, 4]Output: true

#### Examples

##### Example 1

- **Output:**
```text
false
```
- **Explanation:** Trees are not identical.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(h)

### Accepted Solutions (1)

#### Solution 1 (C++)

- **Submitted:** 2026-09-29 19:03:21
- **Status:** Correct
- **Marks:** 2

```cpp
/*
class Node {
public:
    int data;
    Node* left;
    Node* right;

    Node(int x) {
        data = x;
        left = nullptr;
        right = nullptr;
    }
};
*/
class Solution {
  public:
    bool isIdentical(Node* r1, Node* r2) {
        if(r1==NULL||r2==NULL){
            return r1==r2;
        }
      bool  isleftsame= isIdentical(r1->left,r2->left);
      bool  isrightsame= isIdentical(r1->right,r2->right);
      return isleftsame && isrightsame && r1->data==r2->data;
        
        
    }
};
```

*Generated on: 29/9/2026, 7:03:32 pm*