---
layout: center
transition: fade
---

# [DOM]{.text-teal-400}

---
class: text-sm
---

### [DOM(Document Object Model) manipulation]{.teal-teal-300}

DOM manipulation involves dynamically changing the structure, layout, or content of a web page using programming languages like JavaScript. Some common DOM manipulation techniques includes:

<h2 class= "text-teal-300" >Adding or removing elements.</h2>

Adding elements.*document.createElement(): creates a new element *appendChild(): adds a new element to the end of a parent element *insertBefore(): adds a new element before a specified element.

Example: Adding a new list item
const list=
document.getElementById('myList');
const newItem=
document.createElement('li')
newItem.textContext= 'New item';
list.appendChild(newitem);

# [Removing elements.]{.text-teal-300}

*removeChild() :removes a child element from a parent element.
*remove(): removes an element directly.

Example: Removing a list item
constlist=
document.getElementById('myList');
const itemToRemove=
list.children[0];
list.removeChild(itemtoremove);

---
class: text-sm
hideInToc: true
---

<h3 class= "text-teal-300">DOM TREE.</h3>
<div class= "f-[10px]">
This is a hierarchical representation of an HTML document's structure. It consists of nodes, which can be:
* Elements(e.g. html, body, div)
* Attributes(e.g. id, class, src)
* Text nodes(e.g. text content within elements)

DOM Tree Manipulation
This involves dynamically changing the structure or content of the DOM tree. This can be done using various methods:
1. Creating elements: Using 
document.createElement() to create new elements
2. Adding elements: Using appendChild() or insertBefore() to add new elements to the DOM tree.
3. Removing elements: Using removeChild() or remove() to remove elements.
4. Modifying elements: Using properties like textContent, innerHTML, and setAttribute() to modify content or attributes.

Example:
Suppose we want to build a simple todo list that allows users to:
* Add new todo items
* Mark todo items as completed
* Delete todo items
</div>

HTML STRUCTURE
```html
<ul id=="todo-list></ul>
<input id="todo-input"type="text"placeholder="Add new todo">
<button id="add-todo-btn">Add</button>
```

---
class: text-sm
hideInToc: true
---

## [JAVASCRIPT STRUCTURE]{.text-teal-300}

```js
const todoList= document.getElementById('todo-list');
const todoInput= document.getElementById('todo-input');
const addTodoBtn= document.getElementById('add-addTodo-Btn');

addTodoBtn.addEventListener('click', addToDo);

function addTodo(){
const newToDo= document.createElement('li');
newToDO.textContent=todoInput.value;
constmdeleteBtn.textContent= 'Delete'
newToDo.appendChild(deleteBtn);

// addEventListener for delete button
deleteBtn.addEventListener('click',()=>{newToDo.remove();
});


//addEventListener for marking todo as completed
newToDO.addEventListener('click',()=>{newToDO.classList.toggle('completed');
})

todoList.appendChild(newToDO);
todoInput.value=";
}
```

---
class: text-sm
hideInToc: true
---

## [The Browser Object Model(BOM)]{.text-teal-300}
This is a programming interface for interacting with the browser. It provides access to browser specific functionality and properties. It involves the following:

1. Windows: This is the browser window
2. Navigator: It provides information about the browser and its capabilities.
3. Location: It represents the current URL and allows navigation
4. History: It provides access to the browser's history.

Examples:

* Getting the current URL
console.log(window.location.href);

* To open a new window
window.open('https;//www.example.com',_blank');

* To get the browser's user agent
console.log(navigator.userAgent);