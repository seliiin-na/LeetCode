[Problem Link](https://leetcode.com/problems/palindrome-linked-list/description/)

### Things to Note
1. use 2 running men technique to find middle of list (a fast & a slow pointer) -- if len(list) is odd, include the mid point in 1st half
2. reverse the 2nd half of the list in place (*pointer manipulation!!)
```python
    prev = None
    curr = head
    while (curr != None):
        # use temp to grab curr's next in forward direction before losing it!
        temp = curr.next
        curr.next = prev
        prev = curr
        curr = temp
    return prev  
```
4. compare 1st half & 2nd half one by one, until 2nd half reaches end
5. reverse back 2nd half


```python
class Solution:
    def end_of_1st_half(self, head) -> ListNode:
        # use 2 running men technique to find mid of list
        slow = head
        fast = head
        while fast.next != None and fast.next.next != None:
            fast = fast.next.next
            slow = slow.next

        return slow

    def reverse(self, head) -> ListNode:
        prev = None
        curr = head
        while (curr != None):
            temp = curr.next
            curr.next = prev
            prev = curr
            curr = temp
        # return head of reversed list
        return prev

    def isPalindrome(self, head: Optional[ListNode]) -> bool:
        # empty list or list with 1 elemt
        if head == None or head.next == None:
            return True
        
        result = True 
        # find mid point of list
        end_of_1st = self.end_of_1st_half(head)

        # reverse the 2nd half
        reversed_2nd  = self.reverse(end_of_1st.next)

        # compare the 2 halves
        while reversed_2nd != None:
            if head.val != reversed_2nd.val:
                result = False
            head = head.next
            reversed_2nd = reversed_2nd.next

        # reverse back the 2nd half
        end_of_1st.next = self.reverse(reversed_2nd)

        return result
```
