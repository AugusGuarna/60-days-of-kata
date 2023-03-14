# Basic encryption

This exercise was taken from [codewars](https://www.codewars.com/kata/5862fb364f7ab46270000078)

## Task

The most basic encryption method is to map a char to another char by a certain math rule. Because every char has an ASCII value, we can manipulate this value with a simple math expression. For example 'a' + 1 would give us 'b', because 'a' value is 97 and 'b' value is 98.

You will need to write a method which does exactly that -

get a string as text and an int as the rule of manipulation, and should return encrypted text. for example:

encrypt("a",1) = "b"

Full ascii table is used on our question (256 chars) - so 0-255 are the valid values.

If the value exceeds 255, it should 'wrap'. ie. if the value is 345 it should wrap to 89.

Good luck.

## Idea

To solve the problem the idea will be take taking the ASCII value of the correspondan char and sum the given integer.
### Code
```
#include <string>
std::string encrypt(std::string text, int rule) {
  for (int i = 0; i < text.size(); i++){
    char encryption = (text[i]+rule)%256;
    text [i] = encryption;
  }
  return text;
};
```
