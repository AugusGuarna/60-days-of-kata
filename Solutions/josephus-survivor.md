# Josephus survivor
This exercise was taken from [codewars](https://www.codewars.com/kata/555624b601231dc7a400017a)

## Task

In this kata you have to correctly return who is the "survivor", ie: the last element of a [Josephus permutation](https://www.codewars.com/kata/josephus-permutation/).

Basically you have to assume that n people are put into a circle and that they are eliminated in steps of k elements, like this:

```
n=7, k=3 => means 7 people in a circle
one every 3 is eliminated until one remains
[1,2,3,4,5,6,7] - initial sequence
[1,2,4,5,6,7] => 3 is counted out
[1,2,4,5,7] => 6 is counted out
[1,4,5,7] => 2 is counted out
[1,4,5] => 7 is counted out
[1,4] => 5 is counted out
[4] => 1 counted out, 4 is the last element - the survivor!
```

The above link about the "base" kata description will give you a more thorough insight about the origin of this kind of permutation, but basically that's all that there is to know to solve this kata.

**Notes and tips**: using the solution to the other kata to check your function may be helpful, but as much larger numbers will be used, using an array/list to compute the number of the survivor may be too slow; you may assume that both n and k will always be >=1.

## Idea

To solve the problem we're going to first create a vector with all the people (vector.size() = n) and then just like in the [previous Josephus problem](https://github.com/AugusGuarna/60-days-of-kata/blob/main/Solutions/josephus-permutation.md) we're going to delete elements from the vector but this time until its lenght is equal to 1.

### Code

```
#include <vector>

int josephusSurvivor(int n, int k) {
  std::vector<int> v (n, 0);
  for (int j = 0; j < v.size(); j++){
    v[j] = 1 + j;
  }
  int i = 0;
  while (v.size() > 1){
    i = (i + k - 1) % v.size();
    v.erase(v.begin() + i);
  }
  return v[0];
}
```

