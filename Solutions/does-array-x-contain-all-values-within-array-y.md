# Does array x contain all values within array y?
This exercise was taken from [codewars](https://www.codewars.com/kata/5143cc9694a24abcd2000001)
## Task
We want to extend the array class so that it provides a `contains_all?` method. This method will always assume that an array is passed in and will return `true` if all values in the passed in array are present within the current array.
### Examples

```
items = std::vector<int>{1, 2, 3, 4, 5, 6, 7, 8, 9}

contains_all(items, {1, 2, 3})  # should == true
contains_all(items, {1, 5, 13}) # should == false because 13 is not in the items array
```

## Idea

Even though this problem can be solved using two cycles, I decided to just use one. The basic idea will be staying in one element of target and check if that element is inside arr. If that element is inside arr then we'll sum 1 to result and pass to the next element of target and restart the process on arr. If that element's not there then we won't sum anything to result and restart everything.  

### Code
 ```
 #include <vector>

bool contains_all(const std::vector<int>& arr, const std::vector<int>& target) {
  int i = 0, j = 0, result = 0;
  while (i < arr.size() && j < target.size()){
    if (arr[i] == target[j]){
      result++;
      j++;
      i = 0;
    } else if (i == arr.size() - 1){
      i = 0;
      j++;
    } else {
      i++;
    } 
  }
  return result == target.size();
}
```