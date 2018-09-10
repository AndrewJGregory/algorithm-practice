# BEST TIME TO BUY AND SELL STOCK

### High level idea

There are three cases to think about that lead to the solution of the problem. Here they are:

1. [1, 5, 6, 2, 3] (best profit = 6)
2. [100, 2, 7] (best profit = 5)
3. [2, 4, 1] (est profit = 2)

The overall constraints of the problem to keep in mind are that one cannot sell a stock before buying it and the maximum profit must be returned. An intuitive way to understand this is to set the first day's price to the lowest in the array and the second day's price to the highest in the array. This almost works except for the fact that the second day needs to come after the first day. These examples serve to illustrate how this approach needs to be modified in order to correctly work.

The first example is the easiest to understand because the minimum price is the first day and the maximum price is after it. The intuitive solution above would work.

However, with the second example, things become tricky because the maximum price is actually on the first day however there are no days that come before the first day so no stock can be sold. This second example shows the necessity of resetting the second day's price if it is before the first day because the stock cannot be sold before it is bought. If only the maximum and minimum prices were taken into account, then no profit could be computed because the price of 100 comes before the price of 2, which violates the constraints of the problem. If the second day happens to be before the first day for whatever reason, then reset it and start over to find a viable price to sell the stock at.

Finally, the last example shows that the first day's price cannot be blindly reset continuosly and that the profit must be calculated as the array is traversed. If the profit is calculated after the loop is over then the first day's price would be 1 but that comes after the second day, so a profit of 0 would be returned because the stock cannot be sold before it is bought. As such, the profit is computed again and again and if it happens to be better than the profit that has been seen so far, accordingly set the best profit. This is the last block in the loop for both solutions.

### Time and space complexity

Let `n` be how many prices there are: <br>

- Time: `O(n)` <br>
- Space: `O(1)` <br>

No extra space is used except for a couple of variables that do not depend on the input size. Every price is checked so the time complexity is linear with respect to the size of the input.
