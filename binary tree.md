# Binary Tree

## 543. Diameter of Binary Tree

```
class Solution {
    int ans = 1; //全局变量记录ans， 一条路径的最大长度为该路径经过的节点数减1，所以从root开始节点数为1
    public int diameterOfBinaryTree(TreeNode root) {
        max(root); 
        return ans - 1;
    }
    public int max(TreeNode node){
        if(node == null){
            return 0; //当访问到空节点时， 返回0
        }
        int leftMax = max(node.left); //递归计算左子树的最大深度
        int rightMax = max(node.right);//递归计算右子树的最大深度
        ans = Math.max(ans, leftMax + rightMax + 1); //记录最多的节点数
        return Math.max(leftMax , rightMax) + 1; //返回当前子树的最大深度
    }
}
```
