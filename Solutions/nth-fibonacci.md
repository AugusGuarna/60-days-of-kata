# N-th Fibonacci
This exercise was taken from [codewars](https://www.codewars.com/kata/522551eee9abb932420004a0)
## Task
I love Fibonacci numbers in general, but I must admit I love some more than others.

I would like for you to write me a function that, when given a number `n` (`n >= 1`), returns the nth number in the Fibonacci Sequence
### Examples

```
 nthFibo(4) == 2
```
Because 2 is the 4th number in the Fibonacci Sequence.

For reference, the first two numbers in the Fibonacci sequence are `0` and `1`, and each subsequent number is the sum of the previous two.


## Idea
To solve this exercise we're going to implement a function that's based on the formula used to calculate Fibonacci's numbers: F(n) = F(n-2) + F(n-1).
Even though F(0) = 0 and F(1) = 1, this kata considers that F(1) = 0 and F(2) = 1.

### Code
 ```
 int nthFibo(int n) { 
  int a = 0;
  int b = 1;
  int result = 0;
  if (n == 1){
    return a;
  } else if (n == 2){
    return b;
  } else {
    for (int i = 2; i < n; i++){
      result = a + b;
      a = b;
      b = result;
    }
    return result;
  }
}
```
