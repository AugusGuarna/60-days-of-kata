# Convert string to camel case

This exercise was taken from [codewars](https://www.codewars.com/kata/517abf86da9663f1d2000003)

## Task
Complete the method/function so that it converts dash/underscore delimited words into [camel casing](https://en.wikipedia.org/wiki/Camel_case). The first word within the output should be capitalized only if the original word was capitalized (known as Upper Camel Case, also often referred to as Pascal case). The next words should be always capitalized.

### Examples

`"the-stealth-warrior"` gets converted to `"theStealthWarrior"`

`"The_Stealth_Warrior"` gets converted to `"TheStealthWarrior"`

`"The_Stealth-Warrior"` gets converted to `"TheStealthWarrior"`

## Idea

To solve the problem the idea will be identifying those positions where an underscore can be spotted and copy the following position to our result.

### Code
```
#include <string>

using namespace std;

std::string to_camel_case(std::string text) {
  string result{""};
  int i{0};
  while (i < text.size()){
    if (text[i] == '_' || text[i] == '-'){
      result.push_back(toupper(text[i+1]));
      i = i+2;
    } else {
      result.push_back(text[i]);
      i++;
    }
  }
  return result;
}

```
