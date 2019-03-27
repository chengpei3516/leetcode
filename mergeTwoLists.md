# 合并两个有序链表

>题目描述：将两个有序链表合并为一个新的有序链表并返回。新链表是通过拼接给定的两个链表的所有节点组成的。 
>
>**示例：**
>
>```
>输入：1->2->4, 1->3->4
>输出：1->1->2->3->4->4
>```

## 代码

~~~java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) { val = x; }
 * }
 */
class Solution {
    
    public ListNode mergeTwoLists(ListNode l1, ListNode l2) {
        ListNode listNode = new ListNode(0);
        ListNode current = listNode;
        while (l1 != null && l2 != null) {
            if (l1.val > l2.val) {
                current.next = l2;
                current = current.next;
                l2 = l2.next;
            } else {
                current.next = l1;
                current = current.next;
                l1 = l1.next;

            }
        }
        if (l1 == null) {
            current.next = l2;
        } else {
            current.next = l1;
        }
        return listNode.next;
    }
}
~~~

