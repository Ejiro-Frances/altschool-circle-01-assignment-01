---
layout: center
transition: fade-out
---

# [Promises, async/await]{.text-teal-400}

<div mt-2 />

- <a href="" @click="$slidev.nav.next()">Introduction: callbacks</a>
- <a href="" @click="$nav.go()">Promise</a>
- <a href="" @click="$nav.go()">Promises Chaining</a>
- <a href="" @click="$nav.go()">Error handling with promises</a>
- <a href="" @click="$nav.go()">Promise API</a>
- <a href="" @click="$nav.go()">Promisification</a>
- <a href="" @click="$nav.go()">Microtasks</a>
- <a href="" @click="$nav.go()">Async/await</a>


---
hideInToc: true
class: text-sm
scrollable: true
---

## [Introduction: callbacks]{.text-teal-300}

Okay, so I learned about asynchronous programming in JavaScript using callbacks. It's about running code later, not immediately.

`setTimeout` is one example, and so is loading scripts. The `loadScript` function dynamically adds a `<script>` tag to the page, causing the browser to load and execute it. But the code after `loadScript` doesn't wait for the script to finish loading.

```javascript {all}
function loadScript(src) {
  let script = document.createElement("script");
  script.src = src;
  document.head.append(script);
}

loadScript("/my/script.js");
// the code below loadScript runs without waiting
```

To know when a script has loaded, you can use a callback function.

```javascript {all}{maxHeight:'100px'}
function loadScript(src, callback) {
  let script = document.createElement("script");
  script.src = src;
  script.onload = () => callback(script); //Callback on load of file
  document.head.append(script);
}

loadScript("/my/script.js", function () {
  // this code runs after the script loads
  newFunction();
});
```

If you need to load scripts in sequence, you nest the `loadScript` calls within each other's callbacks.

```javascript {2|all}
loadScript("/my/script.js", function (script) {
  loadScript("/my/script2.js", function (script) {
    // ...
  });
});
```

---
class: text-sm
---

## [Handling errors:]{.text-teal-300}

Error handling is important. The callback function should accept an error argument, so you can check for loading errors. The "error-first callback" convention says that the first argument of the callback is reserved for error (if any).

```javascript
function loadScript(src, callback) {
  let script = document.createElement("script");
  script.src = src;

  script.onload = () => callback(null, script); // null means no error
  script.onerror = () => callback(new Error(`Script load error for ${src}`));

  document.head.append(script);
}

loadScript("/my/script.js", function (error, script) {
  if (error) {
    // handle the error
  } else {
    // script loaded successfully
  }
});
```

---
class: text-sm
---

## [Pyramid of Doom]{.text-teal-300}

A big problem with callbacks is the "pyramid of doom" or "callback hell." When you have many nested callbacks, the code becomes hard to read and manage.

```javascript {all}{maxHeight:'100px'}
loadScript("1.js", function (error, script) {
  if (error) {
    handleError(error);
  } else {
    loadScript("2.js", function (error, script) {
      if (error) {
        handleError(error);
      } else {
        loadScript("3.js", function (error, script) {
          // ...
        });
      }
    });
  }
});
```

You can try to flatten the structure by using named functions for each step, but it makes the code fragmented and harder to follow.

```javascript {all}{maxHeight:'180px'}
loadScript("1.js", step1);

function step1(error, script) {
  if (error) {
    handleError(error);
  } else {
    loadScript("2.js", step2);
  }
}
// ... and so on
```

Promises are a better way to handle asynchronous code and avoid the pyramid of doom.

##

---
hideInToc: true
class: text-sm
---

## [Promise]{.text-teal-300}

Okay, so a Promise in JavaScript is like a way to handle something that takes time, like a singer releasing a song. Imagine a singer promising fans a new song.

```javascript
let promise = new Promise(function (resolve, reject) {
  // executor (the producing code, "singer")
});
```

`new Promise()` creates a Promise object. The function you give it, called the **executor**, is the "producing code." It's the singer working on the song. The `resolve` and `reject` arguments are functions provided by JavaScript.

- `resolve(value)`: Call this when the job is done _successfully_, with the result `value`.
- `reject(error)`: Call this if there's an _error_, with the error object.

