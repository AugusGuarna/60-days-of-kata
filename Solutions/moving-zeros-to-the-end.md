# Moving zeros to the end

This exercise was taken from [Codewars](https://www.codewars.com/kata/52597aa56021e91c93000cb0)

## Task
Write an algorithm that takes an array and moves all of the zeros to the end, preserving the order of the other elements.

### Examples
```
move_zeros({1, 0, 1, 2, 0, 1, 3}) // returns {1, 1, 2, 1, 3, 0, 0}
```
## Idea

The idea is quite basic, we're going to create a vector with the same size as the input one but filled with zeros. Then we'll check which elements of the input vector are different from zero and copy them into the new vector (in order ofc). This way once we've finished copying we'll have all the zeros at the end. 

### Code
```
#include <vector>
using namespace std;

std::vector<int> move_zeroes(const std::vector<int>& input) {
  vector <int> result (input.size(), 0);
  int i = 0;
  int j = 0;
  while (i < input.size()){
    if(input[i] != 0){
      result[j] = input [i];
      j++;
    }
    i++;
  }
  return result;
}
```
