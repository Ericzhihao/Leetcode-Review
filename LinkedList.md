# 24.swap pairs

```
public ListNode swapPairs(ListNode head) {
        if(head == null || head.next == null){
            return head; //递归终止条件
        }
        ListNode first = head; //第一个
        ListNode second = head.next; //第二个
        first.next = swapPairs(second.next); //第一个的下一个指向递归完成后的第二个的下一个
        second.next = first; //完成交换
        return second;
    }
```
Time Complexity: O(n)
Space Complexity: O(n)    也可以用迭代做，思路更清晰一点



