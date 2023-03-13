# Dots on domino's bone

This exercise was taken from [codewars](https://www.codewars.com/kata/6405f2bb2894f600599172fd)

## Task

To earn a huge capital, you need to have an unconventional mindset. Of course, with such a complex job, there must also be special mechanisms for recreation and entertainment. For this purpose, the casino came up with a special domino set. Ordinary dominoes are a set of different combinations of two tiles, each displaying `0` to `6` points. And this set is a similar combination of tiles, but the number of points on each can be from zero to a set value that depends on the intellectual level of the players. There are all kinds of tile combinations in this dice set, but none of them must be repeated (combinations such as `2 | 5` and `5 | 2` are considered the same).\
When making this set of dominoes, the manufacturer faced the problem of counting the total number of points on all dominoes. This is due to the fact that the dominoes are decorated with diamonds, which are dots on the tiles and the cost of which must be estimated during manufacture.

**Input data**:

The function receives a parameter n, which indicates the maximum number of points on one domino tile.


**Test values are 0 < n < 1000**

**Output data**:

Your function should return the optional number of diamond stones to be made for a given set of dice.

### Examples
For dominoes where the maximum possible number on the knuckle is 2, the possible knuckles will be as follows --> `0 | 1`, `0 | 2`, `1 | 1`, `1 | 2`, `2 | 2` therefore, the sum of all values on the knuckles will be `1 + 2 + 1 + 1 + 1 + 2 + 2 + 2 = 12`

```
2 --> 12
3 --> 30
20 --> 4620
```

## Idea

To solve the problem, as pieces are going to repeat themselves, we must observe two things.
1. Suppose the input is 3. Then we're going to sum 3 pieces with a zero, 3 pieces with a one, 2 pieces with a two and 1 piece with a three (to repetition in the sum). If the input is 4, then we're going to sum 4 pieces with a zero, 4 pieces with a one, 3 pieces with a two, 2 pieces with a three and 1 piece with a four. That means we can already predict the number of times the first number of the piece is going to be summed. This can be represented with the following formula: `number_of_times = first_number * (limit_number + 1 - first_number) `. The number 1 that appears it's because 0 and 1 appear the same amount of times.
2. When we're summing the second number on the piece we must keep in mind that we may have already summed it. Suppose the input is two as in the example given. We can see that when the first number is 1, we don't have to sum the `1 | 0` piece. And when the first number is 2, we don't have to sum the `2 | 0 ` and the `2 | 1 ` pieces. To solve this issue we can nest two cycles as you'll se in the code.

### Code
```
int dots_on_domino_bones(int number)
{
    int sum = 0;
    if (number < 0){
      return -1;
    } else {
      for (int i = 0; i < number + 1; i++){
        sum += i*(number + 1 - i);
        for (int j = i; j < number + 1; j++){
          sum += j;
        }
      }
      return sum;
    }     
}
```
