# 题目 209. 长度最小的子数组
给定一个含有 n 个正整数的数组和一个正整数 target 。

找出该数组中满足其和 ≥ target 的长度最小的 连续子数组 [numsl, numsl+1, ..., numsr-1, numsr] ，并返回其长度。如果不存在符合条件的子数组，返回 0 

# 思路
1.双重循环暴力破解
2.双指针，快指针在前，慢指针前进，如果不符合条件，快指针向前，一直找到最小的答案

# 代码
```js
var minSubArrayLen = function(target, nums) {
    let start = 0;
    let end = 0;
    let len = nums.length;
    let sum = 0;
    let ans = Infinity;
    while(end<len) {
        sum +=nums[end]
        while(sum>=target) {
            ans = Math.min(ans,end-start+1)
            sum -=nums[start]
            start++
        }
        end++
    }
    return ans === Infinity ? 0 : ans;
};
```

# 复杂度
时间：O(n)
空间：O(1)