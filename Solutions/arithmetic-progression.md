# Arithmetic progession
This exercise was taken from [codewars](https://www.codewars.com/kata/55caf1fd8063ddfa8e000018)

## Task

In your class, you have started lessons about [arithmetic progression](). Since you are also a programmer, you have decided to write a function that will return the first `n` elements of the sequence with the given common difference `d` and first element `a`. Note that the difference may be zero!

The result should be a string of numbers, separated by comma and space.


### Example

```
# first element: 1, difference: 2, how many: 5
arithmetic_sequence_elements(1, 2, 5) == "1, 3, 5, 7, 9"
```

## Idea

To solve the problem we're going to store the different values of the sum inside an int variable which then we'll transform into a string that'll be appended on the result string.

### Code

```
#include <string>

using namespace std;

std::string arithmeticSequenceElements(int a, int d, int n)
{
  string result = "";
  int aP = a; //aP = arithmeticProgression
  for (int i = 0; i < n; i++){
    string r = "";
    if (i != n - 1){
      r = to_string(aP) + ", ";
      result.append(r);
      aP += d;
    } else {
      r = to_string (aP);
      result.append(r);
    }
  }
  return result;
}
```

