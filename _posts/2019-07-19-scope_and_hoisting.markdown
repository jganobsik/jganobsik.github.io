---
layout: post
title:      "Scope and Hoisting"
date:       2019-07-19 16:10:37 +0000
permalink:  scope_and_hoisting
---


Today I will be explaining two important and sometimes confusing elements of JavaScript: **Scope and Hoisting**. I will also cover how ES6 syntax affects Scope and Hoisting, and some best practices for declaring variables with Scope and Hoisting in mind. Let's start with some basic definitions.

# What Is Scope?
**Scope** refers to the visibility of a variable, which is dependent on how and where the variable is declared. Each new function we declare has a **Local** scope, and functions within functions have their own local scope too. Variables with **Local** scope are only accessible within their respective functions.   **Global** scope allows variables to be accessed by any function on a page. Variables are declared globally when they are initialized outside of a function, typically at the top of a page.

Local Scope Example
```
function myFunction() {
    let localVariable = 5;
    localVariable++;
		return localVariable;
 
}

function addTwoToLocalVariable(){
    localVariable + 2;
   	return localVariable;
}
```

If we run myFunction, we will always get 6 as the result, no matter how many times we run it. This is because our function creates a new local variable each time we run it, and it disappears afterwards. Running addTwoToLocalVariable results in an error informing us that localVariable is undefined, since it cannot access the local variable declared within the myFunction function.

Global Scope Example 
```
let globalVariable = 10

function myFunction() {
   
    globalVariable++
    return globalVariable;
}

function addTwoToGlobalVariable(){
    globalVariable += 2;
    return globalVariable;
}

```

In this example, myFunction will add 1 to globalVariable each time it is called. If I run myFunction 10 times, globalVariable's value is 20.  addTwoToGlobalVariable will add 2 to globalVariable each time it is called with no issues, since it is accessing a global variable now.
# What Is Hoisting?
**Hoisting** refers to the placement and declaration of variables and functions and how this affects their behavior when called.  Examine the following code:

```
console.log(num); 
let num = 6;
```

This code returns an error because we are attempting to call a variable before it has been declared.

```
num = 6
console.log(num); 
let num;
```

This code will also produce an error, since variables declared with let are not hoisted
```
num = 6
console.log(num); 
var num;
```
This code will work, as variables declared with var are hoisted.  Many people refer to **Hoisting** as bringing your variable or function to the top of the page. While this works as a mental model, the actual reason behind why our third example works has to do with the javascript compiler, specifically the way the compiler stores variables in memory. 
# Best Practices

 Now that we have covered scope and hoisting, we should have a good idea about how our variables will interact with our code. To wrap everything up, let's examine some best practices for declaring variables.
 
**Global Const vs Let**

If we go back to our Global Variables example and change let to const, our code will break. This is because a constant can only be declared and assigned once. Once assignment has occured, we cannot change the value. As such, we should use Const when we want to ensure that the variable's assigned value stays the same. The inverse is also true: variables which need to be changed should be declared with let or var.

**Looping**

Let and Var are very similar, but there is one particular use case where let behaves differently. Examine these two simple for loops, one declared with let, the other with var
```
function iterate() {
    //i is *not* visible out here

    for( let i = 0; ti < 5; i++ ) {
        //i is only visible in here (and in the for() parentheses)
        //and there is a separate i variable for each iteration of the loop
    }

    //i is *not* visible out here
}

functionwithVar() {
    //i *is* visible out here

    for( var i = 0; i < 5; i++ ) {
        //i is visible to the whole function
    }

    //i *is* visible out here
}

```

Imagine i declared my iterator variable using **value** instead of **i**. I could unintentionally interfere with other things that i declared using value. Granted, this example would demonstrate poor variable naming on the programmer's part. A much more likely scenario would be working on a large code base where it is possible that other programmers are not following best practices in variable naming. In this scenario, using let can help us avoid unintended collision between variables, and ensure that we are not interfering with code outside our loop.

**Global  vs Local  Variables**

When we are declaring and assigning variables, we should keep in mind how and when they should be used. If we wish to modify a variable several times and keep the result, global variables are the way to go. If we only want to keep track of something within a function, local variables would be the proper solution. 

Thanks for following along, I hope you gained some valuable insight into scope and hoisting!






