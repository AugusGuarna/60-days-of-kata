# ROT-13
This exercise was taken from [codewars](https://www.codewars.com/kata/530e15517bc88ac656000716)
## Task
ROT13 is a simple letter substitution cipher that replaces a letter with the letter 13 letters after it in the alphabet. ROT13 is an example of the Caesar cipher.

Create a function that takes a string and returns the string ciphered with Rot13. If there are numbers or special characters included in the string, they should be returned as they are. Only letters from the latin/english alphabet should be shifted, like in the original Rot13 "implementation".

## Idea

To solve this kata we'll create two different strings: one will contain the whole alphabet in uppercase and the other in lowercase.
This way we can cypher messages that contain both upper and lowercase characters.\
This is a method to figure the position of char inside the alphabet so we can exchange it with the correct one.

### Code
 ```
#include <string>
#include <cctype>

using namespace std;

string rot13(string msg)
{
  string MINUS = "abcdefghijklmnopqrstuvwxyz";
  string MAYUS = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
  for (int i = 0 ; i < msg.size() ; i++){
    if (isupper(msg[i])){
      int j = 0;
      while (j < MAYUS.size() && MAYUS[j] != msg[i]){
        j++;
      }
      msg [i] = MAYUS [(j+13)%26];
    } else if (islower(msg[i])) {
      int h = 0;
      while (h < MINUS.size() && MINUS[h] != msg[i]){
        h++;
      }
      msg [i] = MINUS [(h+13)%26];
    } else { 
    }
  }
  return msg;
}
```
