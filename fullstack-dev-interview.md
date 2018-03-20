
### EVENT DELEGATION:

When we have a lot of elements handled in a similar way, then instead of assigning a handler to each of <br> them – we put a single handler on their common ancestor.
them – we put a single handler on their common ancestor.

RESOURCE: https://www.youtube.com/watch?v=6NMSCh3DJug

#####################################################

### CLOSURE:

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


### VIRTUAL DOM:

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

***In summary, here's what happens when you try to update the DOM in React:***

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

## WHAT IS THE DIFFERENCE BETWEEN: NULL AND UNDEFINED?

They both indicate the absense of value. The key difference is: 
- 'null' is assigned to the variable as a representation of no value. 
- 'undefined': a variable has been declared but has not yet been assigned a value.
* Analogy: You are filling out an application form( at the DMV or Social Secirity office), you will write N/A or "not applicable" if the question is not relevant to you. This means that you have READ the question and wrote an answer(You assigned a value). But if you did not write anything, it means that you either did not know what to write, or most likely you did not even see the question. Similarly, if you do not assign a value to the variable, it returns 'undefined', if the variable has a value of 'null', then it means someone deliberately assigned 'null' value to it for whatever reason.
So, 'null' is assigned, 'undefined' is not. 


#####################################################

## CAN YOU DESCRIBE DIFFERENCE BETWEEN A FOREACH() AND .MAP()
### AND WHY WOULD YOU PICK ONE VERSUS THE OTHER?

- forEach() allows a callback function to mutate the current array, it has side effects, it iterates over a list and applies some operation with side effects to each list member (such as saving each one to the database for example)
- map() map iterates over a list, transforms each member of that list, and returns another list of the same size with the transformed members (such as converting a list of strings to uppercase)

- Why does forEach() exist when it does not return a value and if we can do the same thing with map()?:
The answer is EFFICIENCY. If you are not interested in transforming an array into another array, why should you compute the transformed array? Only to dump it? Of course not! If you don't want a transformation, you shouldn't do a transformation.



What's a typical use case for anonymous functions?

How do you organize your code? (module pattern, classical inheritance?)


#####################################################

## WHAT IS THE DIFFERENCE BETWEEN HOST OBJECTS AND NATIVE OBJECTS?
- Host objects are inherent to the environment. For the browser, this includes objects like window, document. Since they depend from the ‘host’ (environment), the behaviour could be different!

* EXAMPLES: window, document, location, history,XMLHttpRequest, setTimeout, getElementsByTagName

- Native objects are inherit from ECMAScript language and are built-in objects provided by JavaScript. So long as you’re writing in javascript you may always use them. It doesn’t matter if you are running Chrome, Firefox or Internet Explorer or even if you’re just in Node JS, you’ve got access to the native objects.

* EXAMPLES: Object (constructor), Date, Math, parseInt, eval, string methods likeindexOf and replace, array methods, …

Difference between: function Person(){}, var person = Person(), and var person = new Person()?

What's the difference between .call and .apply?

Explain Function.prototype.bind.

What's the difference between feature detection, feature inference, and using the UA string?

#####################################################

## Explain Ajax in as much detail as possible.

AJAX = Asynchronous JavaScript And XML and is NOT a programming language. AJAX uses a combination of: 
* A browser built-in XMLHttpRequest object (to request data from a web server) and 
* JavaScript and HTML DOM (to display or use the data)
- AJAX allows web pages to be updated asynchronously by exchanging data with a web server behind the scenes. This means that it is possible to update parts of a web page, without reloading the whole page. Imagine if Twitter or facebook loaded every time you "liked" or "commented" a post. AJAX lets us do some partial changes to the web page without reloading the whole page. If you "liked" or "commented" a post on facebook, instead of reloading the whole page immediately, it stages them and applies partial changes to the page. 

#####################################################

## WHAT ARE THE ADVANTAGES AND DISADVANTAGES OF USING AJAX? 

