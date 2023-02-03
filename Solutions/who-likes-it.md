# Who likes it?

This exercise was taken from [Codewars](https://www.codewars.com/kata/5266876b8f4bf2da9b000362)

## Task
You probably know the "like" system from Facebook and other pages. People can "like" blog posts, pictures or other items. We want to create the text that should be displayed next to such an item.

Implement the function which takes an array containing the names of people that like an item. It must return the display text as shown in the examples.


### Examples
```
[]                                -->  "no one likes this"
["Peter"]                         -->  "Peter likes this"
["Jacob", "Alex"]                 -->  "Jacob and Alex like this"
["Max", "John", "Mark"]           -->  "Max, John and Mark like this"
["Alex", "Jacob", "Mark", "Max"]  -->  "Alex, Jacob and 2 others like this"
```
Note: for 4 or more names, the number in `"and 2 others"` simply increases.


## Idea
To solved this problem I basically divided the code in the five cases that were indicated.

### Code
```
#include <string>
#include <vector>

using namespace std;

std::string likes(const std::vector<std::string> &names)
{
  
    if (names.size() == 0) {
      return "no one likes this";
    } else if (names.size() == 1){
      return names[0] + " likes this";
    } else if (names.size() == 2){
      return names[0] + " and " + names[1] + " like this";
    } else if (names.size() == 3){
      return names[0] + ", " + names[1] + " and " + names[2] + " like this";
    } else if (names.size() >= 4){
      int n = names.size() - 2;
      return names[0] + ", " + names[1] + " and " + to_string(n) + " others like this";
    }
}
```
