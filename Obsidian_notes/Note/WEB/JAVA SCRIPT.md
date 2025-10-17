

---

##  1. Introduction to JavaScript

**JavaScript** is a **client-side scripting language** designed to make web pages **interactive** and **dynamic**. While **HTML** defines the structure of a page and **CSS** defines its style, JavaScript brings the page to life through interactivity.

It executes directly inside the **browser**—meaning no server is required for it to run. This makes it an essential part of modern web development.

###  Why JavaScript?

- **Adds interactivity** (buttons, forms, sliders).
    
- **Validates user inputs** before sending data to the server.
    
- **Manipulates HTML and CSS dynamically.**
    
- **Responds to user actions** like clicks, keystrokes, and mouse movement.
    

Example of basic integration:

```html
<button onclick="alert('Hello!')">Click Me</button>
```

When you click the button, the alert box is shown — illustrating how JavaScript adds dynamic behavior to static pages.

---

##  2. JavaScript and Scripting Languages

JavaScript is a **scripting language**, meaning its code is **interpreted** line-by-line by the browser rather than compiled beforehand.

###  Characteristics:

- **Lightweight and fast** — no compilation step.
    
- **Case-sensitive** — `Name` and `name` are different.
    
- **Object-oriented** — uses objects, arrays, and functions.
    
- **Event-driven** — responds to user-triggered events.
    
- **Cross-platform** — works across browsers (Chrome, Edge, Firefox, Safari).
    

###  Difference Between Scripting and Programming:

| Feature   | Scripting Language | Programming Language      |
| --------- | ------------------ | ------------------------- |
| Execution | Interpreted        | Compiled                  |
| Speed     | Slower             | Faster                    |
| Example   | JavaScript, Python | C, Java                   |
| Use       | Web automation     | System or app development |

---

##  3. Ways to Add JavaScript to a Web Page

1. **Inline JavaScript**
    
    ```html
    <button onclick="alert('Hello!')">Click</button>
    ```
    
2. **Internal JavaScript**  
    Defined within the `<script>` tag in the HTML document.
    
    ```html
    <script>
      function greet() {
        alert('Welcome!');
      }
    </script>
    ```
    
3. **External JavaScript**  
    Linked using the `<script src="file.js"></script>` tag. This promotes modularity and reuse across multiple pages.
    

###  Best Practice:

- Use **external scripts** for scalability.
    
- Place scripts at the **end of the `<body>`** so HTML loads first.
    

---

##  4. Variables and Scope

Variables store data that can be reused and modified.

### Declaration Types:

```js
var name = "John"; // function-scoped
let age = 25;      // block-scoped
const PI = 3.14;   // constant
```

- **var** → old syntax; can be redeclared.
    
- **let** → used when values change.
    
- **const** → immutable; must be initialized.
    

### Example:

```js
let x = 10;
x = 20; // valid
const y = 30;
y = 40; // ❌ error
```

---

##  5. Data Types and Type Conversion

JavaScript is **dynamically typed** — you don’t need to declare variable types.

| Data Type | Example                   |
| --------- | ------------------------- |
| String    | "Hello"                   |
| Number    | 10, 3.14                  |
| Boolean   | true, false               |
| Object    | {name:"Ravi"}             |
| Array     | [10, 20, 30]              |
| Null      | empty value               |
| Undefined | declared but not assigned |

###  Type Conversion

| Method         | Description               | Example         |
| -------------- | ------------------------- | --------------- |
| `Number()`     | Converts string to number | `"42"` → 42     |
| `parseInt()`   | Integer conversion        | `"42.5"` → 42   |
| `parseFloat()` | Decimal conversion        | `"42.5"` → 42.5 |
| `+` Unary      | Quick numeric conversion  | `+"10"` → 10    |

---

##  6. Operators and Control Structures

### Arithmetic Operators

`+`, `-`, `*`, `/`, `%`

### Comparison

`==`, `===`, `!=`, `<`, `>`, `<=`, `>=`

### Logical

`&&` (AND), `||` (OR), `!` (NOT)

### Conditional Example:

```js
let age = 18;
if (age >= 18) console.log("Adult");
else console.log("Minor");
```

### Loops

#### For Loop

```js
for(let i=1;i<=5;i++){console.log(i);}
```

#### While Loop

```js
let i=1;
while(i<=5){console.log(i);i++;}
```

Example — Even numbers between 1 and 20:

```js
let i=1;
while(i<=20){
  if(i%2===0) console.log(i);
  i++;
}
```

---

##  7. User Input and Validation

`prompt()` is used for user input, and `alert()` or `document.write()` displays output.

Example: Add two numbers

```html
<script>
let num1 = Number(prompt("Enter first:"));
let num2 = Number(prompt("Enter second:"));
let sum = num1 + num2;
alert("Sum = " + sum);
</script>
```

Example: Check Even or Odd

```js
let num = Number(prompt("Enter number:"));
if(num % 2 === 0) alert("Even");
else alert("Odd");
```

---

##  8. Functions

Functions organize code into reusable blocks.

### Declaration:

```js
function greet(name){ return "Hello, " + name; }
```

### Expression:

```js
let add = function(a,b){ return a+b; };
```

### Arrow Function:

```js
const square = n => n*n;
```

### Return Example:

```js
function isEven(num){ return num%2===0; }
console.log(isEven(4)); // true
```

Functions can also take user input and return results dynamically.

---

##  9. Arrays

Arrays store multiple values in a single variable.

```js
let fruits = ["Apple", "Banana", "Mango"];
console.log(fruits[0]); // Apple
```

### Common Methods:

- `push()` → add end
    
- `pop()` → remove end
    
