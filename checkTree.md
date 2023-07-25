# 判断之和

```js
/**
 * @param {TreeNode} root
 * @return {boolean}
 */
var checkTree = function(root) {
    return root.val==root.left.val+root.right.val ? true  : false
};
```