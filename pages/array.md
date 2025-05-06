--- 
layout: center
transition: fade-out
---

# [Array]{.text-teal-400}

<v-click>Understanding arrays in JavaScript</v-click>

---
class: text-sm
---

## [What is an Array?]{.text-teal-400}
In JavaScript, an **array** is a special variable that can hold more than one value at a time. These values can be of any data type, including numbers, strings, and even other arrays.

You can think of an array as a data structure that stores list of items. Instead of creating seperate variables for each items:

```js
let item1 = "Pen" ;
let item2 = "Book";
let item3 = "Ruler";
```

You can just do this instead:

```js
let items = ["Pen", "Book", "Ruler"];👍
let again=1;
```

It's like a container that stores values in a specific order.

---
class: text-sm
---

## [Why Use Array?]{.text-teal-400}

<p></p>

+ To group related data
- To loop through data easily
+ To manage list (e.g. a list of users, scores, products)


Imagine trying to store 1000 scores without an array 😫

---
class: text-sm
---

## [Array Declaration]{.text-teal-300}

There are two syntaxes to create an empty array namely sqauare bracket notation [] and Array Constructor.

#### [Array Literal (Square Bracket Notation)]{.text-teal-300}

```js
let arr = []; //this is an empty array

let myArr = ["Apple", "Orange", "Pear"];

```

<v-click>
<h1></h1>

#### [Array Constructor]{.text-teal-300} 

```js
let arr = new Array(); //this is an empty array

let myArr = new Array("Apple", "Orange", "Pear")
```

The array literal ```[]``` is the most commonly used syntax.

</v-click>

<div v-click class="text-xl">

⚠️ ***Warning***

Note: Using the literal from ```[]``` is preferred because it is simpler and less error-prone.

</div>

---
class: text-sm
---

## [Accessing Array Elements]{.text-teal-400}

In JavaScript, array elements are indexed starting from zero, meaning the first element has an index of 0, the second 1, and so on.
To access a specific element in an array, use square brackets ([]) with the index number of the element you want.

```js
let fruits = ["Apple", "Orange", "Pear"];
console.log(fruits[0]); // Output: Apple
console.log(fruits[2]); // Output: Pear
```
You can modify the elements in an array by assigning the value of a specific index.

***Example***: Let's modify the first index ```Apple``` to ```Banana```

```js
fruits[0] = "Banana"

console.log(fruits[0]); // Output: Apple

console.log(fruits); // Output: ["Banana", "Orange", "Pear"]

```
---
class: text-sm
---

- **Array Length**

The ```.length``` property of an array returns the total number of elements in the array. 

```js
let fruits = ["Apple", "Orange", "Pear"];
console.log(fruits.length); // Output: 3

```
<p></p>

### [Array Methods]{.text-teal-300}

Array methods are built in functions in JavaScript that allow you to manipulate and interact with data stored in arrays easily.
You can use them to add, remove, modify, rearrange or search array elements.

Some commonly used array methods are:
 
**push()** - Adds elements to the end of an array

```js
let fruits = ["Apple", "Orange", "Pear"];
fruits.push("Strawberry");

console.log(fruits);

// Output: ["Apple", "Orange", "Pear", "Strawberry"]
```
---
class: text-sm
---

### [Array Method Contd.]{.text-teal-300}

<div class="grid grid-cols-2 gap-4">

<div>

**pop()** - Removes the last elements from an array

```js
fruits.pop(); // Output: "Strawberry"
console.log(fruits);
// Output: ["Apple", "Orange", "Pear"]
```

**shift()** - Removes the first elements from an array

```js
fruits.shift(); // Output: "Apple"
console.log(fruits);
// Output: ["Orange", "Pear"]
```


**unshift()** - Adds elements to the beginning of an array

```js
fruits.unshift("Strawberry", "Banana");

console.log(fruits);

// Output: ["Strawberry", "Banana", "Orange", "Pear"]

```
</div>

<div>

**slice()** - Returns selected elements in an array as a new array

```js
const newFruits = fruits.slice(0, 2);

console.log(newFruits);

// Output: ["Strawberry", "Banana"]

```

**reverse()** - Reverses the order of the elements in an array

```js
fruits. reverse()

onsole.log(fruits);

// Output: ["Pear", "Orange" "Banana", "Strawberry"]

```

</div>

</div>

---
hideInToc: true
class: text-sm
---

# [Objects]{.text-teal-300}

Objects are data types used to store data in **key: value pair**. It is used to group  related data in a single variable.

```js
 let user = {
  name: "Zara",
  age: 35,
  isAdmin: true,
 }
```

Each ```key``` is also called a property, and it is associated value can be any data type: string, number, array, function etc.

#### Objects can be created in two ways:

<br>

1. Using Object Literals
```js
// Using object literal
 let user = {}

```
2. Object Constructor
```js
//Using Object Constructor
 let user = new Object()

```
---
class: text-sm
---

### [Acessing Object Properties]{.text-teal-300}

To access the property of an object, you can use **dot notation** or **bracket notation**. Dot notation is the most common way to access object property.

```js
//Using Dot Notation

console.log(user.name);
// output : "Zara"

```
```js
//Using Bracket Notation

console.log(user["user"]);
// output : "Zara"
```

Bracket notation is useful when you want to access a property name stored in a variable.
```js
const key = "age";

console.log(user[key]);

// output : "Zara"
```
---
class: text-sm
---

You can add, remove or modify object anytime.

```js
user.age = 30; // modify the age property
user.location = "Lagos"; // add new property and value
delete user.isAdmin // delete the property
console.log(user);

//output: {name: "Zara", age: 30, location: "Lagos}
```

Objects can also contain functions, which are called **methods**. <span class= "bg-black text-cyan-400 rounded-sm py-1 px-1.5"> Object methods are actions that can be performed on objects.</span>

```js
 let person ={
  firstName: "Zara",
  lastName: "Joel",
  age: 15,
  greet: function() {
    console.log("Hello, my name is " + this.firstName + " " + this.lastName)
  }
 }
 person.greet(); // output: Hello, my name is Zara Joel
```

```this``` keyword in this example refers to the ```person``` object
