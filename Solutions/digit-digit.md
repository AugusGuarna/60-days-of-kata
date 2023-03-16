# Digit * Digit

This exercise was taken from [codewars](https://www.codewars.com/kata/546e2562b03326a88e000020)

## Task

Welcome. In this kata, you are asked to square every digit of a number and concatenate them.

For example, if we run 9119 through the function, 811181 will come out, because 92 is 81 and 12 is 1. (81-1-1-81)

Example #2: An input of 765 will/should return 493625 because 72 is 49, 62 is 36, and 52 is 25. (49-36-25)

**Note**: The function accepts an integer and returns an integer.

## Idea

To solve the problem the idea will be taking the remainder of dividing the number by 10 and square it. Then we'll sum that result to an int variable and for the next number we'll do the same but multiplying it by 10^j with j being the number of digits the variable already has.

### Code
```
include <cmath>

using namespace std;

int square_digits(int num) {
  int result = 0;
  int j = 0;
  for(int i = num; i != 0; i = i/10){
    int n = pow(i % 10, 2);
    if (n / 10 != 0){
      result += n * pow (10, j);
      j = j + 2;
    } else {
      result += n * pow (10, j);
      j++;
    }
  }
  return result;
}
```