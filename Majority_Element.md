# Problem: Majority Element
- **Difficulty**: Easy
- **Link**: [LeetCode Problem Link](https://leetcode.com/problems/majority-element/description/)

---

## Problem Description

Given an array nums of size n, return the majority element.

The majority element is the element that appears more than ⌊n / 2⌋ times. You may assume that the majority element always exists in the array.

 

Example 1:

Input: nums = [3,2,3]
Output: 3

Example 2:

Input: nums = [2,2,1,1,1,2,2]
Output: 2


---

## Solution
### **Approach**
1. Think about how if it is the majority of the numbers, if we compare it with every other number we will still have a numerical majority.

   
### **Complexity**
- **Time Complexity**: O(n)
- **Space Complexity**: O(1)

---

### **Code (Java)**

```java
class Solution {
    public int majorityElement(int[] nums) {
        int candidate = 0;
        int count = 0;

        for (int num : nums) {
            if (count == 0) {
                candidate = num;
            }
            if (num == candidate) {
                count += 1;
            } else {
              count -= 1; 
            }
        }

        
        return candidate;  
    }
}
