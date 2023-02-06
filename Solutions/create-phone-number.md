# Create phone number

This exercise was taken from [Codewars](https://www.codewars.com/kata/525f50e3b73515a6db000b83)

## Task
Write a function that accepts an array of 10 integers (between 0 and 9), that returns a string of those numbers in the form of a phone number.

The returned format must be correct in order to complete this challenge.

Don't forget the space after the closing parentheses!

### Examples
```
createPhoneNumber(int[10]{1, 2, 3, 4, 5, 6, 7, 8, 9, 0}) // => returns "(123) 456-7890"
```

## Idea

Although there are multiple solutions (probably fancier than this one) to this problem (some of them include starting an string and then replacing the values with the help of a cycle and some ifs), I chose a straight forward approach.

### Code
```
#include <string>

using namespace std;
 
std::string createPhoneNumber(const int arr [10]){
  return "("+ to_string(arr[0]) + to_string(arr[1]) + to_string(arr[2]) + ") " + to_string(arr[3]) + to_string(arr[4]) + to_string(arr[5]) +"-"+ to_string(arr[6]) + to_string(arr[7]) + to_string(arr[8])+ to_string(arr[9]);
}
```
