# Find the parity outlier

This exercise was taken from [Codewars](https://www.codewars.com/kata/5526fc09a1bbd946250002dc)

## Task
You are given an array (which will have a length of at least 3, but could be very large) containing integers. The array is either entirely comprised of odd integers or entirely comprised of even integers except for a single integer `N`. Write a method that takes the array as an argument and returns this "outlier" `N`.
### Examples
```
[2, 4, 0, 100, 4, 11, 2602, 36]
Should return: 11 (the only odd number)

[160, 3, 1719, 19, 11, 13, -21]
Should return: 160 (the only even number)
```

## Idea
Although I solved this problem multiple times and tried different approaches, the one exposed here is the one that I found more elegant and simple.\
Basically, the program counts the even and the odd numbers of the array and save the last value of each. By doing this, once every value has been counted we just need to compare the number of even and the number of odds. If even > odds, then there's just one odd and we got to return the odd value saved. If odds > even, then we got to return the even value saved. 

### Code
```
using namespace std;

int FindOutlier(std::vector<int> arr)
{
    int resultEven = 0;
    int resultOdd = 0;
    int i = 0;
    int even = 0;
    int odd = 0;
    while (i < arr.size()){
      if (arr[i] % 2 == 0){
        even++;
        resultEven = arr[i];  
        i++;
      } else {
        odd++;
        resultOdd = arr[i];
        i++;
      }
    }
    if (even > odd){
      return resultOdd;
    } else {
      return resultEven;
    }
}
```
