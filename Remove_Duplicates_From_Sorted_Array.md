# Problem: Remove duplicates from sorted array
- **Difficulty**: Easy
- **Link**: [LeetCode Problem Link](https://leetcode.com/problems/remove-duplicates-from-sorted-array/description/)

---

## Problem Description
Given an integer array nums sorted in non-decreasing order, remove the duplicates in-place such that each unique element appears only once. The relative order of the elements should be kept the same. Then return the number of unique elements in nums.

Consider the number of unique elements of nums to be k, to get accepted, you need to do the following things:

Change the array nums such that the first k elements of nums contain the unique elements in the order they were present in nums initially. The remaining elements of nums are not important as well as the size of nums.
Return k.

Example 1:

Input: nums = [1,1,2]
Output: 2, nums = [1,2,_]
Explanation: Your function should return k = 2, with the first two elements of nums being 1 and 2 respectively.
It does not matter what you leave beyond the returned k (hence they are underscores).

---

## Solution
### **Approach**
1. This approach uses two pointers: one (slow) keeps track of the position for the next unique element, and the other (fast) scans the array. Whenever a new unique element is found, it is moved to the position pointed to by slow, ensuring duplicates are removed in-place.
### **Complexity**
- **Time Complexity**: O(n)
- **Space Complexity**: O(1)

---

### **Code (Java)**

```java
class Solution {
    public int removeDuplicates(int[] nums) {
        int slow = 0 ; 
        for (int fast = 1; fast < nums.length ; fast++){
            if (nums[fast] != nums[slow]) {
                slow++;
                nums[slow] = nums[fast];
            }
        }
        return slow + 1; 
    }
}
