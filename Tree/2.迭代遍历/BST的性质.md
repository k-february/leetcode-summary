### BST

#### BST的中序遍历必然为严格正序的序列
```cpp
// 中序遍历的模板
// BST的所有相关题型都可以复用模板加以解决
class Solution {
public:
    vector<int> inorderTraversal(TreeNode* root) {
        vector<int> ans;
        stack<TreeNode*> st;
        TreeNode* p = root;
        while (!st.empty() || p) {
            while (p) {
                st.push(p);
                p = p->left;
            }
            TreeNode* cur = st.top();
            st.pop();
            ans.emplace_back(cur->val);
            p = cur->right;
        }
        return ans;    
    }
};
```
* 时间复杂度：$O(n)$
* 空间复杂度：$O(n)$


相关题型:
- **[`98. Validate Binary Search Tree`](https://leetcode.cn/problems/binary-tree-inorder-traversal/description/)**
- **[`99. Recover Binary Search Tree`](https://leetcode.cn/problems/binary-tree-preorder-traversal/description/)**
- **[`230. Kth Smallest Element in a BST`](https://leetcode.cn/problems/binary-tree-postorder-traversal/description/)**
- **[`230. Kth Smallest Element in a BST`](https://leetcode.cn/problems/binary-tree-postorder-traversal/description/)**
- **[`230. Kth Smallest Element in a BST`](https://leetcode.cn/problems/binary-tree-postorder-traversal/description/)**
- **[`230. Kth Smallest Element in a BST`](https://leetcode.cn/problems/binary-tree-postorder-traversal/description/)**
- **[`230. Kth Smallest Element in a BST`](https://leetcode.cn/problems/binary-tree-postorder-traversal/description/)**

####
####
####
####
####