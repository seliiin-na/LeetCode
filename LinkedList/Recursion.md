#### 0021-Merge 2 Sorted Lists

```cpp
ListNode* mergeTwoLists(ListNode* list1, ListNode* list2) { 
    if (list1 == nullptr)
        return list2;
    else if (list2 == nullptr)
        return list1;

    // if value pointend by l1 pointer is less than equal to value pointed by l2 
    // pointer, call recursively l1 -> next and whole l2 list.

    else if (list1->val <= list2->val) {
        list1->next = mergeTwoLists(list1->next, list2);
        return list1;
    }
    else {
        list2->next =  mergeTwoLists(list1, list2->next);
        return list2;
    }
}
```
