# Triming a string

This exercise was taken from [codewars](https://www.codewars.com/kata/563fb342f47611dae800003c)

## Task

Create a function that will trim a string (the first argument given) if it is longer than the requested maximum string length (the second argument given). The result should also end with "..."

These dots at the end also add to the string length.

For example, `trim("Creating kata is fun", 14)` should return `"Creating ka..."`

If the string is smaller or equal than the maximum string length, then simply return the string with no trimming or dots required.

e.g. `trim("Code Wars is pretty rad", 50)` should return `"Code Wars is pretty rad"`

If the requested string length is smaller than or equal to 3 characters, then the length of the dots is not added to the string length.

e.g. `trim("He", 1)` should return `"H..."`, because 1 <= 3

Requested maximum length will be greater than 0. Input string will not be empty.

## Idea

To solve this problem we got to solve 3 different cases
1. When the size is bigger than the input string size. In this case we should return the string without any alterations
2. When size is bigger than 3. In this case we have to add to the substring that goes from 0 to size-3 the following chars "..."
3. When size is 3 or less. In this case we have to add to the substring that goes from 0 to size the following chars "..."

### Code

```
#include <string>

using namespace std;

std::string trim(const std::string& phrase, size_t size) {
  string result = phrase;
  if (size >= phrase.size()){
    return result;  
  } else {
      if (size > 3){
        result = result.substr(0, size-3) + "...";
        return result;
      } else {
        result = result.substr(0,size) + "...";
        return result;  
      }
  }
}
```