# 给定一棵二叉树的根节点 root ，请找出该二叉树中每一层的最大值。

# BFS
```js
var largestValues = function(root) {
    if(!root) {return []}
    let res = []
    let queen = [root]
    while(queen.length) {
        let len = queen.length;
        let maxVal = -Infinity;
        // let arr = [];
        while(len>0) {
            len--;
            let item = queen.shift()
            maxVal = Math.max(item.val,maxVal)
            if(item.left) {
                queen.push(item.left)
            }
            if(item.right) {
                queen.push(item.right)
            }
        }
        res.push(maxVal)
    }
    return res;
};
```

# DFS
```js
var largestValues = function(root) {
    if (!root) {
        return [];
    }
    const res = [];
    const dfs = (res, root, curHeight) => {
        if (curHeight === res.length) {
            res.push(root.val);
        } else {
            res.splice(curHeight, 1, Math.max(res[curHeight], root.val));
        }
        if (root.left) {
            dfs(res, root.left, curHeight + 1);
        }
        if (root.right) {
            dfs(res, root.right, curHeight + 1);
        }
    }
    dfs(res, root, 0);
    return res;
};
```