***- Advantages:***  
* AJAX allows easier and quicker interaction between user and website as pages are not reloaded for content to be displayed. 
* Easier navigation: AJAX applications on websites can be built to allow easier navigation to users in comparison to using the traditional back and forward button on a browser.

***- Disadvantages:***
* The back and refresh button are rendered useless
- With AJAX, as all functions are loaded on a dynamic page without the page being reloaded or more importantly a URL being changed (except for a hash symbol maybe), clicking the back or refresh button would take you to an entirely different web page or to the beginning of what your dynamic web page was processing. This is the main drawback behind AJAX but fortunately with good programming skills this issue can be fixed.
* It is built on javascript
- While javascript is secure and has been heavily used by websites for a long period of time, a percentage of website surfers prefer to turn javascript functionality off on their browser rendering the AJAX application useless, a work around to this con is present as well, where the developer will need to code a parallel non-javascript version of the dynamic web page to cater to these users.

#####################################################
Explain how JSONP works (and how it's not really Ajax).

Have you ever used JavaScript templating?

If so, what libraries have you used?

### Explain "hoisting".
Hoisting is JavaScript's default behavior of moving declarations to the top. In JavaScript, a variable can be declared after it has been used. In other words; a variable can be used before it has been declared. Variable declarations and function declarations are processed before any code is executed. So, declaring any variable or a function anywhere in the code is equivalent to declaring them at the top. 

- For more explanation, please follow the link: https://www.youtube.com/watch?v=HOIu3owCcZs
Different behaviors are explained when 'let' and 'const' get hoisted in these blogs:
- https://medium.freecodecamp.org/what-is-variable-hoisting-differentiating-between-var-let-and-const-in-es6-f1a70bb43d
- https://medium.freecodecamp.org/function-hoisting-hoisting-interview-questions-b6f91dbc2be8



Describe event bubbling.

What's the difference between an "attribute" and a "property"?

Why is extending built-in JavaScript objects not a good idea?

Difference between document load event and document DOMContentLoaded event?

### What is the difference between == and ===?
* Abstract equality will attempt to resolve the data types via type coercion before making a comparison. 
* Strict equality will return false if the types are different.
```
console.log(3 == "3"); // true
console.log(3 === "3"); // false.
**********
console.log("This is a string." == new String("This is a string.")); // true
console.log("This is a string." === new String("This is a string.")); // false
```

Explain the same-origin policy with regards to JavaScript.

Make this work:
duplicate([1,2,3,4,5]); // [1,2,3,4,5,1,2,3,4,5]

### Why is it called a Ternary operator, what does the word "Ternary" indicate?
* The conditional (ternary) operator is the only JavaScript operator that takes three operands. This operator is frequently used as a shortcut for the if statement.
What is "use strict";? what are the advantages and disadvantages to using it?
* "Ternary" means: in mathematics it means using three as a base.

### Create a for loop that iterates up to 100 while outputting "fizz" at multiples of 3, 
### "buzz" at multiples of 5 and "fizzbuzz" at multiples of 3 and 5
```
function fizzBuzz(n) {
  for (let i = 1; i <= n; i++) {
    if (i % 3 === 0 && i % 5 === 0) {
      console.log("fizzbuzz");
    } else if (i % 3 === 0) {
      console.log("fizz");
    } else if (i % 5 === 0) {
      console.log("buzz");
    } else {
      console.log(i);
    }
  }
}
fizzBuzz(100);
```

Why is it, in general, a good idea to leave the global scope of a website as-is and never touch it?

Why would you use something like the load event? Does this event have disadvantages? 
Do you know any alternatives, and why would you use those?

### Explain what a single page app is and how to make one SEO-friendly.
The most notable difference between a regular website and an SPA is the reduced amount of page refreshes. SPAs have a heavier usage of AJAX — a way to communicate with back-end servers without doing a full page refresh — to get data loaded into our application. As a result, the process of rendering pages happens mostly on the client-side.

- Single-page App Cons
It’s important to be aware of its cons, including:

* The browser does most of the heavy lifting, which means performance can be a problem — especially on less capable mobile devices. Careful thought must be put into search engine optimization (SEO) so your content can be discoverable by search engines and social media websites that provide a link preview.
Mitigating Cons With Server-side Rendering
Most modern JavaScript frameworks are working on ways to handle server-side rendering of SPAs — meaning the user would get a fully populated page when the SPA is loaded for the first time, instead of, for example, seeing a loading indicator. Server-side rendering can alleviate some of the burden browsers have to go through when rendering pages, and will also help with the problem of SEO and content discoverability.

What is the extent of your experience with Promises and/or their polyfills?

### What are the pros and cons of using Promises instead of callbacks?
***Callbacks are functions, promises are objects***
Source: http://jamesknelson.com/grokking-es6-promises-the-four-functions-you-need-to-avoid-callback-hell/
* Callbacks are just blocks of code which can be run in response to events such as as timers going off or messages being received from the server. Any function can be a callback, and every callback is a function.

* Promises are objects which store information about whether or not those events have happened yet, and if they have, what their outcome is.

***Callbacks are passed as arguments, promises are returned***
* Callbacks are defined independently of the functions they are called from – they are passed in as arguments. These functions then store the callback, and call it when the event actually happens.

* Promises are created inside of asynchronous functions (those which might not return a response until later), and then returned. When an event happens, the asynchronous function will update the promise to notify the outside world.

***Callbacks handle success and failure, promises don’t handle anything***
* Callbacks are generally called with information on whether an operation succeeded or failed, and must be able to handle both scenarios.

* Promises don’t handle anything by DEFAULT, but success and failure handlers are attached later.


***Callbacks can represent multiple events, promises represent at most one***
* Callbacks can be called multiple times by the functions they are passed to.

* Promises can only represent one event – they are either successful once, or failed once.

What are some of the advantages/disadvantages of writing JavaScript code in a 
language that compiles to JavaScript?

### What tools and techniques do you use debugging JavaScript code?
* Chrome DevTools - Debugger
* React Developer Tools - if you need to check 'state' and 'prop' values on ReactJS application. 
* Postman (when you need to check the server response)
* Webpack -  you most likely used the 'watchmode' - Webpack will watch your files and when one of them changes, it will immediately rerun the build and recreate your output file. For more information on how to install and use, visit here: 
https://medium.com/javascript-training/beginner-s-guide-to-webpack-b1f1a3638460
- https://medium.com/@interdigitizer/5-debugging-tools-every-javascript-programmer-should-know-and-use-38575141689c

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

### What are the differences between ES6 class and ES5 function constructors?
https://medium.freecodecamp.org/learn-es6-the-dope-way-part-v-classes-browser-compatibility-transpiling-es6-code-47f62267661

* What are the main differences? Clearly the class syntax looks like an object, but remember that actually it’s still a function and behaves so.
* Another main difference is anything you want to store must be within a constructor method. Any prototype method of the class should be inside of that class, but outside of the constructor, without writing ‘.prototype’, and in ES6 function syntax.
### Can you offer a use case for the new arrow => function syntax? How does this new syntax differ from other functions?
https://codeutopia.net/blog/2015/01/06/es6-what-are-the-benefits-of-the-new-features-in-practice/

* Declaring Functions in the ES6 syntax
  ***How does it differ?***
  * allows functions to be a single line and eliminates some of the older syntax. 
  * Arrow syntax automatically binds this to the surrounding code’s context
  * The syntax allows an implicit return when there is no body block, resulting in shorter and simpler code in some cases
  * Last but not least, => is shorter and simpler than function, although stylistic issues are often subjective
### What advantage is there for using the arrow syntax for a method in a constructor?
https://codeutopia.net/blog/2015/01/06/es6-what-are-the-benefits-of-the-new-features-in-practice/

* Arrow syntax automatically binds this to the surrounding code’s context
### What is the definition of a higher-order function?
https://www.sitepoint.com/higher-order-functions-javascript/

* A higher-order function is a function that can take another function as an argument, or that returns a function as a result
### Can you give an example for destructuring an object or an array?
http://wesbos.com/destructuring-objects/

```JS
const person = {
  first: 'Wes',
  last: 'Bos',
  country: 'Canada',
  city: 'Hamilton',
  twitter: '@wesbos'
};
const first = person.first;
const last = person.last;

const = {first, last} = person
```
### ES6 Template Literals offer a lot of flexibility in generating strings, can you give an example?
https://www.codewars.com/kata/create-phone-number/train/javascript/5a78d660fd8c06bd7e000100
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals

* Template literals are string literals allowing embedded expressions. You can use multi-line strings and string interpolation features with them. They were called "template strings" in prior editions of the ES2015 specification.
* To escape a back-tick in a template literal, put a backslash \ before the back-tick.

```JS
function createPhoneNumber(num){
return `(${num[0]}${num[1]}${num[2]}) ${num[3]}${num[4]}${num[5]}-${num[6]}${num[7]}${num[8]}${num[9]}`

(createPhoneNumber([1, 2, 3, 4, 5, 6, 7, 8, 9, 0]), "(123) 456-7890");
}
```
### Can you give an example of a curry function and why this syntax offers an advantage?
https://www.youtube.com/watch?v=iZLP4qOwY8I
https://hughfdjackson.com/javascript/why-curry-helps/

```JS
let dragon = 
  name =>
    size => 
      element => 
        name + ' is a ' +
        size + ' dragon that breathes ' +
        element + '!'
        
let output = dragon('Karo')('large')('ice')
console.log(output)
```
***Benefits***
  * Little pieces can be configured and reused with ease, without clutter;
  * Functions are used throughout.
  * Enables more reusable code. 
  
  * Another advantage of this approach is that it encourages the creation of functions; rather than of methods. While methods are beautiful things - allowing polymorphism, and very readable code - they aren’t always the tool for the job, such as in heavily async code.

### What are the benefits of using spread syntax and how is it different from rest syntax?
https://codeutopia.net/blog/2015/01/06/es6-what-are-the-benefits-of-the-new-features-in-practice/
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax

* ***Benefits*** Much more readable at a glance, You can immediately tell this function can take any number of args. And even better, we don’t need the boilerplate for using arguments.
* Any argument in the argument list can use spread syntax and it can be used multiple times.
* When copying arrays, it helps to eleminate methods such as push, splice and concat
* ***how is it different from rest?*** Rest syntax looks exactly like spread syntax, but is used for destructuring arrays and objects. In a way, rest syntax is the opposite of spread syntax: spread 'expands' an array into its elements, while rest collects multiple elements and 'condenses' them into a single element. 

### How can you share code between files?
https://medium.com/@thejasonfile/a-simple-intro-to-javascript-imports-and-exports-389dd53c3fac

* Javascript helps us out with this by having ***‘imports’ and ‘exports’.*** This is how you can write code in one file and share that code so it can be used by another file or files.
* Ask the interviewer for clarification, there is an outside chance they are looking for knowledge of Git/Github. 

### Why you might want to create static class members?
https://javascript.info/class

* In react we use static classes all of the time.
* Static methods are used when we need a function bound to a class, but not to any object of that class.
* Another example would be a so-called “factory” method

```JS

class Article {
      constructor(title, date) {
        this.title = title;
        this.date = date;
      }
    
      static createTodays() {
        // remember, this = Article
        return new this("Today's digest", new Date());
      }
    }
    
    let article = Article.createTodays();
```

* Now every time we need to create a today’s digest, we can call Article.createTodays(). Once again, that’s not a method of an article, but a method of the whole class.
