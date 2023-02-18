# Hamming distance 
This exercise was taken from [codewars](https://www.codewars.com/kata/5410c0e6a0e736cf5b000e69)
## Task
The [Hamming Distance](https://en.wikipedia.org/wiki/Hamming_distance) is a measure of similarity between two strings of equal length. Complete the function so that it returns the number of positions where the input strings do not match.

### Examples

```
a = "I like turtles"
b = "I like turkeys"
Result: 3

a = "Hello World"
b = "Hello World"
Result: 0

a = "espresso"
b = "Expresso"
Result: 2
```

## Idea
As both strings share the same lenght we can use the same for to compare the characters between both.

### Code
 ```
 #include <string>

unsigned hamming(const std::string &a, const std::string &b)
{
    int result = 0;
    for (int i = 0; i < a.size(); i++){
       if (a[i] != b[i]){
        result++;
      }
     }  
    return result;
}
```
