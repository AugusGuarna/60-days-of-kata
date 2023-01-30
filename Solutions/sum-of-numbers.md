# Sequence sum

This exercise was taken from [Codewars](https://www.codewars.com/kata/55f2b110f61eb01779000053)

## Task
Given two integers `a` and `b`, which can be positive or negative, find the sum of all the integers between and including them and return it. If the two numbers are equal return `a` or `b`.

Note: `a` and `b` are not ordered!
### Examples
```
(1, 0) --> 1 (1 + 0 = 1)
(1, 2) --> 3 (1 + 2 = 3)
(0, 1) --> 1 (0 + 1 = 1)
(1, 1) --> 1 (1 since both are same)
(-1, 0) --> -1 (-1 + 0 = -1)
(-1, 2) --> 2 (-1 + 0 + 1 + 2 = 2)
```

## Idea
Although I solved this way (which I'll explain), I've seen an interest solution that never crossed my mind and that I wanted to mention: using the formula of the Gauss sum.\n The first thing I did was initializing a sum variable and creating an if which checks if a == b to return of one or another as the problems says it should happen in that case. Then I divided two cases: when a<b and when a>b. I'll explain the first one because the second one it's exactly the same.\n As we want to sum all the values between a and b including both, I assigned sum with the a value and created a for. Inside the for I initialized i in a+1 and stated that the guard will be i <= b so that with each iteration i is one of the different numbers between a and b (included). Finally, inside the body of the for it adds i to sum.

### Code
```
int get_sum(int a, int b)
{
  int sum = 0;
  if (a == b){
    return a;
  } else if (a<b){
    sum = a;
    for (int i = a + 1 ; i <= b ; i++ ){
      sum += i;
    }
  } else {
    sum = b;
    for (int j = b + 1 ; j <= a ; j++ ){
      sum += j;
    }
  }
  return sum;
}
```
