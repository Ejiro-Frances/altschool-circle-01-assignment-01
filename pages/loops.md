---

# Week 2 Month1

## Loops

What are loops?

- Loops allow you to excute a block of code repeatedly.
- Loops can also be thought of this: Imagine you have 5 apples and you eat one everyday until none are left. You're repeating the same action—eating an apple—each day, as long as apples remain. That's the essence of a loop.

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

### Explanation:

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
=======
layout: center

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
  // use value}
```

###  Example with an Array:


```js
const fruits = ["apple", "banana", "cherry"];

for (let fruit of fruits) {
  console.log(fruit);}
```

Output:
apple
banana
cherry
=======

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

---