- `unshift()` → add start
    
- `shift()` → remove start
    
- `includes()` → check existence
    
- `concat()` → merge arrays
    
- `reverse()` → reverse order
    
- `sort()` → sort array
    

### Iteration:

```js
let colors = ["Red", "Green", "Blue"];
colors.forEach(c => console.log(c));
```

---

##  10. Objects

Objects store data in **key–value pairs**.

```js
let student = { name: "Rahul", rollNo: 101, marks: 85 };
console.log(student.name);
```

### Updating and Adding:

```js
student.grade = "A"; // add
student.marks = 90;  // update
```

### ES6 Classes:

```js
class Car {
  constructor(brand, model){ this.brand = brand; this.model = model; }
  start(){ console.log(this.brand + " starting..."); }
}
let c1 = new Car("Toyota", "Camry");
c1.start();
```

---

##  11. Built-in JavaScript Objects

JavaScript provides built-in objects for common tasks.

###  Core Objects:

| Object     | Purpose              | Example                              |
| ---------- | -------------------- | ------------------------------------ |
| `Object`   | Base of all objects  | `const obj = {};`                    |
| `Function` | Function creation    | `new Function('a','b','return a+b')` |
| `Boolean`  | Wrapper for booleans | `new Boolean(true)`                  |
| `Symbol`   | Unique identifiers   | `Symbol('id')`                       |
| `Error`    | Error handling       | `throw new Error("Oops!")`           |

###  Date

```js
let d = new Date();
console.log(d.getFullYear());
```

### Math

```js
Math.sqrt(16); // 4
Math.random(); // random number
Math.max(10,20,30); // 30
```

### String

```js
let s = "Hello";
console.log(s.toUpperCase());
console.log(s.includes("He"));
```

###  Array

Methods like `.map()`, `.filter()`, `.reduce()` enable functional programming.

###  Map and Set

- **Map** stores key-value pairs.
    
- **Set** stores unique values.
    

---

##  12. JavaScript Debugging

Debugging helps identify and fix code errors.

### Tools:

- `console.log()` — print messages
    
- `console.error()` — show errors
    
- `console.table()` — print tables
    
- `debugger` statement — pauses code
    
- **Browser DevTools** — inspect variables, set breakpoints, view call stack
    
- **VS Code Debugger** — integrated environment
    
- **ESLint** — linter that detects code issues before runtime
    

Example:

```js
let x = 10, y = 5;
let sum = x + y;
debugger; // execution pauses here
console.log(sum);
```

---

##  13. Document Object Model (DOM)

DOM represents the structure of an HTML page as a **tree of objects** that JavaScript can manipulate.

### Structure:

```html
<html>
 <head><title>My Page</title></head>
 <body><h1>Hello</h1><p>Paragraph</p></body>
</html>
```

Becomes:

```
Document
 └─ html
     ├─ head
     │   └─ title
     └─ body
         ├─ h1
         └─ p
```

### Relationships:

- **Parent:** contains other nodes.
    
- **Child:** inside another node.
    
- **Sibling:** share same parent.
    

---

##  14. DOM Event Handling

**Events** are user actions (clicks, key presses, mouse movement). JavaScript reacts through event handlers.

### Types of Handling:

| Method      | Syntax                       | Multiple Handlers | Recommended |
| ----------- | ---------------------------- | ----------------- | ----------- |
| Inline      | `onclick="func()"`           | ❌                 | No          |
| DOM Level 0 | `element.onclick = func`     | ❌                 | Limited     |
| DOM Level 2 | `element.addEventListener()` | ✅                 | ✅ Yes       |

### Example — `addEventListener`

```html
<button id="btn">Click</button>
<script>
document.getElementById("btn")
.addEventListener("click", ()=>alert("Clicked!"));
</script>
```

### Multiple Events:

```js
btn.addEventListener("click", ()=>alert("Clicked!"));
btn.addEventListener("mouseover", ()=>console.log("Hovered!"));
```

### Event Object:

```js
btn.addEventListener("click", function(event){
 console.log(event.type);
 console.log(event.target);
});
```

---

##  15. Form Validation Example

```html
<form id="myForm">
  <input id="name" type="text" placeholder="Enter name">
  <button type="submit">Submit</button>
</form>

<script>
document.getElementById("myForm").addEventListener("submit", function(event){
  let name = document.getElementById("name").value;
  if(name === ""){
    alert("Please enter your name!");
    event.preventDefault();
  } else {
    alert("Form submitted successfully!");
  }
});
</script>
```

This example shows how **event.preventDefault()** stops form submission until validation passes.

---

##  16. Real-Life Examples

### Change Background Color

```html
<button onclick="changeColor()">Change Color</button>
<script>
function changeColor(){
  let colors = ["pink","yellow","skyblue","lightgreen"];
  let i = Math.floor(Math.random()*colors.length);
  document.body.style.backgroundColor = colors[i];
}
</script>
```

### Multiplication Table

```js
let n = 5;
for(let i=1;i<=10;i++){
  console.log(`${n} x ${i} = ${n*i}`);
}
```

### Largest of Three Numbers

```js
let a=10,b=20,c=15;
let largest = (a>b && a>c)? a : (b>c? b : c);
console.log("Largest:", largest);
```

---

##  Final Insight

JavaScript is not just a scripting language — it’s the **foundation of modern web interactivity**. This unit prepares you to:

- Build **dynamic web pages**.
    
- Handle **user inputs and validations**.
    
- Write **modular and reusable** functions.
    
- Create and manipulate **arrays and objects**.
    
- Use **debugging tools** for efficient development.
    
- Control **DOM elements and browser events**.
    
