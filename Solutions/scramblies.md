# Scramblies

This exercise was taken from [Codewars](https://www.codewars.com/kata/55c04b4cc56a697bb0000048)

## Task
Complete the function `scramble(str1, str2)` that returns `true` if a portion of `str1` characters can be rearranged to match `str2`, otherwise returns `false`.

Notes:

1. Only lower case letters will be used (a-z)
2. No punctuation or digits will be included
3. Performance needs to be considered


### Examples
```
scramble('rkqodlw', 'world') ==> True
scramble('cedewaraaossoqqyt', 'codewars') ==> True
scramble('katas', 'steak') ==> False
```
## Idea

The idea will be comparing the elements of s1 with the elements of s2 to see if s2 is inside s1. You can either do two nested cycles or just one as I did (I prefer optimizing the code in simple but effective ways). The little trick I used to avoid covering the same char two times is implementing a swap.\
This swap will move to the begginig of s1 all the elements we've already compared so we don't cover them again. In this case I was force to copy s1 to another string because it was given as a const (this means we can't modify this variable).\
Finally, as s1 could be a bigger string that contains s2, I implemented a variable that counts everytime we found a char of s2 inside s1. If the programs ends and the variable is equal to the s2 size, then s2 is included inside s1. If not, s2 isn't included in s1.


### Code
```
#include<string>

using namespace std;

bool scramble(const std::string& s1, const std::string& s2){
  int i = 0;
  int j = 0;
  int count = 0;
  string s3 = s1;
  while (i < s1.size() && !(count == s2.size())){
    if (s2[j] == s3 [i]){
      int a = s3 [i];
      s3 [i] = s3 [j];
      s3 [j] = a;
      j++;
      i = j;
      count++;
    } else{
      i++;
    }
  }
  return count == s2.size();
}
```
