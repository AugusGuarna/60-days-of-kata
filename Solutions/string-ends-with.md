# Strings end with?

This exercise was taken from [codewars](https://www.codewars.com/kata/51f2d1cafc9c0f745c00037d)

## Task

Complete the solution so that it returns true if the first argument(string) passed in ends with the 2nd argument (also a string).

### Example

```
solution('abc', 'bc') // returns true
solution('abc', 'd') // returns false
```


## Idea

The idea will be comparing the end of the bigger string with the characters of the ending string. Having this in mind we're gonna count the matches. If the matches equal the size of the ending string then we shall return true.

### Code
````
#include <string>
bool solution(std::string const &str, std::string const &ending) {
  int count = 0;
  for (int i = 0; i < ending.size(); i++){
    if (str[str.size()-1-i] == ending[ending.size()-1-i]){
      count++;
    }
  }  
  return count == ending.size();
}
````