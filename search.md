# 给定一个 n 个元素有序的（升序）整型数组 nums 和一个目标值 target  ，写一个函数搜索 nums 中的 target，如果目标值存在返回下标，否则返回 -1。

# 思路 左右区间往中间去，时间复杂度最低,O(logn),注意好区间的把握，左右闭区间，表示都有效，但是判断的时候需要注意边界的收缩

```js
var search = function(nums, target) {
    let len = nums.length-1;
    let head = 0;
    let tail = len;
    // let mid = 0;
    while(head<=tail) {
        let mid = head+((tail-head)>>2);
        if (nums[mid]>target) {
            tail = mid-1;
        }else if(nums[mid]<target) {
            head = mid+1;
        }else{
            return mid;
        }
    }
    return -1
};
```
# 复杂度
时间O(n)
空间O(1)
