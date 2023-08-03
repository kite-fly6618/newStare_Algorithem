# 题目 移除元素
给你一个数组 nums 和一个值 val，你需要 原地 移除所有数值等于 val 的元素，并返回移除后数组的新长度。

不要使用额外的数组空间，你必须仅使用 O(1) 额外空间并 原地 修改输入数组。

元素的顺序可以改变。你不需要考虑数组中超出新长度后面的元素。



# 思路
快慢指针，实现数组的更新，遇到非目标值时候，意味着是不需要删除的，慢指针向前，左后返回慢指针的长度即使删除目标值后的数组长度

# 代码
```js
var removeElement = function(nums, val) {
    let len = nums.length;
    let slow = 0;
    // let fast = 0;
    for(let fast = 0;fast <len;fast++) {
        if(nums[fast] != val) {
            nums[slow++] = nums[fast]
        }
    }
    return slow;
}
```
# 复杂度
时间复杂度O(n)
空间复杂度O(1)
