# Sequence sum

This exercise was taken from [Codewars](https://www.codewars.com/kata/586f6741c66d18c22800010a)

## Task
Your task is to make function, which returns the sum of a sequence of integers.

The sequence is defined by 3 non-negative values: **begin, end, step (inclusive)**.

If **begin** value is **greater** than the **end**, function should returns **0**.



### Examples
```
2,2,2 --> 2
2,6,2 --> 12 (2 + 4 + 6)
1,5,1 --> 15 (1 + 2 + 3 + 4 + 5)
1,5,3  --> 5 (1 + 4)
```

## Idea
Although it may seem like a tricky problem, if we read closely the instructions we'll realize that the code should be formed by 3 ifs. The first should check if begin is greater than end. The second should check if begin and end are the same. The third, in reality it's not an if but the else clause of the other two. This else clause represents what happens if begin is not greater nor equal. This clause will be the most important one. Inside of it we'll include a while cycle that will be in charge of
the sum of all the correct values. To accomplish this, I created two variables ( I thought I would be the easiest way to comprehend it): accum and sum.\
Accum will store the values that we sould be summing while sum will store the summatory.Accum will start as begin + step so it's the first value after begin that we should sum. Inside the while will add more times the value step to form the others.
Sum it's pretty self explanatory. The while guard won't allow us to sum something greater than the end value.

### Code
```
int sequenceSum(int start, int end, int step)
{
  int accum = start + step;
  int sum = start;
  if (start > end){
    return 0;
  } else if (start == end){
    return sum;
  } else {
    while (accum <= end ){
      sum += accum;
      accum += step;

    }
    return sum;
  }
}
```
