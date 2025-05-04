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
- Esther Oluwatimilehin
- Name
- Name
- Name
- Name
- Name
- Name
- Name
- Name

---

# Table of contents

You can use the `Toc` component to generate a table of contents for your slides:

<Toc minDepth="1" maxDepth="1" />

The title will be inferred from your slide content, or you can override it with `title` and `level` in your frontmatter.

<Toc text-sm minDepth="1" maxDepth="2" />

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
level: 2
---

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

[Frontend HandBook](https://frontendmasters.com/guides/front-end-handbook/2024/)
---

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

It’s especially useful for developers who want to level up their UI instincts without formal design training.
---

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
---

# Function Expression
```js
let functionName = function (parameters) {
  //function body
}
```
```js
const add = function(a, b) {
  return a + b;
};
console.log(add(2, 3)); // 5
```
```js
const greet = function(name) {
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
(function() {
  console.log("This runs immediately!");
})(); // This runs immediately!
```
Immediately invoked Function Expression with Parameters
```js
(function(name) {
  console.log(`Hello, ${name}`);
})("Alice");
```
Immediately invoked Function Expression assigned to a variable
```js
const result = (function(a, b) {
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

# Week 2 Month 1

## Loops
What are loops?
- Loops allow you to execute a block of code repeatedly.
- Loops can also be thought of like this: Imagine you have 5 apples and you eat one every day until none are left. You're repeating the same action—eating an apple—each day, as long as apples remain. That's the essence of a loop.

### Loop Declaration
Let's break down what a loop looks like by identifying its three key parts: initialization, condition, and increment — using a for loop as an example.
<div grid="~ cols- gap-2" m="t-2">

```js
for (let i = 0; i < 5; i++) {
  console.log("Loop number:", i);
} 
// Loop number: 0, Loop number: 1, Loop number: 2,  Loop number: 3, Loop number: 4


```
</div>
---

Explanation:
- let i = 0 is the initialization. It sets the starting point (we begin couting from 0).
- i < 5 is the condition. it keeps looping as long as i is less than 5.
- i++ is the increment. it increases i by 1 after each loop cycle

## Types of loops
- for Loop
- while Loop
- do...while Loop
- for...of Loop
- for...in Loop

---

# For Loop
A for loop is used to repeat a block of code a specific number of times.

### Basic Structure of a for Loop

```js

for (initialization; condition; increment) {
  // code to be repeated
}


```

#### Let's Break It Down:
- Initialization: set a starting point(e.g. let i = 0)
- Condition: 	Loop continues while this is true
- Increment: increases a variable's value by 1 every time a loop runs.

---

# Example 1: Print Numbers 1 to 5
```js
for (let i = 1; i <= 5; i++) {
  console.log("Number:", i);
}

Output:
Number: 1
Number: 2
Number: 3
Number: 4
Number: 5

```

### Example 2: Loop Through an Array
```js
const colors = ["red", "blue", "green"];

for (let i = 0; i < colors.length; i++) {
  console.log(colors[i]);
}

Output:
red
blue
green

```

---

# While Loop
A while loop is a control structure that repeats a block of code as long as a specified condition is true.

### Basic structure of a while loop
```js
while (condition) {
  // code to repeat
}

```

### Example: Count from 1 to 5
```js
let i = 1;

while (i <= 5) {
  console.log("Number:", i);
  i++; // increment
}

Output:
Number: 1
Number: 2
Number: 3
Number: 4
Number: 5

```
---

# do...while Loop
A do...while loop is similar to a while loop, but it always runs the code block at least once, even if the condition is false.

### Basic structure of a do...while loop
```js
do {
  // code to run at least once
} while (condition);

```

### Example: Print a word 3 times
```js

let count = 0;
let word = "Hello";

do {
  console.log(word);
  count++;
} while (count < 3);

Output:
Hello
Hello
Hello

```
---
# for...of Loop
The for...of loop is used to loop through the values of iterable objects like:
Arrays, Strings, Sets, Maps

### Basic structure of a for...of loop
```js
for (let value of iterable) {
  // use value
}

```

###  Example with an Array:
```js

const fruits = ["apple", "banana", "cherry"];

for (let fruit of fruits) {
  console.log(fruit);
}

Output:
apple
banana
cherry

```

---

# for...in Loop
A for...in loop is used to loop through the keys (property names) of an object.

### Basic structure of a for...in loop
```js
for (let key in object) {
  // code using key or object[key]
}

```

###  Example:
```js

const person = {
  name: "Alice",
  age: 25,
  country: "Kenya"
};

for (let key in person) {
  console.log(key + ": " + person[key]);
}


Output:
name: Alice
age: 25
country: Kenya

```

