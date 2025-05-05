---
layout: center
transition: fade-out
---

# [Functions]{.text-teal-400}

---
class: text-sm
transition: fade
---

<div class="grid grid-cols-2 gap-4">

<div>
<h3 class= "text-teal-400" >Functions</h3>

- Functions are reusable blocks of code designed to perform a specific task.
- They allow you to write cleaner, more modular, and maintainable code.

<h5 class= "text-teal-300" >Function Declaration</h5>

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
<section class= "text-sm">
<ul>
Explanation:
<li>function calculateArea(...) is a function declaration.</li>
<li>It takes two parameters: width and height.</li>
<li>It returns the area by multiplying them.</li>
<li>You can call it anywhere after (or even before) the declaration thanks to hoisting.</li>
  <!-- <img border="rounded" src="https://github.com/slidevjs/themes/blob/main/screenshots/theme-default/01.png?raw=true" alt=""> -->
  <!-- <img border="rounded" src="https://github.com/slidevjs/themes/blob/main/screenshots/theme-seriph/01.png?raw=true" alt=""> -->
</ul>
</section>
 </div>

</div>

<div>

<h5 class= "text-teal-300" >Function Expression</h5>

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
</div>

</div>
---

<h3 class= "text-teal-300" > Arrow Function </h3>

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

<h3 class= "text-teal-300" >Default Parameters</h3>

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

<h3 class= "text-teal-300" >Rest Parameters</h3>

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

<h3 class= "text-teal-300" >CallBack Function</h3>

```js
function processUserInput(callback) {
  const name = "Jane";
  callback(name);
}
processUserInput((name) => console.log(`Hi, ${name}`)); // Hi, Jane
```

```js {all}{maxHeight:'120px'}
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

<h3 class= "text-teal-300" >Immediately invoked Function Expression</h3>

```js
(function () {
  console.log("This runs immediately!");
})(); // This runs immediately!
```

<h3 class= "text-teal-300" >Immediately invoked Function Expression with Parameters</h3>

```js
(function (name) {
  console.log(`Hello, ${name}`);
})("Alice");
```

<h3 class= "text-teal-300" >Immediately invoked Function Expression assigned to a variable</h3>

```js
const result = (function (a, b) {
  return a + b;
})(5, 3);

console.log(result); // 8
```

<h3 class= "text-teal-300" >Arrow Function IIFE</h3>

```js
(() => {
  console.log("Arrow function IIFE");
})(); // Arrow function IIFE
```