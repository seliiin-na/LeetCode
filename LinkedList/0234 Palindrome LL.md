[Problem Link](https://leetcode.com/problems/palindrome-linked-list/description/)

### Things to Note
1. use 2 running men technique to find middle of list (a fast & a slow pointer) -- if len(list) is odd, include the mid point in 1st half
2. reverse the 2nd half of the list in place (*pointer manipulation!!)
```python
    prev = null
    curr = head
    while (curr != null):
        # use temp to grab curr's next in forward direction before losing it!
        temp = curr.next
        curr.next = prev
        prev = curr
        curr = temp
    return prev  
```
4. compare 1st half & 2nd half one by one, until 2nd half reaches end
5. reverse back 2nd half
