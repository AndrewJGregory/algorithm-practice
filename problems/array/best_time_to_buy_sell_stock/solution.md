# BEST TIME TO BUY AND SELL STOCK

```rb
def max_profit(prices)
#    7 6 4 3 1
# 100 1 5 (example of the || conditional on line 11)
  # maximum is the first num so it'd never reset otherwise - but it should because it's behind the min
  current_profit = 0
  best_profit = 0
  first_day = { price: prices.first, day: 0 }
  second_day = { price: prices.first, day: 0}
  prices.each_with_index do |price, day|
    if price > second_day[:price] || second_day[:day] < first_day[:day]
      second_day[:price] = price
      second_day[:day] = day
    end

    if price < first_day[:price]
      first_day[:price] = price
      first_day[:day] = day
    end

    if first_day[:day] < second_day[:day]
      current_profit = second_day[:price] - first_day[:price]
      best_profit = current_profit if best_profit.zero? || current_profit > best_profit
    end
  end
 best_profit
end
```

```js
var maxProfit = function(prices) {
  let firstStock = { price: prices[0], day: 0 };
  let secondStock = { price: prices[0], day: 0 };
  let bestProfit = 0;
  let currentProfit = 0;
  prices.forEach((price, day) => {
    if (price >= secondStock.price || secondStock.day < firstStock.day)
      secondStock = { price, day };
    if (price < firstStock.price) firstStock = { price, day };
    if (firstStock.day < secondStock.day) {
      currentProfit = secondStock.price - firstStock.price;
      if (bestProfit === 0 || currentProfit > bestProfit)
        bestProfit = currentProfit;
    }
  });
  return bestProfit;
};
```
