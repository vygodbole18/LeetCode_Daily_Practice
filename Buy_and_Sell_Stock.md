# Problem: Best time to buy and sell a stock 
- **Difficulty**: Easy
- **Link**: [LeetCode Problem Link](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/)

---

## Problem Description
You are given an array prices where prices[i] is the price of a given stock on the ith day.

You want to maximize your profit by choosing a single day to buy one stock and choosing a different day in the future to sell that stock.

Return the maximum profit you can achieve from this transaction. If you cannot achieve any profit, return 0.

 

Example 1:

Input: prices = [7,1,5,3,6,4]
Output: 5
Explanation: Buy on day 2 (price = 1) and sell on day 5 (price = 6), profit = 6-1 = 5.
Note that buying on day 2 and selling on day 1 is not allowed because you must buy before you sell.

Example 2:

Input: prices = [7,6,4,3,1]
Output: 0
Explanation: In this case, no transactions are done and the max profit = 0.

---

## Solution
### **Approach**
1. Think intuitively how in a single for loop we keep track of min price and profit. MinPrice ensures buy day always before the sell day  . Update the max profit in every loop. 
### **Complexity**
- **Time Complexity**: O(n)
- **Space Complexity**: O(1)

---

### **Code (Java)**

```java
class Solution {
    public int maxProfit(int[] prices) {
        int maxProfit = 0;
        int minPrice = prices[0]; 
        for (int i = 0 ; i < prices.length ; i ++) {
            minPrice = Math.min(minPrice, prices[i]);
            int profit = prices[i] - minPrice;
            maxProfit = Math.max(profit, maxProfit);

                
    }
    return maxProfit;
}

}