The Promise object has internal properties:

- `state`: Initially `"pending"`, then `"fulfilled"` if `resolve` is called, or `"rejected"` if `reject` is called.
- `result`: Initially `undefined`, then the `value` passed to `resolve` or the `error` passed to `reject`.

---
class: text-sm
---

Here's an example of a successful Promise:

```javascript
let promise = new Promise(function (resolve, reject) {
  setTimeout(() => resolve("done"), 1000); // Simulates a delay
});
```

This code will set the promise to fulfilled after 1 second.

Here's one that rejects:

```javascript
let promise = new Promise(function (resolve, reject) {
  setTimeout(() => reject(new Error("Whoops!")), 1000);
});
```

This code will set the promise to rejected after 1 second.

**Key Points:**

- The executor runs _immediately_ when the `Promise` is created.
- `resolve` or `reject` should only be called _once_. Subsequent calls are ignored.
- It's best to `reject` with `Error` objects.
- You can call `resolve` or `reject` immediately, without a delay.

---
class: text-sm
---

The `state` and `result` are internal, so you can't directly access them.

**Consumers: `then`, `catch`**

These are how "fans" get notified.

- `promise.then(successCallback, errorCallback)`: `successCallback` runs when the Promise is `resolved`, `errorCallback` runs when the Promise is `rejected`.

Example:

```javascript {2|6|all}{maxHeight:'100px'}
let promise = new Promise((resolve) => {
  setTimeout(() => resolve("done!"), 1000);
});

promise.then(
  (result) => alert(result), // shows "done!" after 1 second
  (error) => alert(error) // doesn't run
);
```

- `promise.catch(errorCallback)`: This is the same as `promise.then(null, errorCallback)`. It's for handling errors only.
  Example:

```javascript {2|6|all}{maxHeight:'100px'}
let promise = new Promise((resolve, reject) => {
  setTimeout(() => reject(new Error("Whoops!")), 1000);
});

promise.catch(alert); // shows "Error: Whoops!" after 1 second
```

---
hideInToc: true
class: text-sm
---

## [Promises chaining]{.text-teal-300}

Promises chaining passes results through `.then` handlers. Each `.then` returns a new promise, enabling chaining.

**Basic Example:**

```javascript {all}{maxHeight:'100px'}
new Promise((resolve) => setTimeout(() => resolve(1), 1000))
  .then((result) => {
    alert(result); // 1
    return result * 2;
  })
  .then((result) => {
    alert(result); // 2
    return result * 2;
  })
  .then((result) => alert(result)); // 4
```

Multiple `.then` on a single promise aren't chaining, they run independently.

**Incorrect Chaining:**

```javascript {all}{maxHeight:'100px'}
let promise = new Promise((resolve) => setTimeout(() => resolve(1), 1000));

promise.then((result) => alert(result)); // 1
promise.then((result) => alert(result)); // 1
```

Returning a promise from a `.then` handler makes the chain wait for it to resolve.

**Returning Promises:**

```javascript {2|5|all}{maxHeight:'100px'}
new Promise((resolve) => setTimeout(() => resolve(1), 1000))
  .then((result) => {
    return new Promise((resolve) =>
      setTimeout(() => resolve(result * 2), 1000)
    );
  })
  .then((result) => alert(result)); // 2
```

This enables sequential asynchronous actions.

A `.then` can return a "thenable" (object with a `.then` method).

**Thenable Example:**

```javascript {all}{maxHeight:'100px'}
class Thenable {
  constructor(num) {
    this.num = num;
  }
  then(resolve) {
    setTimeout(() => resolve(this.num * 2), 1000);
  }
}

new Promise((resolve) => resolve(1))
  .then((result) => new Thenable(result))
  .then(alert); // shows 2 after 1000ms
```

Example using `fetch` to load and display a GitHub avatar:

```javascript {2|10|all}{maxHeight:'100px'}
function loadJson(url) {
  return fetch(url).then((response) => response.json());
}

function loadGithubUser(name) {
  return loadJson(`https://api.github.com/users/${name}`);
}

function showAvatar(githubUser) {
  return new Promise((resolve) => {
    let img = document.createElement("img");
    img.src = githubUser.avatar_url;
    document.body.append(img);
    setTimeout(() => {
      img.remove();
      resolve(githubUser);
    }, 3000);
  });
}

