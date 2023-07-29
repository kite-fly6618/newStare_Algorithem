# 链表是否有环  
# 思路  1. 快慢指针，如果有环，则快慢指针必定相遇
#      2. 遍历链表，打上标签，如果遇到标签，则说明有环，不然则没有环
/**
 * @param {ListNode} head
 * @return {boolean}
 */
<!-- // var hasCycle = function(head) {
// var hasCycle = function (head) {
//     let slow = head, fast = head; // 乌龟和兔子同时从起点出发
//     while (fast && fast.next) {
//         slow = slow.next; // 乌龟走一步
//         fast = fast.next.next; // 兔子走两步
//         if (fast === slow) // 兔子追上乌龟（套圈），说明有环
//             return true;
//     }
//     return false; // 访问到了链表末尾，无环
// }; -->

```js
var hasCycle = function (head) {
    while(head&&head.next) {
        if(head.tag){
            return true
        }
        head.tag = true
        head=head.next   
    }
    return false;
}
```

# 时间复杂度空间复杂度
时间 O(n)
空间 
