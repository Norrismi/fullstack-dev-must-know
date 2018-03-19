
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

#####################################################

#### WHAT IS THE DIFFERENCE BETWEEN A VARIABLE THAT IS: NULL AND UNDEFINED?

They both indicate the absense of value. The key difference is: 
- 'null' is assigned to the variable as a representation of no value. 
- 'undefined': a variable has been declared but has not yet been assigned a value.
Analogy: You are filling out an application form( at the DMV or Social Secirity office), you will write N/A or "not applicable" if the question is not relevant to you. This means that you have READ the question and wrote an answer(You assigned a value). But if you did not write anything, it means that you either did not know what to write, or most likely you did not even see the question. Similarly, if you do not assign a value to the variable, it returns 'undefined', if the variable has a value of 'null', then it means someone deliberately assigned 'null' value to it for whatever reason.
So, 'null' is assigned, 'undefined' is not. 


#####################################################

#### CAN YOU DESCRIBE THE MAIN DIFFERENCE BETWEEN A FOREACH() LOOP AND .MAP() LOOP
#### AND WHY WOULD YOU PICK ONE VERSUS THE OTHER?

- forEach() allows a callback function to mutate the current array, it has side effects, it iterates over a list and applies some operation with side effects to each list member (such as saving each one to the database for example)
- map() map iterates over a list, transforms each member of that list, and returns another list of the same size with the transformed members (such as converting a list of strings to uppercase)

Why does forEach() exist when it does not return a value and if we can do the same thing with map()?:
The answer is EFFICIENCY. If you are not interested in transforming an array into another array, why should you compute the transformed array? Only to dump it? Of course not! If you don't want a transformation, you shouldn't do a transformation.



What's a typical use case for anonymous functions?

How do you organize your code? (module pattern, classical inheritance?)


#####################################################

#### WHAT IS THE DIFFERENCE BETWEEN HOST OBJECTS AND NATIVE OBJECTS?
- Host objects are inherent to the environment. For the browser, this includes objects like window, document. Since they depend from the ‘host’ (environment), the behaviour could be different!

*EXAMPLES: window, document, location, history,XMLHttpRequest, setTimeout, getElementsByTagName

- Native objects are inherit from ECMAScript language and are built-in objects provided by JavaScript. So long as you’re writing in javascript you may always use them. It doesn’t matter if you are running Chrome, Firefox or Internet Explorer or even if you’re just in Node JS, you’ve got access to the native objects.

*EXAMPLES: Object (constructor), Date, Math, parseInt, eval, string methods likeindexOf and replace, array methods, …

Difference between: function Person(){}, var person = Person(), and var person = new Person()?

What's the difference between .call and .apply?

Explain Function.prototype.bind.

What's the difference between feature detection, feature inference, and using the UA string?

#####################################################

#### Explain Ajax in as much detail as possible.

AJAX = Asynchronous JavaScript And XML and is NOT a programming language. AJAX uses a combination of: *A browser built-in XMLHttpRequest object (to request data from a web server) and *JavaScript and HTML DOM (to display or use the data)
AJAX allows web pages to be updated asynchronously by exchanging data with a web server behind the scenes. This means that it is possible to update parts of a web page, without reloading the whole page. 
Imagine if Twitter or facebook loaded every time you "liked" or "commented" a post. AJAX lets us do some partial changes to the web page without reloading the whole page. If you "liked" or "commented" a post on facebook, instead of reloading the whole page immediately, it stages them and applies partial changes to the page. 

#####################################################

#### WHAT ARE THE ADVANTAGES AND DISADVANTAGES OF USING AJAX? 

- Advantages:  
*AJAX allows easier and quicker interaction between user and website as pages are not reloaded for content to be displayed. *Easier navigation: AJAX applications on websites can be built to allow easier navigation to users in comparison to using the traditional back and forward button on a browser.

- Disadvantages:
*The back and refresh button are rendered useless
With AJAX, as all functions are loaded on a dynamic page without the page being reloaded or more importantly a URL being changed (except for a hash symbol maybe), clicking the back or refresh button would take you to an entirely different web page or to the beginning of what your dynamic web page was processing. This is the main drawback behind AJAX but fortunately with good programming skills this issue can be fixed.
*It is built on javascript
While javascript is secure and has been heavily used by websites for a long period of time, a percentage of website surfers prefer to turn javascript functionality off on their browser rendering the AJAX application useless, a work around to this con is present as well, where the developer will need to code a parallel non-javascript version of the dynamic web page to cater to these users.

#####################################################
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

