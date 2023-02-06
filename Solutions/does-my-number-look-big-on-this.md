# Does my number look big in this?

This exercise was taken from [Codewars](https://www.codewars.com/kata/5287e858c6b5a9678200083c)

## Task

A [Narcissistic Number](https://en.wikipedia.org/wiki/Narcissistic_number) (or Armstrong Number) is a positive number which is the sum of its own digits, each raised to the power of the number of digits in a given base. In this Kata, we will restrict ourselves to decimal (base 10).

For example, take 153 (3 digits), which is narcissistic:

    1^3 + 5^3 + 3^3 = 1 + 125 + 27 = 153
and 1652 (4 digits), which isn't:

    1^4 + 6^4 + 5^4 + 2^4 = 1 + 1296 + 625 + 16 = 1938
The Challenge:

Your code must return **true** or **false** (not 'true' and 'false') depending upon whether the given number is a Narcissistic number in base 10. This may be True and False in your language, e.g. PHP.\
Error checking for text strings or other invalid inputs is not required, only valid positive non-zero integers will be passed into the function.

## Idea

The strategy to solve this problem will be:
1. Count the digits of the input value
2. Divide the input value into its own digits and then raise this digits to the count we've done
3. See if the sum of the digits of the 2nd step equals the number

For the 1st step we can do a simple for cycle that with each iteration divides the number by ten until the number is zero. Every time it iterates the digits counter will increment in 1. Although this is just one of the many possibilities we've got to solve this, I will mention a pretty clever way I found online which consists of doing:
`log10 (value) + 1`. If you don't get it, think about it for a minute and you'll see why it works.\
For the 2nd step we'll do another cycle with the same structure as the one in the previous step but inside it we're going to calculate the remainder of dividing the input value (and then its variations) by ten in order to isolate the digits one by one. Then we'll raise this values to the digits counted and save them inside a variable while we sum them.\
For the 3rd step a simple if will solve the rest of the problem. Inside the if we're going to compare if the input value is equal to the sum we did in step number 2.

### Code
```
#include <math.h>

bool narcissistic( int value ){
  int digits = 0;
  int n = 0;
  int remainder = 0;
  for ( int i = value; i != 0; i = i/10){
    digits++;
  }
  for ( int j = value; j != 0 ; j = j/10){
    remainder = j % 10;
    n += pow(remainder, digits);
  }
  if (n == value){
    return true;
  } else {
    return false;
  }
}
```
