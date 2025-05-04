---
# You can also start simply with 'default'
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: #000000
# some information about your slides (markdown enabled)
title: Circle one Assignment
info: |
  ## Slidev Starter Template
  Presentation slides for Circle one.

  Learn more at [Sli.dev](https://sli.dev)
# apply unocss classes to the current slide
class: text-center
# https://sli.dev/features/drawing
drawings:
  persist: false
# slide transition: https://sli.dev/guide/animations.html#slide-transitions
transition: slide-left
# enable MDC Syntax: https://sli.dev/features/mdc
mdc: true
# open graph
# seoMeta:
#  ogImage: https://cover.sli.dev
---

# Circle one

Presentation slides for Assignment one

<div @click="$slidev.nav.next" class="mt-12 py-1" hover:bg="white op-10">
  Press Space for next page <carbon:arrow-right />
</div>

<div class="abs-br m-6 text-xl">
  <button @click="$slidev.nav.openInEditor()" title="Open in Editor" class="slidev-icon-btn">
    <carbon:edit />
  </button>
  <a href="https://github.com/slidevjs/slidev" target="_blank" class="slidev-icon-btn">
    <carbon:logo-github />
  </a>
</div>

<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

---

## Circle One members

- Busari Olanrewaju
- Reuben Agbor
- Elinah Mmbone
- Ejiro Francess Ejoh
- Salaudeen Rukayat Temitope
- Name
- Name
- Name
- Name

---

# Table of contents

You can use the `Toc` component to generate a table of contents for your slides:

<Toc minDepth="1" maxDepth="1" />

---

# Week 1 Month 1

In the First Week we discussed about using Learning How To Learn, Frontend HandBook and Refactoring UI Book

#### Learning How To Learn

Learning how to learn means improving your ability to acquire and retain knowledge by understanding how your mind works. It involves: Metacognition: Being aware of and managing your learning strategies, Effective Techniques: Using spaced repetition, active recall, interleaving, and elaboration, Strategy Over Style: Choosing the right method for the material, not relying on learning "styles.", Feedback & Reflection: Regularly assessing and adjusting your approach, Environment & Motivation: Staying focused with clear goals and a good setup.

It’s about learning smarter, not just harder.

Would you like a visual cheat sheet of these principles?

[Learning how to Learn](https://www.coursera.org/learn/learning-how-to-learn?)

<!-- Inline style -->
<style>
.footnotes-sep {
  @apply mt-5 opacity-10;
}
.footnotes {
  @apply text-sm opacity-75;
}
.footnote-backref {
  display: none;
}
</style>

---

## level: 2

# Frontend HandBook

The Frontend Handbook is a guide that outlines best practices, tools, and knowledge areas for frontend developers. It serves as a roadmap for learning and improving in frontend development.

Key Components:
Foundational Skills: Covers HTML, CSS, and JavaScript—the core of frontend.

Frameworks & Libraries: Introduces tools like React, Vue, or Angular.

Tooling: Explains bundlers (Webpack, Vite), package managers, version control (Git), etc.

Performance & Accessibility: Emphasizes speed and inclusive design.

Architecture & Design Patterns: Guides you in building scalable, maintainable codebases.

Testing & Deployment: Covers how to test code and ship to production.

Career & Collaboration: Offers advice on working in teams, communication, and job roles.

It’s like a map for becoming a competent frontend developer—from beginner to advanced.

## [Frontend HandBook](https://frontendmasters.com/guides/front-end-handbook/2024/)

# Refactoring UI

Refactoring UI is a design guide by Adam Wathan and Steve Schoger that teaches developers how to create beautiful, usable interfaces—without needing to be a designer.

Core Ideas:
Design isn’t just about visuals—it's about clarity, hierarchy, and usability.

Small tweaks = big impact: Improving spacing, alignment, contrast, and typography can transform a UI.

Start with structure: Get layout and content right before worrying about colors or details.

Use systems: Consistent spacing, font sizes, and color scales make design easier and better.

Refactor like code: Improve UI in iterations, just like refactoring messy code.

Key Topics:
Visual hierarchy,
Spacing and layout,
Color usage and contrast,
Typography,
Reusable design patterns,
Real-world before/after UI makeovers

## It’s especially useful for developers who want to level up their UI instincts without formal design training.

# Functions

- Functions are reusable blocks of code designed to perform a specific task.
- They allow you to write cleaner, more modular, and maintainable code.

Function Declaration

<div grid="~ cols- gap-2" m="t-2">

```js
function greet(name) {
  return `Hello, ${name}!`;
}
console.log(greet("Alice")); // Hello, Alice!
```

```js
function calculateArea(width, height) {
  return width * height;
}
console.log(calculateArea(5, 10)); // 50
```

Explanation:

- function calculateArea(...) is a function declaration.
- It takes two parameters: width and height.
- It returns the area by multiplying them.
  You can call it anywhere after (or even before) the declaration thanks to hoisting.
  <!-- <img border="rounded" src="https://github.com/slidevjs/themes/blob/main/screenshots/theme-default/01.png?raw=true" alt=""> -->
  <!-- <img border="rounded" src="https://github.com/slidevjs/themes/blob/main/screenshots/theme-seriph/01.png?raw=true" alt=""> -->

 </div>

# Function Expression

```js
let functionName = function (parameters) {
  //function body
};
```

```js
const add = function (a, b) {
  return a + b;
};
console.log(add(2, 3)); // 5
```

```js
const greet = function (name) {
  return `Hello, ${name}`;
};
console.log(greet("Liam")); // Hello, Liam
```

---

# Arrow Function

```js
const multiply = (a, b) => a * b;
console.log(multiply(4, 5)); // 20
```

```js
const createUser = (name, age) => ({
  name: name,
  age: age,
});

console.log(createUser("Alice", 30));
// { name: 'Alice', age: 30 }
```

Default Parameters

```js
function sayHello(name = "Guest") {
  return `Hello, ${name}`;
}
console.log(sayHello()); // Hello, Guest
```

```js
function makeGreeting(name, message = `Hi ${name}, welcome!`) {
  return message;
}

console.log(makeGreeting("John")); // Hi John, welcome!
```

---

# Rest Parameters

```js
function sum(...numbers) {
  return numbers.reduce((a, b) => a + b, 0);
}
console.log(sum(1, 2, 3, 4)); // 10
```

```js
function findMax(...numbers) {
  return Math.max(...numbers);
}
console.log(findMax(3, 7, 2, 9, 5)); // 9
```

CallBack Function

```js
function processUserInput(callback) {
  const name = "Jane";
  callback(name);
}
processUserInput((name) => console.log(`Hi, ${name}`)); // Hi, Jane
```

---

# contd on CallBack Function

```js
function processArray(arr, callback) {
  arr.forEach(callback);
}

function printElement(element) {
  console.log(element);
}

const numbers = [1, 2, 3, 4, 5];
processArray(numbers, printElement);
// Output:
//
```

---

# new

dragPos:
square: -55,0,0,0

---

# Immediately invoked Function Expression

```js
(function () {
  console.log("This runs immediately!");
})(); // This runs immediately!
```

Immediately invoked Function Expression with Parameters

```js
(function (name) {
  console.log(`Hello, ${name}`);
})("Alice");
```

Immediately invoked Function Expression assigned to a variable

```js
const result = (function (a, b) {
  return a + b;
})(5, 3);

console.log(result); // 8
```

Arrow Function IIFE

```js
(() => {
  console.log("Arrow function IIFE");
})(); // Arrow function IIFE
```

---
layout: center

---

# Array

<v-click>Understanding arrays in JavaScript</v-click>

---

## What is an Array?
In JavaScript, an **array** is a special variable that can hold more than one value at a time. These values can be of any data type, including numbers, strings, and even other arrays.

You can think of an array as a data structure that stores list of items. Instead of creating seperate variables for each items:

```js
let item1 = "Pen" ;
let item2 = "Book";
let item3 = "Ruler";
```

You can just do this instead:

```js
let items = ["Pen", "Book", "Ruler"];👍
let again=1;
```

It's like a container that stores values in a specific order.

---

## Why Use Array?

<p></p>

+ To group related data
- To loo through data easily
+ To manage list (e.g. a list of users, scores, products)


Imagine trying to store 100 scroes without an array 😫

---

## Array Declaration

There are two syntaxes to create an empty array namely sqauare bracket notation [] and Array Constructor.

### Array Literal (Square Bracket Notation)

```js
let arr = []; //this is an empty array

let myArr = ["Apple", "Orange", "Pear"];

```

<v-click>
<h1></h1>

### Array Constructor 

```js
let arr = new Array(); //this is an empty array

let myArr = new Array("Apple", "Orange", "Pear")
```

The array literal ```[]``` is the most commonly used syntax.

</v-click>

<div v-click class="text-xl">

⚠️ ***Warning***

Note: Using the literal from ```[]``` is preferred because it is simpler and less error-prone.

</div>

---

## Accessing Array Elements

In JavaScript, array elements are indexed starting from zero, meaning the first element has an index of 0, the second 1, and so on.
To access a specific element in an array, use square brackets ([]) with the index number of the element you want.

```js
let fruits = ["Apple", "Orange", "Pear"];
console.log(fruits[0]); // Output: Apple
console.log(fruits[2]); // Output: Pear
```
You can modify the elements in an array by assigning the value of a specific index.

***Example***: Let's modify the first index ```Apple``` to ```Banana```

```js
fruits[0] = "Banana"

console.log(fruits[0]); // Output: Apple

console.log(fruits); // Output: ["Banana", "Orange", "Pear"]

```
---

- **Array Length**

The ```.length``` property of an array returns the total number of elements in the array. 

```js
let fruits = ["Apple", "Orange", "Pear"];
console.log(fruits.length); // Output: 3

```
<p></p>

### Array Methods

Array methods are built in functions in JavaScript that allow you to manipulate and interact with data stored in arrays easily.
You can use them to add, remove, modify, rearrange or search array elements.

Some commonly used array methods are:
 
**push()** - Adds elements to the end of an array

```js
let fruits = ["Apple", "Orange", "Pear"];
fruits.push("Strawberry");

console.log(fruits);

// Output: ["Apple", "Orange", "Pear", "Strawberry"]
```
---

### **Array Method Contd.**

<div class="grid grid-cols-2 gap-4">

<div>

**pop()** - Removes the last elements from an array

```js
fruits.pop(); // Output: "Strawberry"
console.log(fruits);
// Output: ["Apple", "Orange", "Pear"]
```

**shift()** - Removes the first elements from an array

```js
fruits.shift(); // Output: "Apple"
console.log(fruits);
// Output: ["Orange", "Pear"]
```


**unshift()** - Adds elements to the beginning of an array

```js
fruits.unshift("Strawberry", "Banana");

console.log(fruits);

// Output: ["Strawberry", "Banana", "Orange", "Pear"]

```
</div>

<div>

**slice()** - Returns selected elements in an array as a new array

```js
const newFruits = fruits.slice(0, 2);

console.log(newFruits);

// Output: ["Strawberry", "Banana"]

```

**reverse()** - Reverses the order of the elements in an array

```js
fruits. reverse()

onsole.log(fruits);

// Output: ["Pear", "Orange" "Banana", "Strawberry"]

```

</div>

</div>

---

# Objects

Objects are data types used to store data in **key: value pair**. It is used to group  related data in a single variable.

```js
 let user = {
  name: "Zara",
  age: 35,
  isAdmin: true,
 }
```

Each ```key``` is also called a property, and it is associated value can be any data type: string, number, array, function etc.

#### Objects can be created in two ways:
1. Using Object Literals
```js
// Using object literal
 let user = {}

```
2. Object Constructor
```js
//Using Object Constructor
 let user = new Object()

```
---

### **Acessing Object Properties**

To access a proper of an obkect, you can use **dot notation** or **bracket notation**. Dot notation is the most commint way to access property.

```js
//Using Dot Notation

console.log(user.name);
// output : "Zara"

```
```js
//Using Bracket Notation

console.log(user["user"]);
// output : "Zara"
```

Bracket notation is useful when you want to access a propery name stored in a variable.
```js
const key = "age";

console.log(user[key]);

// output : "Zara"
```
---

You can add, remove or modify object anytime.

```js
user.age = 30; // modify the age property
user.location = "Lagos"; // add new property and value
delete user.isAdmin // delete the property
console.log(user);

//output: {name: "Zara", age: 30, location: "Lagos}
```

Objects can also contain functions, which are called **methods**. Object methods are actions that can be performed on objects.

```js
 let person ={
  firstName: "Zara",
  lastName: "Joel",
  age: 15,
  greet: function() {
    console.log("Hello, my name is " + this.firstName + " " + this.lastName)
  }
 }
 person.greet(); // output: Hello, my name is Zara Joel
```

 ```this``` keyword in this example refers to the ```person``` object

---
src: ./pages/promises.md
---

---

````md
# Understanding Async & Await

---

# What is Async/Await?

Async/await is a modern way to handle asynchronous code in JavaScript.  
It makes asynchronous code look and behave like synchronous code, making it easier to read and understand.

---

# Basic Syntax

```js
async function myFunction() {
  const result = await someAsyncOperation();
  console.log(result);
}
````

* `async` keyword: declares an async function
* `await`: pauses function execution until promise resolves

---

# Fetch API Example

```js
async function fetchData() {
  const response = await fetch('https://api.example.com/data');
  const data = await response.json();
  console.log(data);
}
```

---

# Error Handling with Try...Catch

```js
async function getData() {
  try {
    const response = await fetch('https://api.example.com/data');
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.error('Error:', error);
  }
}
```

* Cleaner error handling
* No `.catch()` chaining

---

# Async/Await vs Promises

| Promises           | Async/Await    |
| ------------------ | -------------- |
| `.then()` chaining | Cleaner syntax |
| Harder to read     | Easier to read |
| `.catch()` needed  | `try...catch`  |

---

# Key Takeaways

* Async/await simplifies asynchronous code
* Use `await` only inside async functions
* Always handle errors with `try...catch`

---

# Mini Demo: Simulate an Async Task

```js
function wait(ms) {
  return new Promise(resolve => setTimeout(resolve, ms));
}

async function runDemo() {
  console.log('Task starting...');
  await wait(2000); // waits 2 seconds
  console.log('Task completed after 2 seconds!');
}

runDemo();
```

---
src: ./pages/events.md
---