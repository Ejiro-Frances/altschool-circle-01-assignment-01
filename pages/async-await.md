# Understanding Async & Await

---

# What is Async/Await?

Async/await is a modern way to handle asynchronous code in JavaScript.  
It makes asynchronous code look and behave like synchronous code, making it easier to read and understand.

# Basic Syntax

```js
async function myFunction() {
  const result = await someAsyncOperation();
  console.log(result);
}
````

* `async` keyword: declares an async function
* `await`: pauses function execution until promise resolves

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

```js {all}{maxHeight:'130px'}
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

##

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

