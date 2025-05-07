---
layout: center
transition: fade-out
scrollable: true
---

# [Forms]{.text-teal-400}

---
hideInToc: true
class: text-sm
---

# [Form]{.text-teal-400}

- Form Events: These are actions triggered by the user’s interaction with form elements (e.g., focus, blur, submit).

- Form Validation: Ensures that user input meets certain criteria before being submitted (e.g., required fields, proper email format).

- Form Submission: Handles the process of sending data to a server or database (either programmatically or through user interaction).


### [Focus & Blur Events]{.text-teal-400}

- Focus Event: Happens when the user clicks into an input field or navigates to it via the keyboard (e.g., pressing Tab).

- Purpose: Used for highlighting fields, validating inputs, or triggering real-time feedback as the user interacts with the form.

- Blur Event: Occurs when the user clicks or navigates away from the input field.

- Purpose: Often used to validate inputs after the user has finished interacting with a field. For example, checking if the email entered is valid when the user leaves the email field.

#### Example:

```html
<input type="email" id="email" onblur="validateEmail()" />
```

---
class: text-sm
---

### Contd:

```js
const emailInput = document.getElementById('email');

emailInput.addEventListener('focus', () => {
  console.log('User is typing their email...');
});

emailInput.addEventListener('blur', () => {
  validateEmail();
});
```

<br>

### Form Attribute

<span class="text-teal-300">Autofocus:</span> Automatically focuses on an input element when the page is loaded, making it user-friendly for forms that require immediate input

Example:

```html
<input type="text" id="name" autofocus>
```

```js
document.getElementById('name').focus(); // Automatically focuses input
```

---
class: text-sm
---

### [Form Submission Events & Methods]{.text-teal-300}


Submit Method: This method submits the form data to the server programmatically.

Use Case: When you want to submit a form without user interaction, such as submitting dynamically created forms.

Example:
document.forms['myForm'].submit();

Submit Event: This event is triggered when the form is submitted via a button click or pressing Enter inside a form field.

Purpose: Used for final validation before submission.

### [Real-Time Validation with Input and Change Events]{.text-teal-300}

Input Event: Fires every time the value of an input element changes (ideal for immediate validation like showing password strength).

Example:

```html
<input type="password" id="password" oninput="checkPasswordStrength()" />
```

This would trigger the checkPasswordStrength function as the user types.

Change Event: Triggered when the user finishes editing and moves away from the field.
