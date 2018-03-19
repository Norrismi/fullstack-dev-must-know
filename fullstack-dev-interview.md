
#### EVENT DELEGATION:

When we have a lot of elements handled in a similar way, then instead of assigning a handler to each of 
them – we put a single handler on their common ancestor.
RESOURSE: https://www.youtube.com/watch?v=6NMSCh3DJug

#####################################################

#### CLOSURE:

A closure is an inner function that has access to the outer function's variables in addition to it's own 
variables and global variables. The inner function has access not only to the outer function's variables, 
but also to the outer function's parameters. You create a closure by adding a function inside another function. 

```
const data = "Beck";

const addNumbers = (a, b) => {
  let returnValue = "the result is: ";
  
  const add = () => {
    return data + ', ' + returnValue + (a + b);
  }
  return add();
}

const result = addNumbers(5, 10);

console.log(result) // Result is: 15


//*************************************

// const addNumbers = (a, b) => {
//   let returnValue = "Result is: ";
  
//   const add = () => {
//     return returnValue + (a + b);
//   }
//   return add;
// }

// const result = addNumbers(5, 10);
// const newFunc = result();

// console.log(newFunc)
```

#####################################################


#### VIRTUAL DOM:

Let's say that you have a list that contains ten items. You check off the first item. Most JavaScript 
frameworks would rebuild the entire list. That's ten times more work than necessary! Only one item changed, 
but the remaining nine get rebuilt exactly how they were before.

React's Virtual DOM solves this problem by updating only the parts where changes have been applied and leaves the rest 
of the items untouched. 

In React, for every DOM object, there is a corresponding "virtual DOM object." A virtual DOM object 
is a representation of a DOM object, like a lightweight copy. Manipulating the DOM is slow. Manipulating 
the virtual DOM is much faster, because nothing gets drawn onscreen. Think of manipulating the virtual 
DOM as editing a blueprint, as opposed to moving rooms in an actual house. When you render a JSX element, 
every single virtual DOM object gets updated.

This sounds incredibly inefficient, but the cost is insignificant because the virtual DOM can update so quickly.

Once the virtual DOM has updated, then React compares the virtual DOM with a virtual DOM snapshot 
that was taken right before the update.

By comparing the new virtual DOM with a pre-update version, React figures out exactly which virtual DOM 
objects have changed. This process is called "diffing".

Once React knows which virtual DOM objects have changed, then React updates those objects, and only those objects, 
on the real DOM. React would be smart enough to rebuild your one checked-off list-item, and leave the rest of your list alone.

This makes a big difference! React can update only the necessary parts of the DOM. React's reputation for performance comes largely from this innovation.

In summary, here's what happens when you try to update the DOM in React:

The entire virtual DOM gets updated.
- The virtual DOM gets compared to what it looked like before you updated it. React figures out which objects have changed.
- The changed objects, and the changed objects only, get updated on the real DOM.
- Changes on the real DOM cause the screen to change.
(This material is taken from https://www.codecademy.com/articles/react-virtual-dom ).








Explain how prototypal inheritance works

What do you think of AMD vs CommonJS?

Explain why the following doesn't work as an IIFE: function foo(){ }();.

What needs to be changed to properly make it an IIFE?

What's the difference between a variable that is: null, undefined or undeclared?

How would you go about checking for any of these states?

What is a closure, and how/why would you use one?

Can you describe the main difference between a forEach loop and a .map() loop and 
why you would pick one versus the other?

What's a typical use case for anonymous functions?

How do you organize your code? (module pattern, classical inheritance?)

What's the difference between host objects and native objects?

Difference between: function Person(){}, var person = Person(), and var person = new Person()?

What's the difference between .call and .apply?

Explain Function.prototype.bind.

What's the difference between feature detection, feature inference, and using the UA string?

Explain Ajax in as much detail as possible.

What are the advantages and disadvantages of using Ajax?

Explain how JSONP works (and how it's not really Ajax).

Have you ever used JavaScript templating?

If so, what libraries have you used?

Explain "hoisting".

Describe event bubbling.

What's the difference between an "attribute" and a "property"?

Why is extending built-in JavaScript objects not a good idea?

Difference between document load event and document DOMContentLoaded event?

What is the difference between == and ===?

Explain the same-origin policy with regards to JavaScript.

Make this work:
duplicate([1,2,3,4,5]); // [1,2,3,4,5,1,2,3,4,5]

Why is it called a Ternary operator, what does the word "Ternary" indicate?

What is "use strict";? what are the advantages and disadvantages to using it?

Create a for loop that iterates up to 100 while outputting "fizz" at multiples of 3, 
"buzz" at multiples of 5 and "fizzbuzz" at multiples of 3 and 5

Why is it, in general, a good idea to leave the global scope of a website as-is and never touch it?

Why would you use something like the load event? Does this event have disadvantages? 
Do you know any alternatives, and why would you use those?

Explain what a single page app is and how to make one SEO-friendly.

What is the extent of your experience with Promises and/or their polyfills?

What are the pros and cons of using Promises instead of callbacks?

What are some of the advantages/disadvantages of writing JavaScript code in a 
language that compiles to JavaScript?

What tools and techniques do you use debugging JavaScript code?

What language constructions do you use for iterating over object properties and array items?

Explain the difference between mutable and immutable objects.

What is an example of an immutable object in JavaScript?

What are the pros and cons of immutability?

How can you achieve immutability in your own code?

Explain the difference between synchronous and asynchronous functions.

What is event loop?

What is the difference between call stack and task queue?

Explain the differences on the usage of foo between function foo() {} and var foo = function() {}

What are the differences between variables created using let, var or const?

What are the differences between ES6 class and ES5 function constructors?

Can you offer a use case for the new arrow => function syntax? 
How does this new syntax differ from other functions?

What advantage is there for using the arrow syntax for a method in a constructor?

What is the definition of a higher-order function?

Can you give an example for destructuring an object or an array?

ES6 Template Literals offer a lot of flexibility in generating strings, can you give an example?

Can you give an example of a curry function and why this syntax offers an advantage?

What are the benefits of using spread syntax and how is it different from rest syntax?

How can you share code between files?

Why you might want to create static class members?

