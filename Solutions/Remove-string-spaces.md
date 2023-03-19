#  Remove string spaces

This exercise was taken from [codewars](https://www.codewars.com/kata/57eae20f5500ad98e50002c5)

## Task

Write a function that removes the spaces from the string, then return the resultant string.

### Examples

```
Input -> Output
"8 j 8   mBliB8g  imjB8B8  jl  B" -> "8j8mBliB8gimjB8B8jlB"
"8 8 Bi fk8h B 8 BB8B B B  B888 c hl8 BhB fd" -> "88Bifk8hB8BB8BBBB888chl8BhBfd"
"8aaaaa dddd r     " -> "8aaaaaddddr"
```

## Idea

The idea to solve the problem will be going through every element of the string and analyzing which are blank spaces and which not. Those that aren't will be copied into another string called result.

### Code
```
#include <string>

using namespace std;

std::string no_space(const std::string& x)
{
  string result = "";
  for (int i = 0; i < x.size(); i++){
    if (x[i] != ' '){
      result.push_back(x[i]);
    }
  }
   return result;
}
```