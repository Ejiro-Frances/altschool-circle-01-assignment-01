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
- Ejiro Francess Ejoh
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

<div class="flex w-full items-center justify-center h-full">
 <h1>Events</h1>
</div>

---

# Events

Events are actions or occurences that happen in the system you are programming, which the system tells you about so you can respond to them in some way if desired. Is like a signal that something has happened.

All DOM nodes generate such signals when we interact with them or the browser does something with them.

Here sre some examples of events:

<div>
<ul>
<li>A mouse <span class="bg-black text-purple-400 py-0.5 px-1.5 rounded-md">click</span>, <span class="bg-black text-purple-400 py-0.5 px-1.5 rounded-md">contextmenu</span>, <span class="bg-black text-purple-400 py-0.5 px-1.5 rounded-md">mouseover</span>/<span class="bg-black text-purple-400 py-0.5 px-1.5 rounded-md">mouseout</span>, <span class="bg-black text-purple-400 py-0.5 px-1.5 rounded-md">mousedown</span>/<span class="bg-black text-purple-400 py-0.5 px-1.5 rounded-md">mouseup</span>, <span class="bg-black text-purple-400 py-0.5 px-1.5 rounded-md">mousemove</span> , touch screen tap, or key press <span class="bg-black text-purple-400 py-0.5 px-1.5 rounded-md">keydown</span>, <span class="bg-black text-purple-400 py-0.5 px-1.5 rounded-md">keyup</span></li>
<li>A form input field was changed <span class="bg-black text-purple-400 py-0.5 px-1.5 rounded-md">change</span>, the form was submitted <span class="bg-black text-purple-400 py-0.5 px-1.5 rounded-md">submit</span>, a file was dragged over the element.</li>
<li>The page has loaded <span class="bg-black text-purple-400 py-0.5 px-1.5 rounded-md">load</span>, <span class="bg-black text-purple-400 py-0.5 px-1.5 rounded-md">DOMContentLoaded</span>, the video is ready <span class="bg-black text-purple-400 py-0.5 px-1.5 rounded-md">loadeddata</span>, the window was resized <span class="bg-black text-purple-400 py-0.5 px-1.5 rounded-md">resize</span>, etc.</li>
</ul>
<p>
Handlers are functions that run in response to events. They can be assigned to handle events. We have HTML-attribute, DOOM-property, and <span class="bg-black text-purple-400 py-0.5 px-1.5 rounded-md">addEventListener</span> method to assign handlers. Use <span class="bg-black text-purple-400 py-0.5 px-1.5 rounded-md">on event</span> properties to assign handlers in HTML or DOM properties.
</p>
</div>

```html
<button onClick="alert('Click!')">Click me</button>
```

---

## More on Event Handlers

DOM properties are assigned to the event handler. They are not strings like HTML attributes. They are functions.

```html
<button id="elem">Click me</button>
<script>
  elem.onClick = function () {
    alert("Click!");
  };
</script>
```

The <span class="bg-black text-purple-400 py-0.5 px-1.5 rounded-md">addEventListener</span> method allows adding multiple handlers on the same event, with additional configuration options and ability to remove them with <span class="bg-black text-purple-400 py-0.5 px-1.5 rounded-md">removeEventListener</span>

```js
elem.addEventListener("click", function () {
  alert("First handler");
});
elem.addEventListenter("click", function () {
  alert("Second handler");
});
```

---

<span class="bg-black text-purple-400 py-0.5 px-1.5 rounded-md">element.addEventListener(event, handler, [options|useCapture])</span>

event - type of event to listen for, e.g. "click", "keydown", etc.

handler - the function to call when the event occurs is called the listener.

options - additional options like <span class="bg-black text-purple-400 py-0.5 px-1.5 rounded-md">once</span>, <span class="bg-black text-purple-400 py-0.5 px-1.5 rounded-md">capture</span>, <span class="bg-black text-purple-400 py-0.5 px-1.5 rounded-md">passive</span>, <span class="bg-black text-purple-400 py-0.5 px-1.5 rounded-md">signal</span> or useCapture - boolean, if true, then the handler is set on the capturing phase, otherwise the bubbling phase.

```js
interface AddEventListenerOptions extends EventListenerOptions {
  once?: boolean
  passive?: boolean
  signal?: AbortSignal
}
```

```js
const elem = document.querySelector(`[data-slidev-no="211"] h1`);
const handler = () => alert("Click!");
elem.addEventListener("click", handler, { once: true });
```

---

## Event Object
