# Remove anchor from URL
This exercise was taken from [Codewars](https://www.codewars.com/kata/51f2b4448cadf20ed0000386)

## Task
Complete the function/method so that it returns the url with anything after the anchor (`#`) removed.

### Examples
```
"www.codewars.com#about" --> "www.codewars.com"
"www.codewars.com?page=1" -->"www.codewars.com?page=1"
```

## Idea
The solution to this problem comes pretty easy if we have a basic knowledge of strings. We gotta keep in mind that strings work just like vectors.\
The idea will be using a linear search that stops once found the anchor "#".
Once found the place where the anchor is located, we save that position and we print the string from 0 to that index. For this step we're going to create a new string. Then we can return that new string or copy the new string into the old one and return the old one.

### Code
```
std::string replaceAll(std::string str) {
  int i = 0;
  int stringSize = str.size();
  while (i < stringSize && str[i] != '#'){
    i++;
  }
  int j = 0;
  std::string a;
  while (j<i){
    a.push_back(str[j]);
    j++;
  }
  return a;
}
```
