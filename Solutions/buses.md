# Buses!

This exercise was taken from [codewars](https://www.codewars.com/kata/640dee7cbad3aa002e7c7de4)

## Task

To get to the health camp, the organizers decided to order buses. It is known that some children `kids` and `adults` adults are going to go to the camp. Each bus has a certain number of seats `places`. There must be at least two adults on each bus in which children will travel.

Determine whether it will be possible to send all children and adults to the camp, and if so, what is the minimum number of buses required to order for this.

**Input data:**

arguments kids, adults, places each of them does not exceed 10,000.

**Output data:**

we need to return the number of buses that need to be ordered. If it is impossible to send everyone to the camp, return 0

### Examples

```
kids=10, adults=4, places=7 --> 2 (2 buses, both seating 2 adults & 5 kids)
kids=10, adults=4, places=5 --> 0 (impossible to send everyone to the camp)

```


## Idea

To solve the problem we must pay attention to the different cases that may happen.
1. If the number of places is 0, we must return 0.
2. To calculate the busses that are needed we can do (kids + adults)/ places but in case the result is not whole we gotta sum 1. This is because the bus we're adding will cover the remainder.
3. If we've got no kids but we've got adults, then we can return the buses.
4. If adults >= 2 * buses_needed then we can return the buses.
5. If we've got enough parents to travel with the kids but there's a parent that must travel in a bus alone, we've gotta return the buses.

### Code
```
int buses(const int kids, const int adults, const int places) {
  int buses_needed = 0;
  if (places == 0){
    return buses_needed;
  } else {
    buses_needed = (kids + adults)/places;
  }
  if ((kids + adults) % places != 0){
    buses_needed++;
  }
  if (adults >= 2 * buses_needed || (kids == 0 && adults > 0)|| (kids > 0 && adults > 0 && (kids+adults-1)%places == 0 && (adults-1) == 2 * (buses_needed-1))){
    return buses_needed;
  } else {
    return 0;
  }
}
```