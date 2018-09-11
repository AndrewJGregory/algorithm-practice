# BEST TIME TO BUY AND SELL STOCK 2

```rb
def max_profit(prices)
  totalProfit = 0
  currentProfit = 0
  buyInfo = { price: prices.first, day: 0 }
  sellInfo = { price: prices.first, day: 0 }
  day = 1
  while day < prices.length
    price = prices[day]
    if (price < sellInfo[:price] && buyInfo[:day] < sellInfo[:day])
      totalProfit += currentProfit
      buyInfo = { price: price, day: day }
      sellInfo = { price: price, day: day }
      currentProfit = 0
    end
    buyInfo = { price: price, day: day } if (price < buyInfo[:price])
    sellInfo = { price: price, day: day } if (price > sellInfo[:price] || buyInfo[:day] > sellInfo[:day])
    currentProfit = sellInfo[:price] - buyInfo[:price] if (buyInfo[:day] < sellInfo[:day])
    day += 1
  end
  totalProfit += currentProfit
  totalProfit
end
```

```js
var maxProfit = function(prices) {
  let totalProfit = 0;
  let currentProfit = 0;
  let firstDayInfo = { price: prices[0], day: 0 };
  let secondDayInfo = { price: prices[0], day: 0 };

  for (let day = 1; day < prices.length; day++) {
    let price = prices[day];
    if (firstDayInfo.day < secondDayInfo.day && price < secondDayInfo.price) {
      totalProfit += currentProfit;
      firstDayInfo = { price, day };
      secondDayInfo = { price, day };
      currentProfit = 0;
    }

    if (price < firstDayInfo.price) firstDayInfo = { price, day };
    if (price > secondDayInfo.price || secondDayInfo.day < firstDayInfo.day)
      secondDayInfo = { price, day };
    if (firstDayInfo.day < secondDayInfo.day)
      currentProfit = secondDayInfo.price - firstDayInfo.price;
  }
  totalProfit += currentProfit;
  return totalProfit;
};
```
