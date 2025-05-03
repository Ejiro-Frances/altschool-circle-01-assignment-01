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

# What is an Event

An event is an action or occurrence that happens in the browser and can be detected by JavaScript.

It is like a signal that something has happened.

All DOM nodes generate such signals when we interact with them or the browser does something with them.

## Examples of Events

- Mouse events e.g a user clicks a button
- Keyboard events e.g a user presses a key
- Form element events e.g a user submits a form
- Document events e.g when the HTML is loaded and processed
- CSS events e.g when a CSS-animation finishes.

---

## Common types of events

| Event Type           | Description                 |
| -------------------- | --------------------------- |
| `click`              | Mouse click                 |
| `submit`             | Form submission             |
| `keyup / keydown`    | Key is pressed              |
| `load`               | Page or resource is loaded  |
| `mouseover/mouseout` | Mouse moves over an element |
| `resize`             | Window size changes         |
| `change`             | Form input field is changed |
| `submit`             | Form is submitted           |

---

# Event Handlers

Handlers are functions that run in response to events. They can be assigned to handle events.

### How can handlers be assigned?

There are several ways to assign a handler.

- HTML attribute
- DOM property
- Add Event listener

<br>

#### Use <span class="bg-black text-purple-400 py-0.5 px-1.5 rounded-md">on\<event></span> properties to assign handlers in HTML or DOM properties.

<br>
<br>
For instance, to assign a click handler for an input using html attribute, we can use onclick, like here:
<br>
```html
<button onClick="alert('Click!')">Click me</button>
```

---

## Event Handlers by DOM properties

DOM properties are assigned to the event handler. They are not strings like HTML attributes, they are functions.

DOM-property case matters.

Assign a handler to elem.onclick, not elem.ONCLICK, because DOM properties are case-sensitive.

```html
<button id="elem">Click me</button>
<script>
  elem.onclick = function () {
    alert("Click!");
  };
</script>
```

---

### The onclick property in JavaScript can only store one function at a time. If you assign a new function to it, it replaces the old one.

In the example below adding a handler with JavaScript overwrites the existing handler:

```html
<input type="button" id="elem" onclick="alert('Before')" value="Click me" />

<script>
  elem.onclick = function () {
    // overwrites the existing handler
    alert("After"); // only this will be shown
  };
</script>
```

<br>
Use addEventListener() instead — it lets you attach multiple handlers without overwriting:

---

## Using addEventListener

The <span class="bg-black text-purple-400 py-0.5 px-1.5 rounded-md">addEventListener</span> method allows adding multiple handlers on the same event, with additional configuration options and ability to remove them with <span class="bg-black text-purple-400 py-0.5 px-1.5 rounded-md">removeEventListener</span>

<br>
The syntax to add a handler:

<br>

```js
element.addEventListener(event, handler, [options | useCapture]);
```

event - type of event to listen for, e.g. "click", "keydown", etc.

handler - the function to call when the event occurs is called the listener.

options - additional options like <span class="bg-black text-purple-400 py-0.5 px-1.5 rounded-md">once</span>, <span class="bg-black text-purple-400 py-0.5 px-1.5 rounded-md">capture</span>, <span class="bg-black text-purple-400 py-0.5 px-1.5 rounded-md">passive</span>, <span class="bg-black text-purple-400 py-0.5 px-1.5 rounded-md">signal</span> or useCapture - boolean, if true, then the handler is set on the capturing phase, otherwise the bubbling phase.

<br>
### To remove the handler, use removeEventListener:

```js
element.removeEventListener(event, handler, [options]);
```

## To remove a handler – assign elem.onclick = null.

---

## Examples

<br>

```js
elem.addEventListener("click", function () {
  alert("First handler");
});
elem.addEventListenter("click", function () {
  alert("Second handler");
});

const button = document.querySelector("#myBtn");

button.addEventListener("click", () => {
  alert("Button was clicked!");
});
```

---

## Note:

For some events, handlers only work with addEventListener

There exist events that can’t be assigned via a DOM-property. Only with addEventListener.

For instance, the DOMContentLoaded event, that triggers when the document is loaded and the DOM has been built.

```js
// will never run
document.onDOMContentLoaded = function () {
  alert("DOM built");
};
```

<br>

```js
// this way it works
document.addEventListener("DOMContentLoaded", function () {
  alert("DOM built");
});
```

<br>

So addEventListener is more universal. Although, such events are an exception rather than the rule.

---

# UI Events

UI (User Interface) Events are a subset of browser events related to user interaction with the web page or the browser window.

## Examples:

- load
- resize
- scroll
- focus / blur

```js
window.addEventListener("resize", () => {
  console.log("Window was resized!");
});
```

---

# Event Objects

---

## The Event Object

When an event occurs, JavaScript creates an event object that contains information about the event.

#### Common Properties of Event Objects

