---
layout:     post
title:      "[leetcode] 二叉树的非递归遍历"
subtitle:   ""
date:       2021-01-26 18:04:00
author:     "Nalido"
header-img: "img/post-bg-2015.jpg"
catalog: true
tags:
    - leetcode
    - python
---

https://leetcode.com/problems/binary-tree-inorder-traversal/
```python
def inorderTraversal(self, root):
    """
    :type root: TreeNode
    :rtype: List[int]
    """
    stack, ans = [], []
    while root or stack:
        while root:
            stack.append(root)
            root = root.left
        root = stack.pop()
        ans.append(root.val)
        root = root.right
    return ans
    
def preorderTraversal(self, root):
    stack = []
    node = root
    while stack or node:
        while node:
            res.append(node.val)
            stack.append(node)
            node = node.left
        node = stack.pop()
        node = node.right
    return res
```
