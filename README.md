# Stock Picker

**LEETCODE: Best Time to Buy and Sell Stock**

Have the function StockPicker(arr) take the array of numbers stored in arr which will contain integers that represent the amount in dollars that a single stock is worth, and return the maximum profit that could have been made by buying stock on day x and selling stock on day y where y > x. For example: if arr is [44, 30, 24, 32, 35, 30, 40, 38, 15] then your program should return 16 because at index 2 the stock was worth $24 and at index 6 the stock was then worth $40, so if you bought the stock at 24 and sold it at 40, you would have made a profit of $16, which is the maximum profit that could have been made with this list of stock prices.

If there is not profit that could have been made with the stock prices, then your program should return -1. For example: arr is [10, 9, 8, 2] then your program should return -1.

---

## THE SOLUTION

```
function StockPicker(arr) {
  let minPrice = Infinity;
  let maxProfit = -1;

  for (let price of arr) {
    if (price < minPrice) {
      minPrice = price; // Update the minimum price
    } else {
      maxProfit = Math.max(maxProfit, price - minPrice); // Update the maximum profit
    }
  }

  return maxProfit;
}
```


Time Complexity: O(n)

Space Complexity: O(1)
