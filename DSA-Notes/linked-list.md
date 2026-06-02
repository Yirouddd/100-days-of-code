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
