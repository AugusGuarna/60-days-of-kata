# Cats and shelves
This exercise was taken from [codewars](https://www.codewars.com/kata/62c93765cef6f10030dfa92b)
## Task
An infinite number of shelves are arranged one above the other in a staggered fashion.
The cat can jump either one or three shelves at a time: from shelf i to shelf i+1 or i+3 (the cat cannot climb on the shelf directly above its head), according to the illustration:
```
                 ┌────────┐
                 │-6------│
                 └────────┘
┌────────┐       
│------5-│        
└────────┘  ┌─────► OK!
            │    ┌────────┐
            │    │-4------│
            │    └────────┘
┌────────┐  │
│------3-│  │     
BANG!────┘  ├─────► OK! 
  ▲  |\_/|  │    ┌────────┐
  │ ("^-^)  │    │-2------│
  │ )   (   │    └────────┘
┌─┴─┴───┴┬──┘
│------1-│
└────────┘
``` 

Start and finish shelf numbers (always positive integers, finish no smaller than start).

Find the minimum number of jumps to go from start to finish.

### Examples

Start `1`, finish `5`, then answer is `2 (1 => 4 => 5 or 1 => 2 => 5)`


## Idea

To solve the problem we got two cases to analyze:
1. The distance between start and finish is a multiple of 3
2. The distance between start and finish is not a multiple of 3

In case 1 the cat should jump `(finish-start)/3` times to do the minimum jumps possibles.\
In case 2 the cat should jump `(finish - start) % 3 + (finish-start -(finish - start) % 3)/3` timesto do the minimum jumps possibles.\
If we look closely case 1 in reality is case 2 when finish - start % 3 = 0. 

### Code
 ```
using namespace std;

unsigned int Cats(unsigned int start, unsigned int finish) {
    return (finish - start) % 3 + ((finish - start) - (finish - start) % 3)/3 ;  
}
```
