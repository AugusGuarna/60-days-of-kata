# The mark of Zorro

This exercise was taken from [codewars](https://www.codewars.com/kata/63115a60e5da9e004aa3004f)

## Task

In this kata, you will need to develop an algorithm that returns all items from a matrix, just like when Zorro prints his "Z" mark. In this case, the function must be a template (for c++), which works regardless of the type of data contained in the array. All matrices will be square, and the empty ones should return an empty array. The output should use the same container type as either of the input types (std::vector for c++).

### Examples

```
std::vector<std::vector<char>> matrix {

{'a', 'b', 'c', 'e'},

{'f', 'g', 'h', 'i'},

{'j', 'k', 'l', 'm'},

{'n', 'o', 'p', 'q'}

};

should return {'a', 'b', 'c', 'e', 'h', 'k', 'n', 'o', 'p', 'q'}
---------------------------------------------------------------------
std::vector<std::vector<float>> matrix {

{1.5, 17.7, 9.345},

{0.1, 91.0, 14.81},

{9.9, -1.7, -9.13}

}; 

should return {1.5, 17.7, 9.345, 91.0, 9.9, -1.7, -9.13}
---------------------------------------------------------------------
std::vector<std::vector<std::string>> matrix {};

should return {}
```

## Idea

To solve the problem the idea will be covering the first line, the antidiagonal and the last line of the matrix with 3 different cycles.

### Code
```
#include <vector> 

template <typename T> std::vector<T> zorro(const std::vector<std::vector<T>> matrix) {
  std::vector<T> result = {};
  if (matrix.size() == 0){
    return result;
  } else { 
    for (int i = 0; i < matrix[0].size() - 1; i++){
      result.push_back(matrix[0][i]);
    }
    for (int j = 0; j < matrix.size(); j++){
      result.push_back(matrix[j][matrix[0].size() - 1 - j]);
    }
    for (int k = 1; k < matrix[0].size(); k++){
      result.push_back(matrix[matrix.size()-1][k]);
    }
    return result;
  }
}
```