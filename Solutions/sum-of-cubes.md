# Sum of cubes
This exercise was taken from [codewars](https://www.codewars.com/kata/59a8570b570190d313000037)
## Task
Write a function that takes a positive integer n, sums all the cubed values from 1 to n (inclusive), and returns that sum.

Assume that the input n will always be a positive integer.
### Examples

```
2 --> 9 (sum of the cubes of 1 and 2 is 1 + 8)
3 --> 36 (sum of the cubes of 1, 2, and 3 is 1 + 8 + 27)
```

## Idea
I think no explanation is needed.

### Code
 ```
 #include <iostream>
#include <cmath>

using namespace std;

unsigned int sum_cubes(unsigned int n) {
  int sum = 0;
  for (int i = 0; i < n + 1 ; i++){
    sum += pow(i, 3);
  }
  return sum;
}
```
