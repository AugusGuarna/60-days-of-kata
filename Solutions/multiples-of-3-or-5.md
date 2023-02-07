# Multiples of 3 or 5

This exercise was taken from [Codewars](https://www.codewars.com/kata/514b92a657cdc65150000006)

## Task

If we list all the natural numbers below 10 that are multiples of 3 or 5, we get 3, 5, 6 and 9. The sum of these multiples is 23.

Finish the solution so that it returns the sum of all the multiples of 3 or 5 below the number passed in. Additionally, if the number is negative, return 0 (for languages that do have them).

Note: If the number is a multiple of both 3 and 5, only count it once.

## Idea

This is a problem I reckon to be quite easy but the tricky part kicks in when we reach the case where you have a multiple of 3 that's multiple of 5 at the same time. To sort this obstacle you might think of 3 ifs:
1. if (i % 5 == 0 && i % 3 == 0) 
2. if (i % 5 == 0)
3. if (i % 3 == 0)

Or at least, that's how I first though about it. There's nothing wrong with this but it's not that classy and you can simplify the expression using the logical or (which means or p or q or both).

### Code
```
int solution(int number) 
{
  int result = 0;
  if (number < 0){
    return result;
  } else {
    int i = 0;
    while (i < number){
      if (i % 5 == 0 || i % 3 == 0){
        result += i;
        i++;
      } else {
        i++;
      }
    }
    return result;
  }
}
```
