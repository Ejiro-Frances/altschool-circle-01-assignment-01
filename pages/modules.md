---
layout: center
transition: fade
---

# [Modules and Bundlers]{.text-teal-400}

---
hideInToc: true
class: text-sm
---

## [WHAT ARE MODULES]{.text-teal-300}

Modules are individual files of code that each handle a specific part of your application. They allow you to break your code into smaller, reusable pieces instead of writing everything in one large file.

#### Example
```js
// math.js
export function add(a, b) {
  return a + b;
}

// app.js
import { add } from './math.js';
console.log(add(2, 3)); // Output: 5
```

### [what do we use modules for?]{.text-teal-300}

Modules allow you to break large codebases into smaller, logical pieces (e.g., files or components).
Each module handles one specific task or feature.

```js {2|all}{maxHeight: '120px'}
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
hideInToc: true
class: text-sm
---

## [What is a Bundler?]{.text-teal-300}

A bundler is a tool that takes all your JavaScript (or other types of) files and combines them into one or a few files that a browser can run efficiently.

A bundler:

- Resolves all your imports and dependencies

- It figures out what each file needs and pulls it together into one place.

- Combines all modules into one (or a few) files


---
hideInToc: true
class: text-sm
---

#### Example:

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

