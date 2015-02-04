--- 
layout: post 
title: February, 3, 2015 San Francisco
---


# Recursion - Tips and Pitfalls

If you enjoy puzzles and programming, you might enjoy implementing solutions
using recursive techniques.  Although a powerful tool, recursion can lead to
some head-banging confusion.  I've put together some things to keep in mind
while writing your recursive algorithms.

For this tutorial I will demonstrate with a simple recursive function to
calculate the factorial of a number:

```javascript
var factorial = function(val){
  
  //quick input check
  if(typeof val !== 'number' || val < 0){
    return null;
  }

  //here's the meat

  if(val === 0){
    return 1;
  }

  return val * factorial(val-1);
}
```

#\#1 - Base Case (or exit condition)

I always like to first note what the base would be where the recursive function
would end and stop recursing.  This is very important, as without this check
the function would continue to call itself without end.  In our example, the
base case is defined right after the input check:

```javascript
  if(val === 0){
    return 1;
  }
```

#\#2 - When in doubt, map it out

If the recursive nature is too difficult to model in your head it never hurts
to grab a whiteboard or pen and paper and map out what is going on.  Many times
you might want to write the function calls piling on top of each other and then
removing them when they return like a stack:
                                                factorial(0)    1
                                factorial(1)    factorial(1)    factorial(1)    1
                factorial(2)    factorial(2)    factorial(2)    factorial(2)    factorial(2)    2
factorial(3) -> factorial(3) -> factorial(3) -> factorial(3) -> factorial(3) -> factorial(3) -> factorial(3) -> 6



```javascript
var y = 5;

```
#\#3 - When in doubt, draw it out


#\#4 - The function doesn't end with the recursive call









