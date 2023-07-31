# 给定一个单链表 L 的头节点 head ，单链表 L 表示为：
# L0 → L1 → … → Ln - 1 → Ln
# 请将其重新排列后变为：
# L0 → Ln → L1 → Ln - 1 → L2 → Ln - 2 → …
# 不能只是单纯的改变节点内部的值，而是需要实际的进行节点交换。
 

# 思路
将链表节点放置于数组中，使用双向队列，从两头取到节点，重新排列，把最后节点值为空即可

```js
var reorderList = function(head) {
     let queen = [];
     let p = head;
     while(p){
         queen.push(p);
         p=p.next;
     }
     while(queen.length>2){
         let h = queen.shift()
         let t = queen.pop()
         t.next = h.next
         h.next = t
     }
     queen[queen.length-1].next = null
     return head
}; 
```