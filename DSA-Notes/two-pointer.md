# Two Pointers

常见题其实可以分成几类

## 1. 快慢指针：一个负责扫描，一个负责放结果
适合：
```text
删除 / 移动 / 去重
```
例如：
```python
int slow = 0;

for (int fast = 0; fast < nums.size(); fast++) {
    if (nums[fast] != 0) {
        nums[slow] = nums[fast];
        slow++;
    }
}
```

理解成：
```text
fast：去找有用的元素
slow：下一个有用元素该放的位置
```
类似题：

26 Remove Duplicates
27 Remove Element
283 Move Zeroes

---

## 2. 左右指针：从两边往中间靠
适合：
```text
反转 / 回文 / 两数之和
```
例如：
```python
int left = 0;
int right = s.size() - 1;

while (left < right) {
    if (s[left] != s[right]) return false;
    left++;
    right--;
}
```
理解成：
```text
left 看左边
right 看右边
逐渐向中间检查
```
类似题：

125 Valid Palindrome
167 Two Sum II
344 Reverse String

---
## 3. 滑动窗口：左右指针维护一个区间
适合：
```text
最长 / 最短 / 子数组 / 子串
```
例如：
```python
int left = 0;

for (int right = 0; right < nums.size(); right++) {
    // 把 nums[right] 加进窗口

    while (窗口不合法) {
        // 移除 nums[left]
        left++;
    }

    // 更新答案
}
```
理解成：
```text
right：扩大窗口
left：缩小窗口
```
类似题：

3 Longest Substring Without Repeating Characters
209 Minimum Size Subarray Sum
424 Longest Repeating Character Replacement
