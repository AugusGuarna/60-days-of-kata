# Looking for a benefactor
This exercise was taken from [codewars](https://www.codewars.com/kata/569b5cec755dd3534d00000f)

## Task
The accounts of the "Fat to Fit Club (FFC)" association are supervised by John as a volunteered accountant. The association is funded through financial donations from generous benefactors. John has a list of the first `n` donations: `[14, 30, 5, 7, 9, 11, 15]`\
He wants to know how much the next benefactor should give to the association so that the average of the first `n + 1` donations should reach an average of `30`. After doing the math he found `149`. He thinks that he could have made a mistake.\
if dons = `[14, 30, 5, 7, 9, 11, 15]` then `new_avg(dons, 30)` --> `149`

Could you help him?\

The function `new_avg(arr, navg)` should return the expected donation **(rounded up to the next integer)** that will permit to reach the average navg.

Should the last donation be a non positive number `(<= 0)` John wants us:

To return:

1. Nothing in Haskell, Elm
2. None in F#, Ocaml, Rust, Scala
3. -1 in C, D, Fortran, Nim, PowerShell, Go, Pascal, Prolog, Lua, Perl, Erlang
4. or to throw an error (some examples for such a case):
   5. IllegalArgumentException() in Clojure, Java
   6. ArgumentException() in C# 
   7. echo ERROR in Shell
   8. argument-error in Racket
   9. std::invalid_argument in C++
   10. ValueError in Python
    
So, he will clearly see that his expectations are not great enough. In "Sample Tests" you can see what to return.

### Notes
1. all donations and navg are numbers (integers or floats), arr can be empty.
2. See examples below and "Sample Tests" to see which return is to be done.
```
new_avg([14, 30, 5, 7, 9, 11, 15], 92) should return 645
new_avg([14, 30, 5, 7, 9, 11, 15], 2) 
should raise an error (ValueError or invalid_argument or argument-error or DomainError or ... ) 
or return `-1` or ERROR or Nothing or None depending on the language.
```
## Idea

To solve the problem I highly recommend writing it as a math problem and try to solve for the value of x. Once you've done this the solution will come easily but note that you have to round the result ;) . 

### Code

 ```
#include <vector>
#include <cmath>
class NewAverage
{
public:
   static long long newAvg(std::vector<double> &arr, double navg){
     double result = navg * (arr.size() + 1);
     for (int i = arr.size()-1; i > -1 ; i--){
       result -= arr[i];
     }
     if (result <= 0){
       throw std::logic_error("std::logic_error");
     }
     return ceil(result);
   }
};
```

