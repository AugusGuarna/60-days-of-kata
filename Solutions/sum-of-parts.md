# Sum of parts

This exercise was taken from [Codewars](https://www.codewars.com/kata/5ce399e0047a45001c853c2b)

## Task

Let us consider this example (array written in general format):

`ls = [0, 1, 3, 6, 10]`

Its following parts:
```
ls = [0, 1, 3, 6, 10]
ls = [1, 3, 6, 10]
ls = [3, 6, 10]
ls = [6, 10]
ls = [10]
ls = []
```

The corresponding sums are (put together in a list): `[20, 20, 19, 16, 10, 0]` 

The function `parts_sums` (or its variants in other languages) will take as parameter a list ls and return a list of the sums of its parts as defined above.

### Examples
```
ls = [1, 2, 3, 4, 5, 6] 
parts_sums(ls) -> [21, 20, 18, 15, 11, 6, 0]

ls = [744125, 935, 407, 454, 430, 90, 144, 6710213, 889, 810, 2579358]
parts_sums(ls) -> [10037855, 9293730, 9292795, 9292388, 9291934, 9291504, 9291414, 9291270, 2581057, 2580168, 2579358, 0]
```

## Idea

I consider this problem to be a quite interesting one. It may not be **that** difficult but in order to solve it we got to read carefully the task.\
The idea will be divide the solution into two different cycles:
1. The first one will sum all of the values of the input vector
2. The second one will place the correct values inside the output vector

So, for the first one a simple for cycle in charge of the sum will be enough.\
For the second one, as the values should be in a sort of "descending order" we'll place the value of the sum in the 0 position but then for the 1 position we're going to place the value of the sum minus the value on the 0 position of the input vector. We're going to do this with all the different positions.\
However, if we'have chosen that the output and input vector share the same length, we'll be missing the last value, which should be zero. To solve this issue we got to change the output length to the input.size() + 1 (if we do every sum we'll have ls.size()+1 values).\
But now, you may be arguing that by doing this we'll have an indeterminaton because the ls[ls.size()] it's not in scope and, in fact, that's true. How can we avoid this scenario? By initializating the output vector wirh zeros in every position. This way we avoid the indetermination and we respect the fact that the last value ought to be zero.
### Code
```
#include<vector>

using namespace std;

std::vector<unsigned long long> partsSum(const std::vector<unsigned long long>& ls){
  vector<unsigned long long> result (ls.size() + 1,0);
  unsigned long long sum = 0;
  for (int i = 0; i < ls.size(); i++){
    sum += ls [i];
  }
  for (int j = 0; j < ls.size(); j++){
    result [j] = sum;
    sum -= ls[j];
  }
  return result;
}
```
