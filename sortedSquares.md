# 给你一个按 非递减顺序 排序的整数数组 nums，返回 每个数字的平方 组成的新数组，要求也按 非递减顺序 排序。

# 思路
双指针，数组中平方的最大值一定在数组平方的两端，所以比较两端的大小即可挑出最大值

# 代码
```js
var sortedSquares = function(nums) {
    let len = nums.length-1;
    let i = 0,j = len,k=len;
    let res = new Array(len).fill(0);
    while(i<=j) {
        let left = nums[i]*nums[i];
        let right = nums[j]*nums[j];
        if (left>right) {
            res[k--] = left;
            i++
        } else {
            res[k--] = right;
            j--
        }
    }
    return res;
}
```

# 复杂度
时间o(n)
空间o(n)