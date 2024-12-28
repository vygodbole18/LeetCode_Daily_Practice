# Problem: Remove duplicates from sorted arrays II
- **Difficulty**: Medium
- **Link**: [LeetCode Problem Link](https://leetcode.com/problems/remove-duplicates-from-sorted-array-ii/)

---

## Problem Description
Given an integer array nums sorted in non-decreasing order, remove some duplicates in-place such that each unique element appears at most twice. The relative order of the elements should be kept the same.

Since it is impossible to change the length of the array in some languages, you must instead have the result be placed in the first part of the array nums. More formally, if there are k elements after removing the duplicates, then the first k elements of nums should hold the final result. It does not matter what you leave beyond the first k elements.

Return k after placing the final result in the first k slots of nums.

Do not allocate extra space for another array. You must do this by modifying the input array in-place with O(1) extra memory.

Example 1:

Input: nums = [1,1,1,2,2,3]
Output: 5, nums = [1,1,2,2,3,_]
Explanation: Your function should return k = 5, with the first five elements of nums being 1, 1, 2, 2 and 3 respectively.
It does not matter what you leave beyond the returned k (hence they are underscores).

---

## Solution
### **Approach**
1. Use two pointers (slow and fast) to ensure that each unique element appears at most twice by checking if the current element differs from the element two positions before slow.

### **Complexity**
- **Time Complexity**: O(n)
- **Space Complexity**: O(1)

---

### **Code (Java)**

```java
class Solution {
    public int removeDuplicates(int[] nums) {
        int slow = 2; 
        for (int fast = 2; fast < nums.length;fast++) {
            if(nums[fast] != nums[slow - 2 ]){
                    nums[slow] = nums[fast];
                    slow++;
            } 
        }
        return slow;
    }
}
