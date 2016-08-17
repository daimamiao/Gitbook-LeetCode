---
title: 'LeetCode 104:Maximum Depth of Binary Tree'
date: 2016-08-17 09:28:39
tags:
categories:
thumbnail:
---
Given a binary tree, find its maximum depth. <!--more-->

The maximum depth is the number of nodes along the longest path from the root node down to the farthest leaf node.

### Code
```c
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode(int x) : val(x), left(NULL), right(NULL) {}
 * };
 */
class Solution {
public:
    int maxDepth(TreeNode* root) {
        return root == NULL ? 0 : max(maxDepth(root -> left), maxDepth(root -> right)) + 1;
    }
};
```