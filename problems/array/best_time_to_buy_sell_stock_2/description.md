# BEST TIME TO BUY AND SELL STOCK 2

### High level idea

There are multiple cases to consider:

1. [100, 2, 7]
2. [7,1,5,3,6,4]
3. [5, 4, 3, 2, 1]
4. [1, 2, 3, 4, 5]

Since multiple transcations are allowed, multiple profits can be made. The question is, when should the stock be sold? The stock should be sold when the sell price drops to less than what it already is. In the case of example 2, the price of `3` is less than the price of `5`, so the stock should be sold for a profit and another stock should be bought to start the process over again. This happens once more with the last three prices of case 2, the stock is bought at a price of 3 but sold at a price of 6 because it cannot be sold for anymore since 4 is less than 6.

In case 3, no profit can be made so do not buy or sell any stock.

In case 4, the stock can be bought on first day and sold on the last day for the maximum amount of profit.

In case 1, the important thing to keep in mind is that the sell price might have to be reset if it comes before the buy price because this is a scenario that violates the question's constraint of the stock has to be bought before it is sold.

With these cases in mind, the algorithm can be written. If the price is lower than what has been seen previously, update the buy info accordingly. If the price is higher than what has been seen previously or if the sell day comes before the buy day, then update the sell info accordingly. If the price drops to a lower value than the sell price, sell the stocks for a profit and add this to the total profit. Once the stocks are sold and the total profit is updated, the current profit can be set to zero to avoid the edge case in case 2. In this case, the stocks would be sold on the last day and the total profit would be updated. However, due to case 4, the current profit is also added outside of the iteration because it does not satisfy the "drop" in price that the algorithm is looking for. To avoid adding the profit twice, the current profit can be set to zero once it has been added to the final profit.

### Time and space complexity

Let `n` be the size of the prices array:

- Time: `O(n)` <br>
- Space: `O(1)`

The entire array will be traversed and while multiple variables are initialized, the size of these variables do not depend on the size of the prices array.
