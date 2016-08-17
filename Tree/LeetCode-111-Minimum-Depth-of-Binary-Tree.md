---
title: 'LeetCode 111:Minimum Depth of Binary Tree'
date: 2016-08-17 09:39:00
tags:
categories:
thumbnail:
---
Given a binary tree, find its minimum depth. <!--more-->

The minimum depth is the number of nodes along the shortest path from the root node down to the nearest leaf node.

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
    int minDepth(TreeNode* root) {
        if(root == NULL) {
            return 0;
        }
        int left = minDepth(root->left);
        int right = minDepth(root->right);
        return (left == 0 || right == 0) ? left + right + 1: min(left,right) + 1;
    }
};
```