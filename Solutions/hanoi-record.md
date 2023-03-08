# Hanoi record
This exercise was taken from [codewars](https://www.codewars.com/kata/534eb5ad704a49dcfa000ba6)

## Task

Your task, is to calculate the minimal number of moves to win the game "Towers of Hanoi", with given number of disks.

### What is "Towers of Hanoi"?
Towers of Hanoi is a simple game consisting of three rods, and a number of disks of different sizes which can slide onto any rod. The puzzle starts with the disks in a neat stack in ascending order of size on one rod, the smallest at the top, thus making a conical shape.

The objective of the puzzle is to move the entire stack to another rod, obeying the following simple rules:

1. Only one disk can be moved at a time.
2. Each move consists of taking the upper disk from one of the stacks and placing it on top of another stack i.e. a disk can only be moved if it is the uppermost disk on a stack.
3. No disk may be placed on top of a smaller disk.

## Idea

This exercise can be solved pretty easily if we know (or if we manage to discover) the close formula that allows us to calculate the number of movements that are necessary to solve a hanoi puzzle.

### Code

```
#include <cmath>

unsigned long long hanoi(unsigned disks) {
  return pow(2, disks) -1;
}
```

