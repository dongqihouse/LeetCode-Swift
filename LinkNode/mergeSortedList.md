# 合并2个有序链表

https://leetcode-cn.com/problems/merge-two-sorted-lists/


```swift
class ListNode {
    var val: Int
    var next: ListNode?
    public init() { self.val = 0; self.next = nil; }
    public init(_ val: Int) { self.val = val; self.next = nil; }
    public init(_ val: Int, _ next: ListNode?) { self.val = val; self.next = next;}
}

class Solution {
    func mergeTwoLists(_ list1: ListNode?, _ list2: ListNode?) -> ListNode? {
        // 1. 新起一个listNode来存储
        let dummy = ListNode(0)
        var node = dummy
        
        var l1 = list1
        var l2 = list2
        
        while l1 != nil && l2 != nil {
            if l1!.val > l2!.val {
                node.next = l2
                l2 = l2!.next
            } else {
                node.next = l1
                l1 = l1!.next
            }
            
            // 最重要的事补尾结点
            node = node.next!
        }
        
        node.next = l1 ?? l2
        
        return dummy.next
    
    }
}

```