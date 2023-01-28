# Odd or even?
This exercise was taken from [codewars](https://www.codewars.com/kata/5949481f86420f59480000e7)
## Task
Given a list of integers, determine whether the sum of its elements is odd or even.
Give your answer as a string matching `"odd"` or `"even"`.
If the input array is empty consider it as: `[0]` (array with a zero).

### Examples

```
Input: [0]
Output: "even"

Input: [0, 1, 4]
Output: "odd"

Input: [0, -1, -5]
Output: "even"
```

## Idea
The solution to this exercise is pretty easy.
First of all, we've got to sum every element of the array (a for cycle). Then, once we had the total sum, we have to check if totalSum mod 2 == 0. In the case in which this is true, then the program should return "even". In the other case, "odd".

### Code
 ```
 #include <string>
 #include <vector>

 std::string odd_or_even(const std::vector<int> &arr)
 {
   int sum = 0;
   for (int i = 0; i < arr.size(); i++){
     sum = sum + arr[i];
   }
   if (sum % 2 == 0){
     return "even";
   } else {
     return "odd";
     }

 }
```
