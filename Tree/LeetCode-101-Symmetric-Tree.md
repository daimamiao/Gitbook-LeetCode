---
title: 'LeetCode 101:Symmetric Tree'
date: 2016-08-17 09:07:21
tags:
categories:
thumbnail:
---
Given a binary tree, check whether it is a mirror of itself (ie, symmetric around its center).

For example, this binary tree [1,2,2,3,4,4,3] is symmetric:
```
    1
   / \
  2   2
 / \ / \
3  4 4  3
```
But the following [1,2,2,null,3,null,3] is not:
```
    1
   / \
  2   2
   \   \
   3    3
```

### Code
```c
int isSymmetricHelp(struct TreeNode *left, struct TreeNode *right) {
    if (left == NULL || right == NULL) {
        return left == right;
    }
    if (left->val != right->val) {
        return false;
    }
    return isSymmetricHelp(left->left, right->right) && isSymmetricHelp(left->right, right->left);
}
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     struct TreeNode *left;
 *     struct TreeNode *right;
 * };
 */
bool isSymmetric(struct TreeNode* root) {
    return root == NULL || isSymmetricHelp(root->left, root->right);
}
```