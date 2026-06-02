# 8 basic question type of LINKEDLIST

#### Definition of Linked List
``` c
struct ListNode {
    int val;
    ListNode *next;

    ListNode(int x) : val(x), next(nullptr) {}
};
```

## 1. Traverse
``` c
ListNode* cur = head;

while(cur){
    cout << cur->val << " ";
    cur = cur->next;
}
```

---

## 2. Inverse
leetcode 206
from 
``` c
1 -> 2 -> 3 -> null
```
to
```c
3 -> 2 -> 1 -> null
```

3 pointers method:
``` c
ListNode* prev = nullptr;
ListNode* cur = head;

while(cur){

    ListNode* nxt = cur->next;

    cur->next = prev;

    prev = cur;
    cur = nxt;
}

return prev;
```

---

## 3. Delete node
leetcode 203

use Dummy node since head could be deleted
```c
ListNode dummy(0);
dummy.next = head;

ListNode* cur = &dummy;
```

traverse
``` c
while(cur->next){

    if(cur->next->val == val)
        cur->next = cur->next->next;
    else
        cur = cur->next;
}
```

---

## Find the center node
leetcode 876

``` c
1 -> 2 -> 3 -> 4 -> 5
```
return 3

**fast and slow pointer**





---

Linked List Cycle

```python
slow 每次走1步
fast 每次走2步

无环：
    fast先到null

有环：
    fast最终追上slow

相遇 => true
到null => false
```
