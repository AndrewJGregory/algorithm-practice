# MAX CONSECUTIVE ONES

```rb
def find_max_consecutive_ones(nums)
    best_streak = 0
    current_streak = 0
    nums.each do |num|
        if num == 1
            current_streak += 1
        else
            best_streak = current_streak if current_streak > best_streak
            current_streak = 0
        end
    end
    [best_streak, current_streak].max
end
```

```js
var findMaxConsecutiveOnes = function(nums) {
  let bestStreak = 0;
  let currentStreak = 0;
  nums.forEach(num => {
    if (num) {
      currentStreak++;
    } else {
      if (currentStreak > bestStreak) bestStreak = currentStreak;
      currentStreak = 0;
    }
  });
  return Math.max(bestStreak, currentStreak);
};
```
