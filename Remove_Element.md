# Problem: Remove Element
- **Difficulty**: Easy
- **Link**: [LeetCode Problem Link](https://leetcode.com/problems/remove-element/)

---

## Problem Description

Given an integer array nums and an integer val, remove all occurrences of val in nums in-place. The order of the elements may be changed. Then return the number of elements in nums which are not equal to val.

Consider the number of elements in nums which are not equal to val be k, to get accepted, you need to do the following things:

Change the array nums such that the first k elements of nums contain the elements which are not equal to val. The remaining elements of nums are not important as well as the size of nums.
Return k.

Example 1:

Input: nums = [3,2,2,3], val = 3
Output: 2, nums = [2,2,_,_]
Explanation: Your function should return k = 2, with the first two elements of nums being 2.
It does not matter what you leave beyond the returned k (hence they are underscores).


---

## Solution
### **Approach**
1. the fast pointer checks value of each element in the array, if it is not equal to val, it copies the current element to the position of slow and then increases it 
What this does is the 1st slow elements will never contain the value of val. 
This does it in O(n). 
Use 2 pointers - a) Dynamic partitiioning, b) in place modification, c) simultaneous read and write. 

### **Complexity**
- **Time Complexity**: O(n)
- **Space Complexity**: O(1)

---

### **Code (Java)**

```java
class Solution {
    public int removeElement(int[] nums, int val) {
        int slow = 0 ; 
        for (int fast = 0 ; fast < nums.length ; fast++){
            if (nums[fast] != val){
                nums[slow] = nums[fast];
                slow++;
            }
        }
        return slow; 

    }
}