## 题目分析：

给定一个二叉排序树。将每个节点的值改为当前值与二叉排序树中所有比该节点大的值的和。

### 解题思路
二叉树的遍历。按`右子树 -> 根 -> 左子树`的顺序遍历, 并记录当前的和。复杂度`O(n)`.