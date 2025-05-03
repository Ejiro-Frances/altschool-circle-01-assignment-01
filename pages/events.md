

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
