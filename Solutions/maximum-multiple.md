# Maximum multiple

This exercise was taken from [Codewars](https://www.codewars.com/kata/5aba780a6a176b029800041c)

## Task
Given a **Divisor** and a **Bound**, find the largest integer N such that:
1. N is divisible by divisor
2. N is less than or equal to bound
3. N is greater than 0.

Note : the parameters (divisor, bound) passed to the function are only positive values. It's guaranteed that a divisor is found.

### Examples
```
maxMultiple (2,7) ==> return (6)
```
Explanation:
(6) is divisible by (2) , (6) is less than or equal to bound (7) , and (6) is > 0. 
```
maxMultiple (10,50)  ==> return (50)
```
Explanation:
(50) is divisible by (10) , (50) is less than or equal to bound (50) , and (50) is > 0.

```
maxMultiple (37,200) ==> return (185)
```
Explanation:
(185) is divisible by (37) , (185) is less than or equal to bound (200) , and (185) is > 0.


## Idea

This problem can be divided into two parts:
1. When the bound is the N we're looking for
2. When the bound is not the N we're looking for

This is way a simple if it's all we need to solve it. In case 1 then we shall return the bound. In case 2 we shall return the closest number to the bound that's divisible by the parameter. To find this number we got to ways:
1. Divide the bound by the divisor and with the function `floor()` obtain the integer part of the number. Having done this we simply got to multiply that integer by the divisor and we've found our n.
2. Calculate what's the result of bound % divisor (this operation is called module) and substract that value from the bound.

I used the first method since I'm trying to incorporate built in functions from c++ to my coding skills.

### Code
```
#include <math.h>
int maxMultiple(int divisor, int bound) 
{
  if (bound/divisor == 0){
    return bound;
  } else {
    return floor(bound/divisor)*divisor;
  }
}
```