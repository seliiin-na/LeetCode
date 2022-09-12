#### Things to note:
1. use iterative solution: need to add extra node pointers to keep track of next & prev


```cpp
ListNode* reverseList(ListNode* head) {
    // make extra variables to store curr->next and curr->prev
    ListNode *next = nullptr, *prev = nullptr;
    ListNode *curr = head;
    while (curr != nullptr) {
        next = curr->next;
        // actual reversing step:
        // make curr->prev the node that curr is pointing to
        curr->next = prev;

        // move prev & curr one node ovver:
        prev = curr; // order: must update prev BEFORE curr!
        curr = next; 
    }
    // this is returning the final starting node, which is the last node 
    // in the original list
    return prev;
}

```
