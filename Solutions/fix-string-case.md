# Fix string case
This exercise was taken from [codewars](https://www.codewars.com/kata/5b180e9fedaa564a7000009a)

## Task

In this Kata, you will be given a string that may have mixed uppercase and lowercase letters and your task is to convert that string to either lowercase only or uppercase only based on:

1. make as few changes as possible.
2. if the string contains equal number of uppercase and lowercase letters, convert the string to lowercase.

### Example

```
solve("coDe") = "code". Lowercase characters > uppercase. Change only the "D" to lowercase.
solve("CODe") = "CODE". Uppercase characters > lowecase. Change only the "e" to uppercase.
solve("coDE") = "code". Upper == lowercase. Change all to lowercase.
```

## Idea

To solve this problem we're going to count how many uppercase and lowercase characters we've got. Then, a simple if is enough to solve the problem.  

### Code

```
#include <string>

std::string solve(const std::string& str){
  int mayus = 0;
  int minus = 0;
  std::string result = "";
  for (int i = 0; i < str.size(); i++){
    if (isupper(str[i])){
      mayus++;
    }
  }
  minus = str.size() - mayus;
  if (mayus > minus){
    for (int j = 0; j < str.size(); j++){
      if(islower(str[j])){
        result.push_back(toupper(str[j]));
      } else {
        result.push_back(str[j]);
      }
    }
  } else {
    for (int l = 0; l < str.size(); l++){
      if(isupper(str[l])){
        result.push_back(tolower(str[l]));
      } else {
        result.push_back(str[l]);
      }
    }
  }
  return result;
}
```