loadJson("/article/promise-chaining/user.json")
  .then((user) => loadGithubUser(user.name))
  .then(showAvatar)
  .then((githubUser) => alert(`Finished showing ${githubUser.name}`));
```

Key takeaway: Return promises (or thenables) from `.then` handlers for sequential asynchronous operations.



---
hideInToc: true
class: text-sm
---

## [Error handling with promises]{.text-teal-300}

Okay, so promises are good at dealing with errors. When a promise rejects, like if a website doesn't exist, `.catch` will jump in to handle it. You don't have to put `.catch` right after the thing that might fail; it can be later in the chain.

```javascript {all}{maxHeight:'60px'}
fetch("https://no-such-server.blabla")
  .then((response) => response.json())
  .catch((err) => alert(err));
```

Basically, there's like a "try...catch" built-in around promise code. So if something throws an error inside a promise, it automatically becomes a rejected promise.

```javascript {5|all}{maxHeight:'120px'}
new Promise((resolve, reject) => {
  throw new Error("Whoops!");
}).catch(alert);

//Same as:

new Promise((resolve, reject) => {
  reject(new Error("Whoops!"));
}).catch(alert);
```

If you throw an error in a `.then`, it's like rejecting the promise.

```javascript {5|all}{maxHeight:'100px'}
new Promise((resolve, reject) => {
  resolve("ok");
})
  .then((result) => {
    throw new Error("Whoops!");
  })
  .catch(alert);
```

---
class: text-sm
---

If the `.catch` cannot handle the error, rethrow it. Error handling propagates up the chain until it is handled.

```javascript {all}{maxHeight:'150px'}
new Promise((resolve, reject) => {
  throw new Error("Whoops!");
})
  .catch(function (error) {
    if (error instanceof URIError) {
      // handle it
    } else {
      alert("Can't handle such error");
      throw error;
    }
  })
  .then(function () {
    /* doesn't run here */
  })
  .catch((error) => {
    alert(`The unknown error has occurred: ${error}`);
  });
```

If an error isn't handled, the browser will usually show something in the console and you can handle errors with `unhandledrejection`.

```javascript
window.addEventListener("unhandledrejection", function (event) {
  alert(event.promise);
  alert(event.reason);
});

new Promise(function () {
  throw new Error("Whoops!");
});
```

So, use `.catch` where you know how to deal with errors, and rethrow errors that the block doesn't know how to handle. If you can't recover, it's okay to not use `.catch`, but always have `unhandledrejection` to prevent app crashing.

---
hideInToc: true
class: text-sm
---

## [Promise API]{.text-teal-300}

There are 6 static methods in the `Promise` class.

**Static Methods:**

- **`Promise.all(iterable)`:** Waits for all promises in `iterable` to resolve, returns array of results. Rejects immediately if any promise rejects. Order of results matches order in `iterable`.

```javascript {all}
Promise.all([
  new Promise((resolve) => setTimeout(() => resolve(1), 1000)),
  2,
  3,
]).then(alert); // 1, 2, 3
```

- **`Promise.allSettled(iterable)`:** Waits for all promises to settle (resolve or reject). Returns array of objects with `{status: 'fulfilled' | 'rejected', value?: any, reason?: any}`.

```javascript {all}
Promise.allSettled([Promise.resolve(1), Promise.reject("Error")]).then(
  (results) => console.log(results)
);
//[{status: 'fulfilled', value: 1}, {status: 'rejected', reason: 'Error'}]
```

- **`Promise.race(iterable)`:** Waits for the _first_ promise to settle. Returns its result/error.

```javascript {3|all}{maxHeight:'100px'}
Promise.race([
  new Promise((resolve) => setTimeout(() => resolve(1), 1000)),
  Promise.reject(new Error("Whoops!")),
]).then(alert, alert); // Whoops! (reject wins)
```

- **`Promise.any(iterable)`:** Waits for the _first_ promise to fulfill (resolve). Returns its result. If all reject, rejects with `AggregateError`.

```javascript {1|all}{maxHeight:'200px'}
Promise.any([Promise.reject("Error1"), Promise.resolve(1)]).then(alert); // 1
```

---
class: text-sm
---

- **`Promise.resolve(value)`:** Creates a resolved promise with `value`.
- **`Promise.reject(error)`:** Creates a rejected promise with `error`.

**Use Cases:**

- `Promise.all`: Execute multiple async operations concurrently.
- `Promise.allSettled`: Handle multiple async operations, regardless of success/failure.
- `Promise.race`: Implement timeouts or choose the fastest operation.
- `Promise.any`: Find the first successful result from multiple attempts.
- `Promise.resolve`/`Promise.reject`: Less common due to async/await.

---
hideInToc: true
class: text-sm
---

## [Promisification]{.text-teal-300}

Okay, so I learned about "promisification." It's basically turning a function that uses callbacks into one that returns a Promise. This is useful because Promises are often easier to work with than callbacks, especially when dealing with asynchronous operations.

Here's a simple example:

```javascript {maxHeight: '200px'}
function loadScript(src, callback) {
  let script = document.createElement("script");
  script.src = src;

  script.onload = () => callback(null, script);
  script.onerror = () => callback(new Error(`Script load error for ${src}`));

  document.head.append(script);
}

