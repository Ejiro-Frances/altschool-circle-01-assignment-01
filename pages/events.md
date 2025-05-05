---
layout: center
transition: fade-out
---

# [Events]{.text-teal-400}

---
hideInToc: true
class: text-sm
---

# [What is an Event]{.text-teal-400}

An event is an action or occurrence that happens in the browser and can be detected by JavaScript.

It is like a `signal` that something has happened.

All DOM nodes generate such signals when we interact with them or the browser does something with them.

## [Examples of Events]{.text-teal-300}

<br>

- Mouse events e.g a user clicks a button
- Keyboard events e.g a user presses a key
- Form element events e.g a user submits a form
- Document events e.g when the HTML is loaded and processed
- CSS events e.g when a CSS-animation finishes.

---
class: text-sm
---

## [Common Types of Events]{.text-teal-300}

| Event Type           | Description                 |
| -------------------- | --------------------------- |
| `click`              | Mouse click                 |
| `submit`             | Form submission             |
| `keyup / keydown`    | Key is pressed              |
| `load`               | Page or resource is loaded  |
| `mouseover/mouseout` | Mouse moves over an element |
| `resize`             | Window size changes         |
| `change`             | Form input field is changed |

---
hideInToc: true
class: text-sm
---

# [Event Handlers]{.text-teal-400}

Handlers are functions that run in response to events.

There are three ways to assign an event handler.

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
class: text-sm
---

## [Assign Handlers by DOM property]{.text-teal-300}

DOM properties are assigned to event handlers. They are not strings like HTML attributes, they are functions.

- DOM-property case matters: 

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
class: text-sm
---

### Note:

`The onclick property in JavaScript can only store one function at a time. If you assign a new function to it, it replaces the old one.`

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

- To attach multiple handlers without overwriting, use addEventListener() instead

---
class: text-sm
---

## [Assign Handlers using addEventListener]{.text-teal-300}

The <span class="bg-black text-purple-400 py-0.5 px-1.5 rounded-md">addEventListener</span> method allows us to add multiple handlers on the same event, with additional configuration options and ability to remove them with <span class="bg-black text-purple-400 py-0.5 px-1.5 rounded-md">removeEventListener</span>

The syntax to add or remove a handler is:

```js
element.addEventListener(event, handler, [options | useCapture]);

element.removeEventListener(event, handler, [options | useCapture]);
```

- event: type of event to listen for, e.g. `click`

- handler: function to call when the event occurs is called the listener.

- options: additional options like <span class="bg-black text-purple-400 py-0.5 px-1.5 rounded-md">once</span>, <span class="bg-black text-purple-400 py-0.5 px-1.5 rounded-md">capture</span>, <span class="bg-black text-purple-400 py-0.5 px-1.5 rounded-md">passive</span>, <span class="bg-black text-purple-400 py-0.5 px-1.5 rounded-md">signal</span> or useCapture - boolean, if true, then the handler is set on the capturing phase, otherwise the bubbling phase.

#### Examples

```js {2|5|9|all}{maxHeight: '120px'}
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
class: text-sm
---

## Note: 
- To remove a handler – assign elem.onclick = null.
- For some events, handlers only work with addEventListener

For instance, the DOMContentLoaded event, that triggers when the document is loaded and the DOM has been built.

```js
// will never run
document.onDOMContentLoaded = function () {
  alert("DOM built");
};
```
```js
// this way it works
document.addEventListener("DOMContentLoaded", function () {
  alert("DOM built");
});
```

---
class: text-sm
---

## [The Event Object]{.text-teal-300}

When an event occurs, JavaScript creates an event object that contains information about the event.

#### [Common Properties of Event Objects]{.text-teal-200}

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

 Output: If user presses "A", it logs: You pressed: A

---
class: text-sm
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

The event object is also available in the html attribute

```html
<input type="button" onclick="alert(event.type)" value="Event type" />
```
---
class: text-sm
---

## [Object handlers: handleEvent]{.text-teal-300}

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

As we can see, when `addEventListener` receives an object as the handler, it calls obj.handleEvent(event) in case of an event.

---
hideInToc: true
class: text-sm
---

# [Event Propagation]{.text-teal-300}

The standard DOM Events describes 3 phases of event propagation:

- Bubbling phase – the event bubbles up from the element.
- Target phase – the event reached the target element.
- Capturing phase – the event goes down to the element.

Note that while formally there are 3 phases, the 2nd phase (“target phase”: the event reached the element) is not handled separately: handlers on both capturing and bubbling phases trigger at that phase.

### [Event Bubbling]{.text-teal-300}

Events bubble up from the target element to its ancestors.

When an event happens on an element, it first runs the handlers on it, then on its parent, then all the way up on other ancestors.

- Almost all events bubble.

For instance, a focus event does not bubble. There are other examples too, but still it’s an exception, rather than a rule, most events do bubble.

---
class: text-sm
--- 

### Examples

A click on the inner \<p> first runs onclick:

- On that \<p>.
- Then on the outer \<div>.
- Then on the outer \<form>.
- And so on upwards till the document object.

```html
<form onclick="alert('form')">
  FORM
  <div onclick="alert('div')">
    DIV
    <p onclick="alert('p')">P</p>
  </div>
</form>
```

So if we click on \<p>, then we'll see 3 alerts: p - div - form.

The process is called “bubbling”, because events “bubble” from the inner element up through parents like a bubble in the water.

---
class: text-sm
---

### To stop bubbling

- use `event.stopPropagation()`.
- `event.stopImmediatePropagation()`

<br>

##### For instance, here body.onclick doesn’t work if you click on \<button>:

<br>

```html
<body onclick="alert(`the bubbling doesn't reach here`)">
  <button onclick="event.stopPropagation()">Click me</button>
</body>
```

<br>

##### However, Bubbling is convenient. Don’t stop it without a real need: obvious and architecturally well thought out.
<br>

## [Capturing]{.text-teal-300}

To catch an event on the capturing phase, we need to set the handler capture option to true:

<br>

```js
elem.addEventListener(..., {capture: true})

// or, just "true" is an alias to {capture: true}
elem.addEventListener(..., true)
```

---
class: text-sm
---

### [Event Delegation]{.text-teal-300}

The idea is that if we have a lot of elements handled in a similar way, then instead of assigning a handler to each of them – we put a single handler on their common ancestor.

- we attach one event listener to a parent to manage events on child elements.


```js
document.querySelector("#parent").addEventListener("click", function (event) {
  if (event.target.matches(".child")) {
    console.log("Child clicked:", event.target.textContent);
  }
});
```

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
hideInToc: true
class: text-sm
---

# [UI Events]{.text-teal-300}

UI (User Interface) Events are a subset of browser events related to user interaction with the web page or the browser window.

##### Examples:

- load
- resize
- scroll
- focus / blur

```js
window.addEventListener("resize", () => {
  console.log("Window was resized!");
});
```
