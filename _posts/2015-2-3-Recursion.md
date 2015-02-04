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
to grab a whiteboard or pen and paper and map out what is going on.  There are
many ways to do this.  Many times you might want to write the function calls
piling on top of each other and then removing them when they return like a
stack.  In this case due to simplicity we could rewrite each function in terms
of its recursive call:

```javascript
factorial(3) 
-> 3 * factorial(2) 
-> 3 * 2 * factorial(1) 
-> 3 * 2 * 1 * factorial(0) 
-> 3 * 2 * 1 * 1 = 6
```

Here is a slightly more complex recursive example that checks a linked list for
a certain value.

A linked list is a list of node objects that contain two properties: 'value'
and 'next'.  Value refers to a numerical value and next is the next node in the
list.  The final node would have a 'null' value for the next property since it
is the last node.  Each linked list also has a 'head' node, which is the first
node in the list.  This function accepts a list and a target value as the
inputs and returns 'true' or 'false' if the value is contained in the list.

One other feature of this function, is that it contains an internal subroutine
which is called recursively:

```javascript
var contains = function(list, val){
  
  //here is the subroutine:
  var drilldown = function(node){
    if(node.value === val){
      return true;
    }else if(node.next){
      return drilldown(node.next);
    }
    return false;
  };
  
  //the subroutine is called and the results are returned
  return drilldown(list.head);
};
```
#Tip \#3 - Don't forget to return the recursive results if necessary

Many times with more complex recursive situations I find myself not returning
results correctly.  For example, here is an incorrect version of the 'contains'
function above, but without a very important 'return' keyword.  Can you spot
it?

```javascript
var contains = function(list, val){
  
  //here is the subroutine:
  var drilldown = function(node){
    if(node.value === val){
      return true;
    }else if(node.next){
      drilldown(node.next);
    }
    return false;
  };
  
  //the subroutine is called and the results are returned
  return drilldown(list.head);
};

```

The above function would not work due to it not returning the necessary value
in the 'else if' block.

#Tip\#4 - Finally, loops are sometimes more useful than recursing

Depending on your situation, a loop might make more sense.  Loops can't always be substitutes for recurssion but they might provide a more intuitive solution and might be more efficient.  Here is the factorial algorithm implemented with a for-loop:

```javascript

var factorial = function(val){

  //quick input check
  if(typeof val !== 'number' || val < 0){
    return null;
  }

  //loop 
  var result = 1;
  for(var i = 2; i <= val; i++){
    result *= i;
  }

  return result;

};

```








