# Basics of JavaScript (Foundations)
**Goal:** Understand JS syntax, data types, and control structures.

## 1. What is JavaScript?
JavaScript is a `Programming language`. It is a `single-threaded` and `synchronous by nature`, but it handles asynchronous tasks using event loops and constructs like promises and async/await.

- A `programming language` is a set of rules, symbols, and syntax used to write instructions that a computer can understand and execute. It's how humans communicate with computers to create software, websites, games, apps, and more.
  Think of it like:
    - English (or any spoken language) = how humans talk to each other.
    - Programming language = how humans talk to computers.

- `Single-threaded` means, a program or process can only do one task at a time on a single thread of execution.
  - What is a "thread"?
    A thread is the smallest sequence of instructions that can be managed independently by a scheduler (usually part of the operating system). Think of it like a to-do list where the computer does one thing after another.

- JavaScript is `synchronous by nature`, meaning it executes one line at a time in the order it's written. But — and here's the key — if a statement involves an asynchronous operation (like setTimeout, fetch, or reading a file in Node.js), JavaScript doesn't wait for it to finish. Instead, it delegates it and moves on to the next line.


## 2. Variables (let, const, var)
### I. What is a variable?
A variable is like a box where you can store a value (like a number or string), and give that box a name so you can use it later.

### II. JavaScript has 3 main ways to declare variables:
#### 1. `let` – block-scoped, can be changed
- Introduced in ES6 (2015)
- Block-scoped: only exists inside { }
- Can be updated (reassigned), but not re-declared in the same block

**Example:**
```js
let age = 25;
age = 26; // ✅ okay to change
```

#### 2. `const` – block-scoped, cannot be changed
- Also introduced in ES6
- Block-scoped
- Must be assigned a value immediately
- Cannot be reassigned

**Example:**
```js
const name = "Alice";
name = "Bob"; // ❌ Error! Cannot reassign a const
```

- If the value is an object or array, the contents can be changed, but not the reference:

**Example:**
```js
const user = { name: "Alice" };
user.name = "Bob"; // ✅ allowed
user = {}; // ❌ not allowed
```

#### 3. `var` – function-scoped, can be changed and re-declared
- The old way (before ES6)
- Function-scoped, not block-scoped
- Can be re-declared and reassigned
- Can cause confusion due to hoisting

**Example:**
```js
var city = "Paris";
var city = "London"; // ✅ allowed
city = "Rome"; // ✅ also allowed
```

### III. Summary Table
| Keyword	| Scope	    | Reassign?	| Re-declare?	| Introduced In |
|---------|-----------|-----------|-------------|---------------|
| var	    | Function	| ✅ Yes	  | ✅ Yes	    | Old JS        |
| let	    | Block	    | ✅ Yes	  | ❌ No	      | ES6 (2015)    |
| const	  | Block	    | ❌ No	  | ❌ No	      | ES6 (2015)    |

### IV.  Best Practices
- Use **const** by default.
- Use **let** if the value will change.
- Avoid **var** unless you really know what you're doing.

## 3. Data Types (string, number, boolean, null, undefined, object, array)
Data Types are the different kinds of values you can work with in your code.

### I. Types of Data Types
#### 1. Primitive Data Types
These are the basic building blocks. They store single values.

