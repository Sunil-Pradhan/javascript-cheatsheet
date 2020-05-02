 <p align="center">
  <img width="256" height="256" src="/img/JavaScript_logo_large.png">
</p>

<h1 align="center">JavaScript Cheatsheet</h1>

<p align="center">
JavaScript is a dynamic interpreted language that powers the web. It is widely used in browsers and increasingly on servers. This document is a cheatsheet for JavaScript you will frequently encounter in modern projects and most contemporary sample code.
</p>


## Table of Contents

* [JavaScript Basics](#js-basics)
* [Data types](#js-datatypes)
* [Variables](#js-variables)
* [Complementary Resources](#com-res)


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
doStuff();  // Semicolons (;) to terminate lines
```

<a name="js-datatypes"></a>
## Data types

The latest ECMAScript standard defines eight data types:

* Number
* String
* Boolean
* Null
* Undefined
* Symbol 
* BigInt

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
var hello = 'world';
let bar = 'baz';
```

```javascript
// increment and decrement numbers
i++; // the equivalent of i = i + 1
i--; // the equivalent of i = i - 1;
```

<hr>

<a name="com-res"></a>
##### Complementary Resources

When you struggle to understand a concept, I suggest you look for answers on the following resources:


* [MDN (Mozilla Developer Network)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
* [ES6 Features with examples)](http://es6-features.org/#Constants)
* [Reddit (JavaScript))](https://www.reddit.com/r/javascript/)
* [StackOverflow](https://stackoverflow.com/questions/tagged/javascript)