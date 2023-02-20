# Roman numerals decoder
This exercise was taken from [codewars](https://www.codewars.com/kata/51b6249c4612257ac0000005)
## Task
Create a function that takes a Roman numeral as its argument and returns its value as a numeric decimal integer. You don't need to validate the form of the Roman numeral.

[Modern Roman numerals](https://en.wikipedia.org/wiki/Roman_numerals#Standard_form) are written by expressing each decimal digit of the number to be encoded separately, starting with the leftmost digit and skipping any 0s. So 1990 is rendered "MCMXC" (1000 = M, 900 = CM, 90 = XC) and 2008 is rendered "MMVIII" (2000 = MM, 8 = VIII). The Roman numeral for 1666, "MDCLXVI", uses each letter in descending order.

### Examples

```
solution("XXI"); // => 21
```

Help:
```
Symbol    Value
I          1
V          5
X          10
L          50
C          100
D          500
M          1,000
```
## Idea

To solve the problem we've gotta pay attention to those cases in which we've got a small number before a big number (cases such as IX or IV). Once we've sorted this difficulty the solution is pretty straightforward.

### Code
 ```
 #include <iostream>
 #include <string>
 
 using namespace std;
 
 string order = "IVXLCDM";
 
 int solution(string roman) {
   int result = 0;
   for (int i = 0; i < roman.size(); i++){
     if (i != roman.size() - 1){
       if (order.find(roman[i]) < order.find (roman[i+1])){
         if (roman[i] == 'C'){
           result -= 100;
         } else if (roman[i] == 'L'){
           result -= 50;
         } else if (roman[i] == 'X'){
           result -= 10;
         } else if (roman[i] == 'V'){
           result -= 5;
         } else if (roman[i] == 'I'){
           result -= 1;
         }
       } else {
         if (roman[i] == 'M'){
          result += 1000; 
         } else if (roman[i] == 'D'){
           result += 500;
         } else if (roman[i] == 'C'){
           result += 100;
         } else if (roman[i] == 'L'){
           result += 50;
         } else if (roman[i] == 'X'){
           result += 10;
         } else if (roman[i] == 'V'){
           result += 5;
         } else if (roman[i] == 'I'){
           result += 1;
         }
       }
     } else {
       if (roman[i] == 'M'){
        result += 1000; 
       } else if (roman[i] == 'D'){
         result += 500;
       } else if (roman[i] == 'C'){
         result += 100;
       } else if (roman[i] == 'L'){
         result += 50;
       } else if (roman[i] == 'X'){
         result += 10;
       } else if (roman[i] == 'V'){
         result += 5;
       } else if (roman[i] == 'I'){
         result += 1;
       }
     }
   }
   return result;
 }
```
