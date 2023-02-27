# Calculate the number of inversions in an array
This exercise was taken from [codewars](https://www.codewars.com/kata/537529f42993de0e0b00181f)
## Task

Array inversion indicates how far the array is from being sorted.

Inversions are pairs of elements in array that are out of order.

### Examples

```
[1, 2, 3, 4]  =>  0 inversions
[1, 3, 2, 4]  =>  1 inversion: 2 and 3
[4, 1, 2, 3]  =>  3 inversions: 4 and 1, 4 and 2, 4 and 3
[4, 3, 2, 1]  =>  6 inversions: 4 and 3, 4 and 2, 4 and 1, 3 and 2, 3 and 1, 2 and 1
```

## Idea

To solve this problem we can basically implement a insertion sort and count every move that's necessary to order the vector.

### Code
 ```
#include <vector>

using namespace std;

class Kata {
  public:
    int countInversions(const std::vector<int>& vec) {
      int count = 0;
      vector<int> s = vec;
      for (int i = 0; i < s.size(); i++){
        for(int j = i; j > 0 && s[j]<s[j-1];j--){
          int a = s[j];
          s[j] = s[j-1];
          s[j-1] = a;
          count++;
        }
      }
      return count;
    }
};
```