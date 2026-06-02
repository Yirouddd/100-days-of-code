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

## 4. Find the center node
leetcode 876 (easy)

``` c
1 -> 2 -> 3 -> 4 -> 5
```
return 3

**Method： fast and slow pointer**  
fast 每次走 2 步，slow 每次走 1 步。
当 fast 到终点时，slow 正好走了一半。

``` c
ListNode* slow = head;
ListNode* fast = head;

while(fast && fast->next){

    slow = slow->next;
    fast = fast->next->next;
}

return slow;
```

---

## 5. Linked List Cycle

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

``` c
while(fast && fast->next){

    slow = slow->next;
    fast = fast->next->next;

    if(slow == fast)
        return true;
}
```

---

## 6. Cycle entrance
leetcode 142

example
``` c
1 -> 2 -> 3 -> 4
     ^         |
     |_________|
```
retuen 2

---

## 7. Combine 2 ordered linked list
leetcode 21  
1->3->5 and 2->4->6  
to 1->2->3->4->5->6

``` c
ListNode dummy(0);
ListNode* tail = &dummy;
```

``` c
while(l1 && l2){

    if(l1->val < l2->val){

        tail->next = l1;
        l1 = l1->next;
    }
    else{

        tail->next = l2;
        l2 = l2->next;
    }

    tail = tail->next;
}
```

``` c
tail->next = l1 ? l1 : l2;
```

## 8. Delete the nth node


