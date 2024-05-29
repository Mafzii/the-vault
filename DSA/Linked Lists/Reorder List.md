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
    def reorderList(self, head: Optional[ListNode]) -> None:
        """
        Do not return anything, modify head in-place instead.
        """
        def reverseList(head: Optional[ListNode]) -> None:
            prev = None
            curr = head
            while curr:
                forward = curr.next
                curr.next = prev
                prev = curr
                curr = forward
            return prev

        fast = head.next
        slow = head
        while fast and fast.next:
            slow = slow.next
            fast = fast.next.next
        
        # slow has the middle to the end of the list
        rev = reverseList(slow)

		# merge the two 
        li = head
        while li and rev:
            temp1 = li.next
            temp2 = rev.next
            li.next = rev
            rev.next = temp1
            li = temp1
            rev = temp2
                
          
```