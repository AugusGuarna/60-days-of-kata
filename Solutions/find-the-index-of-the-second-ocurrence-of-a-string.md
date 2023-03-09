# Find the index of the second occurence of a letter in a string
This exercise was taken from [codewars](https://www.codewars.com/kata/63f96036b15a210058300ca9)

## Task

In this kata, you need to write a function that takes a string and a letter as input and then returns the index of the second occurrence of that letter in the string. If there is no such letter in the string, then the function should return -1. If the letter occurs only once in the string, then -1 should also be returned.

### Examples

```
secondSymbol('Hello world!!!','l') --> 3
secondSymbol('Hello world!!!', 'A') --> -1
```

## Idea

To solve the exercise we're going to go through the string and once we find the second ocurrence (if it exists) we're going to stop and return that index value.

### Code

```
#include <string>

int secondSymbol(const std::string& str, char symbol) {
  int app = 0, i = 0;
  while(i < str.size() && app < 2){
    if (str[i] == symbol){
      app++;
    }
    i++;
  }
  if (app == 2){
    return i-1;
  } else {
    return -1;
  }
}
```