##### a. `string` – Text
```js
let name = "Alice";
let greeting = 'Hello!';
let sentence = `Hi, ${name}!`; // Template literal
```
- Text inside quotes (single `'`, double `"`, or backticks <code>`</code>)
- Use + or template strings to combine
```js
let fullName = "John" + " " + "Doe";  // John Doe
```

##### b. `number` – Numbers (integers & decimals)
```js
let age = 25;
let price = 19.99;
```
- No separate type for int or float — just `number`
- Supports math: `+`, `-`, `*`, `/`, `%`, etc.

##### c. `boolean` – True or False
```js
let isLoggedIn = true;
let isAdmin = false;
```
- Used for conditions, like:
```js
if (isLoggedIn) {
  console.log("Welcome back!");
}
```

##### d. `null` – Intentionally empty
```js
let middleName = null;
```
- Means "nothing here on _purpose_"
- You set it to null when something is intentionally empty or unknown

##### e. `undefined` – Not assigned
```js
let username;
console.log(username); // undefined
```
- A variable declared but not given a value is undefined
- Also returned by functions with no return:

```js
function test() {}
console.log(test()); // undefined
```

##### f. `symbol` – Unique identifier (advanced)
```js
let id = Symbol("id");
```
- Not often used by beginners
- Used to create unique values for object properties

#### 2. Non-Primitive (Reference) Data Types
These can store collections of values.

##### g. `object` – Key-value pairs
```js
let person = {
  name: "Alice",
  age: 30,
  isStudent: false
};
console.log(person.name); // Alice
```
- Use {} to define an object
- Access values with . or []
- Can hold any data type inside

##### h. `array` – Ordered list
```js
let colors = ["red", "green", "blue"];
console.log(colors[0]); // red
```
- Use [] for arrays
- Index starts at 0
- Can mix types:
```js
let random = \[1, "hello", true];
```
- Has built-in methods like .push(), .pop(), .length, .map(), etc.

### II. `typeof` Operator
You can check the data type using typeof:

```js
typeof "hello"     // "string"
typeof 123         // "number"
typeof true        // "boolean"
typeof null        // 🤯 "object" (weird JS quirk!)
typeof undefined   // "undefined"
typeof [1,2,3]     // "object"
typeof {a:1}       // "object"
```

### III. Quick Summary Table

| Type      | Example           | typeof      |
|-----------|-------------------|-------------|
| string    | `"hello"`         | `"string"`  |
| number    | `123`, `3.14`     | `"number"`  |
| boolean   | `true`, `false`   | `"boolean"` |
| null      | `null`            | `"object"`* |
| undefined | `let x;`          |`"undefined"`|
| object    | `{name: "Bob"}`   | `"object"`  |
| array     | `[1, 2, 3]`       | `"object"`  |
| symbol    | `Symbol("id")`    | `"symbol"`  |

> *Yes, typeof null returning "object" is a known bug from early JavaScript days.


## 4. Operators (arithmetic, comparison, logical)
### I. Let's break down JavaScript Operators into 3 key types
  - `Arithmetic`, `Comparison`, and `Logical`. These are core tools for writing conditions, doing math, and making decisions in code.

#### 1. Arithmetic Operators (Math stuff)
These are used to perform mathematical operations.

| Operator | Description | Example | Result |
|----------|-------------|---------|--------|
| `+` | Addition | `5 + 2` | `7` |
| `-` | Subtraction | `5 - 2` | `3` |
| `*` | Multiplication | `5 * 2` | `10` |
| `/` | Division | `10 / 2` | `5` |
| `%` | Modulus (Remainder) | `10 % 3` | `1` |
| `**` | Exponentiation | `2 ** 3` | `8` |
| `++` | Increment | `x++` or `++x` | `x = x + 1` |
| `--` | Decrement | `x--` or `--x` | `x = x - 1` |

Example:
```js
let x = 10;
console.log(x + 5); // 15
console.log(x % 3); // 1
```

#### 2. Comparison Operators
Used to compare values. Returns true or false.

| Operator | Description | Example | Result |
|----------|-------------|---------|--------|
| `==` | Equal (loose) | `5 == "5"` | `true` |
| `===` | Equal (strict, type+value) | `5 === "5"` | `false` |
| `!=` | Not equal (loose) | `5 != "5"` | `false` |
| `!==` | Not equal (strict) | `5 !== "5"` | `true` |
| `>` | Greater than | `10 > 5` | `true` |
| `<` | Less than | `10 < 5` | `false` |
| `>=` | Greater than or equal to | `10 >= 10` | `true` |
| `<=` | Less than or equal to | `5 <= 5` | `true` |

Example:
```js
console.log(5 == "5");  // true  (loose equality)
console.log(5 === "5"); // false (strict equality)
console.log(10 > 7);    // true
```
> Tip: Always prefer `===` and `!==` in modern JavaScript to avoid unexpected type coercion.

#### 3. Logical Operators
Used to combine multiple conditions or logic checks.

| Operator   | Name | Description                 | Example         | Result |
|------|-----|----------------------------------|-----------------|---------|
| `&&` | AND | True if both conditions are true | `true && false` | `false` |
| `\|\|` | OR  | True if at least one is true     | `true \|\| false` | `true`  |
| `!`  | NOT | Reverses true/false              | `!true`         | `false` |

Example:
```js
let isLoggedIn = true;
let isAdmin = false;

if (isLoggedIn && isAdmin) {
  console.log("Show admin panel");
} else {
  console.log("Access denied");
}
```

### II. Quick Summary
- Arithmetic = Do math (`+`, `-`, `*`, etc.)
- Comparison = Check relationships (`===`, `>`, `!=`)
- Logical = Combine booleans (`&&`, `||`, `!`)



## 5. Conditional Statements (if, else, switch)

## 6. Loops (for, for...of, for...in, while & do..while)
### i. for...i
```javascript title="JavaScript"
let namesList = ["Apple", "Mango", "Banana", "Grapes", "Orange"];

for (let i=0; i<namesList.length; i++) {
    console.log(namesList[i]);
}
```

### ii. for...of (of will return values one by one)
```javascript title="JavaScript"
let namesList = ["Apple", "Mango", "Banana", "Grapes", "Orange"];

for (let i of namesList) {
    console.log(i);
}
```

### iii. for...in (in will return keys or index numbers one by one)
```javascript title="JavaScript"
let namesObject = { fruit_1:"Apple", fruit_2:"Mango", fruit_3:"Banana", fruit_4:"Grapes", fruit_5:"Orange"};

for (let i in namesObject) {
    console.log(namesObject[i]);
}
```

### iv. while loop - (Condition Checked: Before executing the loop)
```javascript title="JavaScript"
let i = 10;

while (i < 5) {
    console.log("while loop");
}
```
**Explanation:**
- let i = 0 → initialize counter
- while (i < namesList.length) → loop runs until condition becomes false
- console.log(namesList[i]) → prints each value
- i++ → increments index to avoid infinite loop

### iv. d0..while loop (Condition Checked: After executing the loop - runs at least once)
```javascript title="JavaScript"
let i = 10;

do {
    console.log("do...while loop");
} while (i < 5);
```
**Explanation:**
- do block runs at least once, even if the condition is false.
- After executing the block, it checks the condition while (i < namesList.length).
- If true, the loop continues.

## 7. Functions (declaration, expressions, arrow functions)

## 8. Error handling (try...catch)

