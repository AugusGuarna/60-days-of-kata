# Adding big numbers
This exercise was taken from [codewars](https://www.codewars.com/kata/525f4206b73515bffb000b21)
## Task

We need to sum big numbers and we require your help.

Write a function that returns the sum of two numbers. The input numbers are strings and the function must return a string.

### Examples


```
add("123", "321"); -> "444"
add("11", "99");   -> "110"
```

### Notes

The input numbers are big\
The input is a string of only digits\
The numbers are positives

## Idea

To solve the problem we've gotta do the type of sum we did in primary school.As the code is pretty long and quite self explanatory I won't go into its details (in internet there are plenty of ways to solve this type of problems).


### Code
 ```
#include <iostream>
#include <string>
#include <sstream>
#include <math.h>

using namespace std;

std::string add(const std::string& a, const std::string& b) {
  string result = "";
  string str1;
  string str2;
  int carry = 0;
  int sum = 0;
  int n = 0;
  int diff = 0;
  if(a.size() < b.size()){
    n = a.size();
    diff = b.size() - a.size();
    str1 = b;
    str2 = a;
  } else{
    n = b.size();
    diff = a.size() - b.size();
    str1 = a;
    str2 = b;
  }
  for (int i = n - 1; i > -1; i--){
    sum = (str1[i+diff] -'0') + (str2[i] -'0') + carry;
    if (sum > 9){
      carry = 1;
      sum = sum%10;
    } else {
      carry = 0;
    }
    result.push_back(sum%10 +'0');
  }
  for (int j = diff - 1; j > -1; j--){
    if (carry > 0){
      sum = (str1 [j]-'0') + carry;
      if (sum > 9){
        carry = 1;
        sum = sum%10;
      } else {
        carry = 0;
      }
      result.push_back(sum + '0');
    } else {
      result.push_back(str1[j]);
    }
  }
  if (carry>0){
    result.push_back(carry +'0');
  }
  reverse(result.begin(), result.end());
  return result;
}
```