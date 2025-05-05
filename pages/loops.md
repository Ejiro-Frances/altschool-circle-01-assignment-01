---
layout: center
transition: fade
---

# [Loops]{.text-teal-400}

---
class: text-sm
transition: fade
---

<h2 class= "text-teal-300 mt-3">What are loops?</h2>

<v-click>
<ul class= "mt-3">
<li>Loops allow you to execute a block of code repeatedly.</li>
<li>Loops can also be thought of like this: Imagine you have 5 apples and you eat one every day until none are left. You're repeating the same action—eating an apple—each day, as long as apples remain. That's the essence of a loop.</li>
</ul>
</v-click>

<v-click>
<h4 class="text-teal-300 mt-3">Loop Declaration</h4>
Let's break down what a loop looks like by identifying its three key parts: initialization, condition, and increment — using a for loop as an example.
<div grid="~ cols- gap-2" m="t-2">

```js
for (let i = 0; i < 5; i++) {s
  console.log("Loop number:", i);
} 
// Loop number: 0, Loop number: 1, Loop number: 2,  Loop number: 3, Loop number: 4
```
</div>

Explanation:
- let i = 0 is the initialization. It sets the starting point (we begin couting from 0).
- i < 5 is the condition. it keeps looping as long as i is less than 5.
- i++ is the increment. it increases i by 1 after each loop cycle
</v-click>


---
class: text-sm
---

<h3 class="text-teal-300 mt-3">Types of loops</h3>

- for Loop
- while Loop
- do...while Loop
- for...of Loop
- for...in Loop

<h4 class="text-teal-300 mt-3">For Loop</h4>

A for loop is used to repeat a block of code a specific number of times.

<h5 class="text-teal-100 mt-3">Basic Structure of a for Loop</h5>

```js

for (initialization; condition; increment) {
  // code to be repeated
}


```

<h5 class="text-teal-300 mt-3">Let's Break It Down:</h5>

- Initialization: set a starting point(e.g. let i = 0)
- Condition: 	Loop continues while this is true
- Increment: increases a variable's value by 1 every time a loop runs.

---
class: text-sm
transition: fade
---

<div class="grid grid-cols-2 gap-4">

<div>
<h5 class="text-teal-300 mt-3">Example 1: Print Numbers 1 to 5</h5>
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
</div>

<div>
<h5 class="text-teal-300 mt-3">Example 2: Loop Through an Array</h5>

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
</div>
</div>


<h4 class="text-teal-300 mt-3">While Loop</h4>
A while loop is a control structure that repeats a block of code as long as a specified condition is true.

<div class="grid grid-cols-2 gap-4">
<div>
<h5 class="text-teal-300 mt-3">Basic structure of a while loop</h5>
```js
while (condition) {
  // code to repeat
}

```
</div>

<div>
<h5 class="text-teal-300 mt-3">Example: Count from 1 to 5</h5>
```js {all}{maxHeight: '150px'}
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
</div>
</div>

---
class: text-sm
---

<h4 class="text-teal-300 mt-3">do...while Loop</h4>
A do...while loop is similar to a while loop, but it always runs the code block at least once, even if the condition is false.

<h5 class="text-teal-100 mt-3">Basic structure of a do...while loop</h5>
```js
do {
  // code to run at least once
} while (condition);

```

<h5 class="text-teal-300 mt-3">Example: Print a word 3 times</h5>
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
class: text-sm
---

<h4 class="text-teal-300 mt-3">for...of Loop</h4>

The for...of loop is used to loop through the values of iterable objects like:

Arrays, Strings, Sets, Maps

<h5 class="text-teal-300 mt-3">Basic structure of a for...of loop</h5>

```js
for (let value of iterable) {
  // use value
}

```

<h5 class="text-teal-300 mt-3">Example with an Array:</h5>
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
class: text-sm
---

<h4 class="text-teal-300 mt-3">for...in Loop</h4>

A for...in loop is used to loop through the keys (property names) of an object.

<h5 class="text-teal-300 mt-3">Basic structure of a for...in loop</h5>
```js
for (let key in object) {
  // code using key or object[key]
}

```

<h5 class="text-teal-300 mt-3">Example:</h5>
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
