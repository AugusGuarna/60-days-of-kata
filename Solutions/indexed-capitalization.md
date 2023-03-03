# Indexed capitalization
This exercise was taken from [codewars](https://www.codewars.com/kata/59cfc09a86a6fdf6df0000f1)

## Task

Given a string and an array of integers representing indices, capitalize all letters at the given indices.\
The input will be a lowercase string with no spaces and an array of digits.

### Example

```
capitalize("abcdef",[1,2,5]) = "aBCdeF"
capitalize("abcdef",[1,2,5,100]) = "aBCdeF". There is no index 100.
```

## Idea

The idea is pretty simple, if the digit of the array is within the range of s then capitalize the char that's in that position.

### Code

```
using namespace std;

std::string capitalize(std::string s, std::vector<int> idxs)
{
  for (int i = 0; i < idxs.size(); i++){
    if(idxs[i] < s.size()){
      s[idxs[i]] = toupper(s[idxs[i]]);
    }
  }
  return s;
}
```

