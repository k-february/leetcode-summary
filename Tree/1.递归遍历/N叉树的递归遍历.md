### N叉树的前后序递归遍历
```cpp
// N叉树递归遍历模版
// 前序遍历在这里处理root
for (auto& c : root->children) {
    dfs(c, ...)
}
// 后序遍历在这里处理root
```

相关题型:
-   前序遍历:**[`589. N-ary Tree Preorder Traversal`](https://leetcode.cn/problems/n-ary-tree-preorder-traversal/description/)**
-   后序遍历:**[`590. N-ary Tree Postorder Traversal`](https://leetcode.cn/problems/n-ary-tree-postorder-traversal/description/)**


#### 前序遍历
Given the  `root`  of an n-ary tree, return  _the preorder traversal of its nodes' values_.
Nary-Tree input serialization is represented in their level order traversal. 
Each group of children is separated by the null value (See examples)

**Example 1:**
>**Input:** `root = [1,null,3,2,4,null,5,6]`
>
>**Output:** `[1,3,5,6,2,4]`
>
>![](https://assets.leetcode.com/uploads/2018/10/12/narytreeexample.png)
>

**Example 2:**
>**Input:** root = `[1,null,2,3,4,5,null,null,6,7,null,8,null,9,10,null,null,11,null,12,null,13,null,null,14]`
>
>**Output:** `[1,2,3,6,7,11,14,4,8,12,5,9,13,10]`
>
>![](https://assets.leetcode.com/uploads/2019/11/08/sample_4_964.png)
>

**Constraints:**

-   The number of nodes in the tree is in the range  `[0, 104]`.
-   `0 <= Node.val <= 104`
-   The height of the n-ary tree is less than or equal to  `1000`.

**Follow up:**  Recursive solution is trivial, could you do it iteratively?

```cpp
// 前序遍历
class Solution {
public:
    void dfs(TreeNode* root, vector<int>& ans) {
        if (!root) {
            return;
        }
        ans.emplace_back(root->val);
        for (auto& p : root->children) {
            dfs(p, ans);
        }
        return;
    }

    vector<int> preorder(TreeNode* root) {
        vector<int> ans;
        dfs(root, ans);
        return ans;    
    }
};
```
* 时间复杂度：$O(n)$
* 空间复杂度：$O(n)$

#### 后序遍历
Given the  `root`  of an n-ary tree, return  _the preorder traversal of its nodes' values_.
Nary-Tree input serialization is represented in their level order traversal. 
Each group of children is separated by the null value (See examples)

**Example 1:**
>**Input:** root = [1,null,3,2,4,null,5,6]
>
>**Output:** [1,3,5,6,2,4]
>
>![](https://assets.leetcode.com/uploads/2018/10/12/narytreeexample.png)
>

**Example 2:**
>**Input:** root = [1,null,2,3,4,5,null,null,6,7,null,8,null,9,10,null,null,11,null,12,null,13,null,null,14]
>
>**Output:** [1,2,3,6,7,11,14,4,8,12,5,9,13,10]
>
>![](https://assets.leetcode.com/uploads/2019/11/08/sample_4_964.png)
>

**Constraints:**

-   The number of nodes in the tree is in the range  `[0, 104]`.
-   `0 <= Node.val <= 104`
-   The height of the n-ary tree is less than or equal to  `1000`.

**Follow up:**  Recursive solution is trivial, could you do it iteratively?
```cpp
// 后序遍历
class Solution {
public:
    void dfs(Node* root, vector<int>& ans) {
        if (!root) {
            return;
        }
        for (auto& p : root->children) {
            dfs(p, ans);
        }
        ans.emplace_back(root->val);
        return;
    }

    vector<int> postorder(Node* root) {
        vector<int> ans;
        dfs(root, ans);
        return ans;
    }
};
```
* 时间复杂度：$O(n)$
* 空间复杂度：$O(n)$