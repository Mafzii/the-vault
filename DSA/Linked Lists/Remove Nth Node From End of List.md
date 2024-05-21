---
tags:
  - leetcode
  - medium
---
```
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def removeNthFromEnd(self, head: Optional[ListNode], n: int) -> Optional[ListNode]:
        # create node thats n places ahead
        n_fast = head
        for _ in range(n):
            n_fast = n_fast.next

        # get n_fast to last node
        curr = head
        while n_fast and n_fast.next:
            curr = curr.next
            n_fast = n_fast.next

        # check if end of the list
        if n_fast == None:
            # remove first node as n = length of the list
            return head.next
        elif curr.next != None:
            curr.next = curr.next.next
        else:
            curr.next = None

        return head
```
