# Square(n) sum
This exercise was taken from [codewars](https://www.codewars.com/kata/515e271a311df0350d00000f)
## Task

Complete the square sum function so that it squares each number passed into it and then sums the results together.

### Examples

```
[1, 2, 2] it should return 9 because 1^2 + 2^2 + 2^2 = 9
```

## Idea

The idea will be squaring and summing every element of the array.

### Code
```
#include <vector>
#include <cmath>
int square_sum(const std::vector<int>& numbers)
{
    int result = 0;
    for (int i = 0; i < numbers.size(); i++){
      result += pow(numbers[i], 2);
    }
    return result;
}
```
