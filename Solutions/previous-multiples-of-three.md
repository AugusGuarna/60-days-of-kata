# Previous multiples of three

This exercise was taken from [codewars](https://www.codewars.com/kata/61123a6f2446320021db987d)

## Task

Given a positive integer n: `0 < n < 1e6`, remove the last digit until you're left with a number that is a multiple of three.

Return `n` if the input is already a multiple of three, and if no such number exists, return `null`, a similar empty value, or `-1`.

### Examples

```
1      => null
25     => null
36     => 36
1244   => 12
952406 => 9
```

## Idea

To solve the problem we're going to divide the number by 10 until we reach a multiple of 3.

### Code
```
int prev_mult_of_three (int n) {
  while (n % 3 != 0 && n > 0){
    n = n / 10;
  }
  if (n != 0){
    return n;
  } else {
    return -1;
  }
  
}
```