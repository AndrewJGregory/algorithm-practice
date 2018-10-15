# Plus One

## High level idea

There are three distinct cases, of which the sample test inputs only demonstrate one of these cases. The **first case** is a number that does not have a terminating 9. The cases of `[1, 2, 3]` and `[4, 3, 2, 1]` are both examples of this simple case, where the answer is obtained merely by adding one to the last digit and returning the array. The other two cases are more complicated because of the "carry-over" effect of adding one to a 9. If each spot in the array is one digit, then an input of `[9]` would produce `[1, 0]`. The array has changed in size and no longer resembles the original array. Therefore, the **second case** is when the input is _all nines_, such as `[9, 9, 9, 9]`, which produces `[1, 0, 0, 0, 0]`. The **third case** is where there are some nines, such as `[1, 0, 8, 9]`, which is `[1, 0, 9, 0]`. There is a distinction between the second and third case because in the second case, _the resultant array is longer than the original array_ whereas in the third case, the resultant array is the same length as the input array.

The first case is the most trivial and can be checked for immediately in either solution. Now, the second and third cases can be handled. In either case, determining where the 9s end from the right of the array is critical because this determines how many digits will change in the array. Once it is known where the 9s end, then the digits can be changed to reflect "adding one" to them. For instance, in the array of `[1, 0, 8, 9]`, the index where there are no more 9s is index 2. Therefore, that index can be incremented by 1 and everything to the right of it can be set to 0. If the digits are all 9s, then this means that the index that is being checked will eventually hit -1, which would give a falsey value in either language. In the second case, where there are all 9s, the solution is merely a leading 1 followed by zeroes. The quantity of zeroes is the original length of the all 9s array. For `[9]` which gives `[1, 0]`, there is 1 zero added, which is the size of the original array. For `[9, 9]`, which gives `[1, 0, 0]`, there are two zeroes added, which is the size of the original array.

## Time and space complexity

Let `n` be the length of the input:

- Time: `O(n)` <br>
- Space: `O(1)` <br>

The worst case is when there are all 9s, because the first loop would check every single element in the array.
