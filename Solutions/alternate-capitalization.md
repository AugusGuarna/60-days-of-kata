# Alternate capitalization
This exercise was taken from [codewars](https://www.codewars.com/kata/59cfc000aeb2844d16000075)

## Task
Given a string, capitalize the letters that occupy even indexes and odd indexes separately, and return as shown below. Index `0` will be considered even.

For example, `capitalize("abcdef") = ['AbCdEf', 'aBcDeF']`. See test cases for more examples.

The input will be a lowercase string with no spaces.

## Idea

To solve this problem we're going to use one cycle. Depending if it's an odd or even position we'll capitalize different chars. 

### Code

```
#include <string>
#include <utility>

using namespace std;

std::pair<std::string, std::string> capitalize(const std::string &s)
{
    string a = s;
    string b = s;
    pair<string, string> result = {"",""};
    for (int i = 0; i < s.size(); i++){
      if (i % 2 == 0){
        a[i] = toupper(a[i]);
      } else {
        b[i] = toupper(b[i]);
      }
    }
    result.first = a;
    result.second = b;
    return result;
}
```

