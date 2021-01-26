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

迭代框架

```java
while(node != null || !stack.isEmpty()) {
    while (node != null) {
        stack.push(node);
        // 先序遍历
        node = node.left;
    }
    node = stack.pop();
    // 中序遍历
    node = node.right;
    // 后序遍历
}
```

Python实现

```python
  
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

def postorderTraversal(self, root):
    """
    :type root: TreeNode
    :rtype: List[int]
    """
    stack, ans = [], []
    prev = None
    while root or stack:
        while root:
            stack.append(root)
            root = root.left
        root = stack.pop()
        if not root.right or root.right == prev:
            ans.append(root.val)
            prev = root
            root = None
        else:
            stack.append(root)
            root = root.right
    return ans
```


