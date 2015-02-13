--- 
layout: post 
title: February, 12, 2015 San Francisco
---


# Clean Code

Once you have your algorithm mapped out and pseudocode written it is easy to start crunching out the actual code to solve the problem, but do yourself and your team a favor and put a lot of focus on writing clean code.  This post will give some idea as to what people are expecting when they ask you to clean your code up, or make it easier to read.

###Properly Indent Your Code

Code is much easier to read when it is properly indented, and quite frankly, if you're not indenting your code properly you will come off as a complete rookie, or even careless. 

To easily indent your written code in Sublime Text, you can highlight the code and click Edit -> Line -> Reindent.

There is no keyboard shortcut for this, but you could add one by going to Preferences -> Key Bindings-User and editing the file by adding the following code inside the outermost square brackets:

```javascript

{ "keys": ["ctrl+k","ctrl+l"],"command":"reindent","args": {"single_line": false}}

```
This will allow you to reindent your entire document by clicking 'ctrl+k+l' without highlighting anything.

###Use Descriptive Variable Names

This is another expected practice when working in teams.  If you are still using variable names like 'x' or 'z', people are going to be very upset with you.  You might also be upset with yourself a month down the road when you're revisiting your code and trying to figure out what you meant.  Programming can be difficult enough without putting the task of trying to decipher your code onto your teammates.

Bad
```javascript

var x = 0;

```
Good
```javascript

  var counterForVisits = 0;

```

###Keep Functions Simple

Sometimes it feels easier to cram a lot of functionality into one function, but when working with a team, this can be very confusing when others are reading your work.  It is a best practice to limit the tasks of your functions to as few as possible, ideally even just one task.  This limits the amount of time your function sits on top of the call stack.  With only one task in your function's body, it can complete that task and return a result, removing itself from the call stack.

###Keep Function Names Specific

Again, this almost goes without saying.  When writing code, always think you are writing for other people to read, or even you down the road.  If your function returns a boolean, perhaps it should be called 'isSomething'.  If your function gets some value, perhaps it should be called 'getSomeValue'.  I think you get the idea.

###Terse is not Better

It seems that many people new to programming are always amazed when they see one line of code that does a very complex task, but usually such functionality crammed into one line of code is not understandable by intelligent people.  Terse is not better in the world of writing clean code and especially when working with teams.  Most professionals won't think you are clever or advanced by writing terse code, they will most likely think you haven't worked on a team before or are very new to the field.

Keep it clean, keep it descriptive, and understand you are writing for your teammates and your future self.  












