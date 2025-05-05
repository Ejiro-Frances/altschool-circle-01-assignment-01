---
layout: center
transition: fade-out
---

# [Making API calls]{.text-teal-400}

---
class: text-sm
---

# [What is an API?]{.text-teal-400}

<br>

An API (Application Programming Interface) is a set of rules that allows different software entities to communicate.  
In web development, APIs enable your application to interact with external services. For example, fetching weather data, submitting forms, or retrieving user information.

<br>

## [Why Use APIs?]{.text-teal-400} 
<br>

- Access external data and services. {v-click}
- Enhance functionality without building from scratch. {v-click}
- Integrate with third-party platforms (e.g., payment gateways, social media). {v-click}

---
class: text-sm
---

# [Making API Calls in JavaScript]{.text-teal-400}

<br>

JavaScript provides several methods to make HTTP requests:

- `fetch()` API: Modern and promise-based. 
- Axios: A popular third-party library.

<br>

## [Using the fetch() API]{.text-teal-400} 

<br>

The `fetch()` function allows you to make network requests, return a promise, and handle HTTPS responses.

```js 
fetch('https://api.example.com/data')
  .then(response => response.json())
  .then(data => {
    console.log(data);
  })
  .catch(error => {
    console.error('Error:', error);
  });
```

---
class: text-sm
---

## [Handling Responses] {.text-teal-400}

<br>

After making a request, handle the response appropriately:

```js 
fetch('https://api.example.com/data')
  .then(response => {
    if (!response.ok) {
      throw new Error('Network response was not ok');
    }
    return response.json();
  })
  .then(data => {
    // Process the data
  })
  .catch(error => {
    // Handle errors
  });
```

- Check response.ok to ensure the request was successful. {v-click}

- Use .json() to parse the response body. {v-click}

---
class: text-sm
---

### [Making POST Requests]{.text-teal-400}

<br>
To send data to the server, use POST requests:

```js
fetch('https://api.example.com/data', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({ name: 'John', age: 30 })
})
  .then(response => response.json())
  .then(data => {
    console.log('Success:', data);
  })
  .catch(error => {
    console.error('Error:', error);
  });

```

- Set the method to 'POST'. {v-click}

- Include headers and body as needed. {v-click}

---
class: text-sm
---

### [Using Async/Await]{.text-teal-400}

<br>
Async/Await provides a cleaner syntax for handling Promises:

```js
async function fetchData() {
  try {
    const response = await fetch('https://api.example.com/data');
    if (!response.ok) {
      throw new Error('Network response was not ok');
    }
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.error('Error:', error);
  }
}

fetchData();
```

---
class: text-sm
---

# [Introducing Axios]{.text-teal-400}

<br>
Axios is a promise-based HTTP client that:

- Automatically transforms JSON data.

- Handles errors more gracefully. 
```js
import axios from 'axios';

axios.get('https://api.example.com/data')
  .then(response => {
    console.log(response.data);
  })
  .catch(error => {
    console.error('Error:', error);
  });
```

---
class: text-sm
---

### [Making POST Requests with Axios]{.text-teal-400}

<br>

Sending data using Axios simplifies HTTP requests with concise syntax.

```js
axios.post('https://api.example.com/data', {
  name: 'John',
  age: 30
})
  .then(response => {
    console.log('Success:', response.data);
  })
  .catch(error => {
    console.error('Error:', error);
  });
```

---
class: text-sm
---

### [Handling Errors]{.text-teal-400}

<br>

Always handle potential errors in API calls:

- Network Errors: When the request fails to reach the server. {

- HTTP Errors: When the server returns an error status code.

```js
fetch('https://api.example.com/data')
  .then(response => {
    if (!response.ok) {
      throw new Error(`HTTP error! status: ${response.status}`);
    }
    return response.json();
  })
  .catch(error => {
    console.error('Fetch error:', error);
  };
```

---
class: text-sm
---

## [Working with API Keys]{.text-teal-400}
<br>
Some APIs require authentication using API keys:
```js
fetch('https://api.example.com/data', {
  headers: {
    'Authorization': 'Bearer YOUR_API_KEY'
  }
})
  .then(response => response.json())
  .then(data => {
    console.log(data);
  });
```
