# Sum of angles

This exercise was taken from [Codewars](https://www.codewars.com/kata/5a03b3f6a1c9040084001765)

## Task

Find the total sum of internal angles (in degrees) in an n-sided simple polygon. N will be greater than 2.


## Idea

This problems can be easily solved by using a lil bit of geometry knowledge. If we analyze the sum of the **internal** angles of different polygons we find a pattern (I took this well known and simple figures because the task tells us that we'll be analyzing n-sided simple polygons):
1. Triangle = 180°
2. Square = 360°
3. Pentagons = 540°
4. Hexagons = 720°

If we pay attention we see that the sum has this pattern:
1. 180° * 1
2. 180° * 2
3. 180° * 3
4. 180° * 4

So, we can affirm that the sum of the internal angles of an n-sided simple polygon is
```
(n-2)*180°
```

### Code
```
int angle(int n) {
  return (n-2)*180;
}
```
