# C++ STL
STL stands for Standard Template Library in C++.  
## What is STL?
The STL is a powerful set of C++ template classes and functions that provide common programming data structures and algorithms. 
It's a fundamental part of the C++ standard library.

## Main Components of STL:
#### Containers - Data structures that store objects
  1. Sequence containers: 维持顺序的容器
       - vector：动态数组   
       - list：双向链表  
       - deque：双端队列
       - array：固定大小的数组
       - forward_list：单向链表
  2. Container adaptors  
       - stack: 后入先出（LIFO）的数据结构，默认基于deque实现。stack常用于深度优先搜索，一些字符串匹配问题以及单调栈问题。  
       - queue：先入先出（FIFO）的数据结构，默认基于deque实现。queue常用于广度优先搜索。  
       - priority_queue： 最大值优先的数据结构，默认基于vector实现堆结构。  
  4. Associative containers
       - set  
       - multiset  
       - map  
       - multimap  
  6. Unordered associative containers:  
       - unordered_set  
       - unordered_multiset  
       - unordered_map  
       - unordered_multimap  
