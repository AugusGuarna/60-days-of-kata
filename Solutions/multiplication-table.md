# Multiplication table
This exercise was taken from [codewars](https://www.codewars.com/kata/534d2f5b5371ecf8d2000a08)
## Task

Your task, is to create N×N multiplication table, of size provided in parameter.

### Examples

For example, when given `size` is 3:

```
1 2 3
2 4 6
3 6 9
```

For the given example, the return value should be:\

`[[1,2,3],[2,4,6],[3,6,9]]`


## Idea

The idea will be the following: start a NxN matrix and then fill each place with the result of multiplying the correspondent line with the correspondent column. As vectors start by 0, we ought to sum 1 to the line and the column.

### Code
 ```
#include <vector>

using namespace std;
vector<vector<int>> multiplication_table(int n){
  vector<vector<int>> table(n,vector<int> (n));
  for (int i = 0; i < table.size(); i++){
    for (int j = 0; j < table[0].size(); j++){
      table[i][j] = (i + 1)*(j + 1);
    }
  }
  return table;
}
```