- event.type – type of event (e.g., "click")
- event.target – the element that triggered the event
- event.preventDefault() – stops default behavior
- event.key – key pressed (for keyboard events)

```html
<input type="text" id="myInput" placeholder="Type something..." />

<script>
  document
    .querySelector("#myInput")
    .addEventListener("keydown", function (event) {
      console.log("You pressed: " + event.key);
    });
</script>
```

<br>

##### Output: If user presses "A", it logs: You pressed: A

---

## More Code Examples

```html
<form id="myForm">
  <button type="submit">Submit</button>
</form>
```

```js
document.querySelector("#myForm").addEventListener("submit", function (event) {
  event.preventDefault(); // Stops form from submitting
  alert("Form submission prevented!");
});
```

<br>

##### The event object is also available in the html attribute

<br>

```html
<input type="button" onclick="alert(event.type)" value="Event type" />
```

---

## Object handlers: handleEvent

<br>

We can assign not just a function, but an object as an event handler using addEventListener. When an event occurs, its handleEvent method is called.

For instance:

```js
<button id="elem">Click me</button>

<script>
  let obj = {
    handleEvent(event) {
      alert(event.type + " at " + event.currentTarget);
    }
  };

  elem.addEventListener('click', obj);
</script>

```

<br>

As we can see, when addEventListener receives an object as the handler, it calls obj.handleEvent(event) in case of an event.

---

# Event Bubbling and Capturing

The standard DOM Events describes 3 phases of event propagation:

- Bubbling phase – the event bubbles up from the element.
- Target phase – the event reached the target element.
- Capturing phase – the event goes down to the element.

<br>

Note that while formally there are 3 phases, the 2nd phase (“target phase”: the event reached the element) is not handled separately: handlers on both capturing and bubbling phases trigger at that phase.

---

### Event Bubbling

Events bubble up from the target element to its ancestors.

<br>

When an event happens on an element, it first runs the handlers on it, then on its parent, then all the way up on other ancestors.

---

### Examples

A click on the inner \<p> first runs onclick:

- On that \<p>.
- Then on the outer \<div>.
- Then on the outer \<form>.
- And so on upwards till the document object.

<br>

```html
<form onclick="alert('form')">
  FORM
  <div onclick="alert('div')">
    DIV
    <p onclick="alert('p')">P</p>
  </div>
</form>
```

So if we click on \<p>, then we’ll see 3 alerts: p → div → form.

The process is called “bubbling”, because events “bubble” from the inner element up through parents like a bubble in the water.

---

## Note

### Almost all events bubble.

### The key word in this phrase is “almost”.

For instance, a focus event does not bubble. There are other examples too, but still it’s an exception, rather than a rule, most events do bubble.

## Stop Bubbling

A bubbling event goes from the target element straight up. Normally it goes upwards till \<html>, and then to document object, and some events even reach window, calling all handlers on the path.

But any handler may decide that the event has been fully processed and stop the bubbling.

The method for it is event.stopPropagation().

---

## For instance, here body.onclick doesn’t work if you click on \<button>:

<br>

```html
<body onclick="alert(`the bubbling doesn't reach here`)">
  <button onclick="event.stopPropagation()">Click me</button>
</body>
```

<br>

### event.stopImmediatePropagation()

If an element has multiple event handlers on a single event, then even if one of them stops the bubbling, the other ones still execute.

In other words, event.stopPropagation() stops the move upwards, but on the current element all other handlers will run.

To stop the bubbling and prevent handlers on the current element from running, there’s a method event.stopImmediatePropagation(). After it no other handlers execute.

#### However, Bubbling is convenient. Don’t stop it without a real need: obvious and architecturally well thought out.

---

## Capturing

There’s another phase of event processing called “capturing”

To catch an event on the capturing phase, we need to set the handler capture option to true:

<br>

```js
elem.addEventListener(..., {capture: true})

// or, just "true" is an alias to {capture: true}
elem.addEventListener(..., true)
```

---

### Event Delegation

Capturing and bubbling allow us to implement one of the most powerful event handling patterns called event delegation.

The idea is that if we have a lot of elements handled in a similar way, then instead of assigning a handler to each of them – we put a single handler on their common ancestor.

In the handler we get event.target to see where the event actually happened and handle it.

i.e attach one event listener to a parent to manage events on child elements.

```js
document.querySelector("#parent").addEventListener("click", function (event) {
  if (event.target.matches(".child")) {
    console.log("Child clicked:", event.target.textContent);
  }
});
```

---

## More Examples

```html
<ul id="menu">
  <li>Home</li>
  <li>About</li>
  <li>Contact</li>
</ul>

<script>
  menu.onclick = function (event) {
    let target = event.target;
    if (target.tagName != "LI") return;
    console.log(target.innerHTML);
  };
</script>
```

---

## src: ./pages/promises.md

```

```
