
# MODULES AND BUNDLERS

---

# WHAT ARE MODULES

Modules are individual files of code that each handle a specific part of your application. They allow you to break your code into smaller, reusable pieces instead of writing everything in one large file.

### Example


```js
// math.js
export function add(a, b) {
  return a + b;
}

// app.js
import { add } from './math.js';
console.log(add(2, 3)); // Output: 5
```

# what do we use modules for?

Modules allow you to break large codebases into smaller, logical pieces (e.g., files or components).
Each module handles one specific task or feature.

```js

// math.js
export function add(a, b) {
  return a + b;
}

// app.js
import { add } from './math.js';
console.log(add(2, 3)); // 5
```

Makes Code Reusable :Functions, classes, or constants defined in one module can be imported and reused anywhere. This reduces duplication and improves consistency

---

# What is a Bundler? 
A bundler is a tool that takes all your JavaScript (or other types of) files and combines them into one or a few files that a browser can run efficiently.

A bundler:

- Resolves all your imports and dependencies

- It figures out what each file needs and pulls it together into one place.

- Combines all modules into one (or a few) files

---

# Example 

before bundling: multiple files

```js
// utils.js
export function greet(name) {
  return `Hello, ${name}`;
}

// main.js
import { greet } from './utils.js';
console.log(greet('Doris'));
```

After bundline - single file

```js
function greet(name) {
  return `Hello, ${name}`;
}
console.log(greet('Doris'));
```