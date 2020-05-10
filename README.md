 <p align="center">
  <img width="256" height="256" src="/img/JavaScript_logo_large.png">
</p>

<h1 align="center">JavaScript Cheatsheet</h1>

<p align="center">
JavaScript is a dynamic interpreted language that powers the web. It is widely used in browsers and increasingly on servers. This document is a cheatsheet for JavaScript you will frequently encounter in modern projects and most contemporary sample code.
</p>

## Table of Contents

- [JavaScript Basics](#js-basics)
- [Data types](#js-datatypes)
- [Variables](#js-variables)
- [Branches and Loops](#js-branch-loops)
- [Complementary Resources](#com-res)

<a name="js-basics"></a>

## JavaScript Basics

Everything in JavaScript is an object.

##### Comments

Single line comments start with `//`. For multi-line commands, you use `/* ... */`.

```javascript
// This is a single line comment

/*
 And this is
 a multi-line
 comment
 */
```

##### Terminate statements

```javascript
doStuff(); // Semicolons (;) to terminate lines
```

<a name="js-datatypes"></a>

## Data types

The latest ECMAScript standard defines eight data types:

- Number
- String
- Boolean
- Null
- Undefined
- Symbol
- BigInt

<a name="js-variables"></a>

## Variables

In JavaScript, a variable is like a temporary location where you store your data for future retrieval.

There are 3 ways to create variables in JavaScript:

`var`, `let`, `const`

Variables created with `var` are in scope of the function (or global if declared in the global scope); `let` variables are block scoped; and `const` variables are like let plus their values cannot be re-assigned.

I recommend always declaring your variables with `const` by default, but with `let` if it is a variable that you need to reassign later.

 <table>
  <tr>
    <th></th>
    <th>Scope</th>
    <th>Reassignable</th>
    <th>Temporal Dead Zone</th>
  </tr>
  <tr>
    <th>const</th>
    <td>Block</td>
    <td>No</td>
    <td>Yes</td>
  </tr>
  <tr>
    <th>let</th>
    <td>Block</td>
    <td>Yes</td>
    <td>Yes</td>
  </tr>
   <tr>
    <th>var</th>
    <td>Function</td>
    <td>Yes</td>
    <td>No</td>
  </tr>
</table>

##### Sample code

```javascript
// This is how you define a variable
// `x` will be `undefined`
var x;

// Declare a constant (the convention is to use CAPS for constants)
const FOO = 42;

// Declare another two variables, using `var` and `let`
var hello = "world";
let bar = "baz";
```

```javascript
// increment and decrement numbers
i++; // the equivalent of i = i + 1
i--; // the equivalent of i = i - 1;
```

<hr>

<a name="js-branch-loops"></a>

## Branches and Loops

### Branching Out:

#### if statement

It is used to execute an instruction or block of instructions only if a condition is fulfilled i.e True.

Syntax:

```javascript
if (condition) {
  // Statements to execute if
  // condition is true
}
```

Example:

![js-if-statement](/img/js-if-statement.png)

#### if...else statement

if...else statement is used when a different sequence of instructions is to be executed depending on the logical value(True/False) of the conditions evaluated.

Syntax:

```javascript
if (condition) {
  // Executes this block if
  // condition is true
} else {
  // Executes this block if
  // condition is false
}
```

Example:

![js-if-else-statement](/img/js-if-else-statement.png)

#### Nested if statement

Embedding if statement inside another if statement is called JavaScript nested if statement. Here, else statement allows you to print different statements depending upon the expression result (true, false).

Syntax:

```javascript
if (condition1) {
  // Executes when condition1 is true
  if (condition2) {
    // Executes when condition2 is true
  }
}
```

Example:

![js-nested-if-statement](/img/js-nested-if-statement.png)

#### if-else-if ladder or else...if statement

Use else if to specify a new condition to test, if the first condition is false.

Syntax:

```javascript
if (condition_1) {
  statement_1_block;
} else if (condition_2) {
  statement_2_block;
} else if (condition_n) {
  statement_n_block;
}
.
.
.
else statment;
```

First check if statement condition 1, if it's not true then go to condition 2 and check. Still it’s not true then go to condition 3 and so on, until you are not getting any true value, otherwise show the else statement.

Example:

![js-if-else-if statement](/img/js-if-else-if%20statement.png)


<hr>

<a name="com-res"></a>

##### Complementary Resources

When you struggle to understand a concept, I suggest you look for answers on the following resources:

- [MDN (Mozilla Developer Network)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
- [ES6 Features with examples)](http://es6-features.org/#Constants)
- [Reddit (JavaScript)](https://www.reddit.com/r/javascript/)
- [StackOverflow](https://stackoverflow.com/questions/tagged/javascript)
