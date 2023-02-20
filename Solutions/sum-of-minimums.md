# Sum of minimums
This exercise was taken from [codewars](https://www.codewars.com/kata/5d5ee4c35162d9001af7d699)
## Task
Given a 2D ( nested ) list ( array, vector, .. ) of size `m * n`, your task is to find the sum of the minimum values in each row.

### Examples

```
[ [ 1, 2, 3, 4, 5 ]        #  minimum value of row is 1
, [ 5, 6, 7, 8, 9 ]        #  minimum value of row is 5
, [ 20, 21, 34, 56, 100 ]  #  minimum value of row is 20
]
```
So the function should return `26` because the sum of the minimums is `1 + 5 + 20 = 26`.

Note: You will always be given a non-empty list containing positive values.

## Idea

To solve this problem we're going to go through every list inside the array and compare the different elements to find the minimun. Once we've compared every element inside the list we'll sum the value that we've stored as minimum into a different variable. We shall repeat the process until we've covered every list.

### Code
 ```
 #include <vector>
 
 using namespace std;
 
 int sum_of_minimums(const std::vector<std::vector<int>> &numbers)
 {
     int sum = 0;
     for (int i = 0; i < numbers.size(); i++){
       int min = numbers[i][0];
       for (int j = 0; j < numbers[0].size(); j++){
         if (numbers[i][j] < min){
           min = numbers[i][j];
         }
         if (j == numbers[0].size()-1){
           sum += min;
         }
       }
     }
     return sum;
 }
```