// Usage (callback style)
// loadScript('script.js', (err, script) => {...})
```

---
class: text-sm
---

This `loadScript` function uses a callback. To promisify it, we can create a wrapper:

```javascript {all}{maxHeight: '200px'}
let loadScriptPromise = function (src) {
  return new Promise((resolve, reject) => {
    loadScript(src, (err, script) => {
      if (err) {
        reject(err);
      } else {
        resolve(script);
      }
    });
  });
};

// Usage (Promise style)
// loadScriptPromise('script.js').then(...);
```

The `loadScriptPromise` now returns a Promise. To make this more reusable, we can create a `promisify` helper function:

```javascript {all}{maxHeight: '200px'}
function promisify(f) {
  return function (...args) {
    return new Promise((resolve, reject) => {
      function callback(err, result) {
        if (err) {
          reject(err);
        } else {
          resolve(result);
        }
      }
      args.push(callback);
      f.call(this, ...args);
    });
  };
}

// Usage:
// let loadScriptPromise = promisify(loadScript);
// loadScriptPromise('script.js').then(...);
```

This `promisify` function takes a function `f` and returns a new function that returns a Promise.

There is also an advanced version of `promisify` that can handle callbacks with multiple results:

```javascript {3|all}{maxHeight: '200px'}
function promisify(f, manyArgs = false) {
  return function (...args) {
    return new Promise((resolve, reject) => {
      function callback(err, ...results) {
        if (err) {
          reject(err);
        } else {
          resolve(manyArgs ? results : results[0]);
        }
      }
      args.push(callback);
      f.call(this, ...args);
    });
  };
}
```

This version either returns a single result if the original callback returns only 1 result or an array of results if the original callback returns multiple results.

---
hideInToc: true
class: text-sm
---

## [Microtasks]{.text-teal-300}

Okay, so promises are always asynchronous. Even if a promise resolves immediately, the `.then`/`.catch`/`.finally` handlers don't run right away.

```javascript
let promise = Promise.resolve();
promise.then(() => alert("promise done!"));
alert("code finished");
```

In this example, `"code finished"` alerts first because promise handlers go into a "microtask queue" (also called `PromiseJobs` in the ECMA specification). This queue is FIFO. The JavaScript engine only runs these microtasks after the current code finishes executing. So, after the `alert("code finished")` line runs, the engine checks the microtask queue and then runs the `.then` handler.

---
class: text-sm
---

If you want to control the order, chain `.then` calls:

```javascript
Promise.resolve()
  .then(() => alert("promise done!"))
  .then(() => alert("code finished"));
```

As for unhandled rejections, JavaScript only fires the `unhandledrejection` event _after_ the microtask queue is empty and there's still a rejected promise without a `.catch`.

```javascript
let promise = Promise.reject(new Error("Promise Failed!"));
window.addEventListener("unhandledrejection", (event) => alert(event.reason));
```

In this example, the `unhandledrejection` event will fire and show the error message. Even if you add a `.catch` later using `setTimeout`, it's too late; the event has already triggered.

---
src: ./async-await.md
---