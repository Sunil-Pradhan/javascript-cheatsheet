 <p align="center">
  <img width="256" height="256" src="/img/JavaScript_logo_large.png">
</p>

<h1 align="center">JavaScript Cheatsheet</h1>

<p align="center">
JavaScript is a dynamic interpreted language that powers the web. It is widely used in browsers and increasingly on servers. This document is a cheatsheet for JavaScript you will frequently encounter in modern projects and most contemporary sample code.
</p>

## Table of Contents

- [JavaScript Basics](#js-basics)
- [Variables](#js-variables)
- [Data types](#js-datatypes)
- [Operators](#js-operators)
- [Branches and Loops](#js-branch-loops)
- [Function](#js-function)
- [Object](#js-object)
- [Array](#js-arrays)
- [String](#js-string)
- [Number](#js-number)
- [Prototype](#js-prototype)
- [this keyword](#js-this)
- [Composition or Mixins](#js-mixins)
- [Class](#js-class)
- [Variable Hoisting](#js-variable-hosting)
- [Rest & Spread Operator](#js-rest-spread)
- [Module - Import & Export](#js-module)
- [Destructuring - Array & Object](#js-destructuring)
- [Symbols](#js-symbols)
- [Generators](#js-generators)
- [Sets & Maps](#js-sets-maps)
- [Map method](#js-map-method)
- [JavaScript Promises](#js-promises)
- [JavaScript Async/Await](#js-async-await)
- [Object Oriented Programming - OOP](#js-oop)
- [Document Object Model - DOM](#js-dom)
- [Complementary Resources](#com-res)

<a name="js-basics"></a>

## JavaScript Basics

Everything in JavaScript is an object.

### JavaScript comments

Single line comments start with `//`. For multi-line commands, you use `/* ... */`.

```javascript
// This is a single line comment

/*
 And this is
 a multi-line
 comment
 */
```

### JavaScript expression

A fragment of code that produces a value is called an expression.

```javascript
5 * 10; //5 * 10 evaluates to 50

x * 10; //expressions can also contain variable values
```

### JavaScript statement

A JavaScript program is a list of instructions to be executed by a computer and these programming instructions are called statements.

```javascript
var x, y, z; //statement 1
x = 5; //statement 2
y = 6; //statement 3
z = x + y; //statement 4
```

If an expression corresponds to a sentence fragment, a JavaScript statement corresponds to a full sentence in a human language.

### Terminate statements in JavaScript

```javascript
doStuff(); // Semicolons (;) to terminate lines
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

<a name="js-variables"></a>

## Variables

In JavaScript, a variable is like a temporary location where you store your data for future retrieval.

There are 3 ways to create variables in JavaScript:

`var`, `let`, `const`

Variables created with `var` are in scope of the function (or global if declared in the global scope); `let` variables are block scoped; and `const` variables are like let plus their values cannot be re-assigned.

I recommend always declaring your variables with `const` by default, but with `let` if it is a variable that you need to reassign later.

![js-variables-let-const-var](/img/js-variables-let-const-var.png)

:bulb: **TIP:** The **Temporal Dead Zone(TDZ)** is never named explicitly in the ECMAScript specification, but the term is often used to describe why `let` and `const` bindings are not accessible before their declaration.

<br>

**Variable declaration:**

```javascript
// This is how you define a variable
// x will be undefined
var x;

// Declare a constant (the convention is to use CAPS for constants)
const PI = 3.14;

// Declare another two variables, using var and let
var firstName = 'Sunil';
let lastName = 'Pradhan';
```

**Re-declaring a JavaScript variable:**

If you re-declare a JavaScript variable, it will not lose its value.

```javascript
var x = 4;
var x;
console.log(x);

//output - 4
```

:bulb: **TIP:** JavaScript statements are executed, one by one, in the same order as they are written.

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

<a name="js-datatypes"></a>

## Data types

### Type of data:

In JavaScript two types of data type available:

- Primitive
- Reference or derived type

**What is the difference between both of them?**

Primitive data types are base data types whereas reference data types are derived.

:bulb: **TIP:** Memory allocation in **primitive data types** happens in **“Stack”** whereas memory allocation in **Reference data types** happens in **“Heap”** (Dynamic memory).

<br>
<br>

The latest ECMAScript standard defines nine data types:

Seven primitive data types:

- Undefined
- Boolean
- Number
- String
- BigInt
- Symbol
- Null

Two derived data types (non-primitive):

- Object
- Function

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

### Undefined:

The meaning of `undefined` is “value is not assigned”, that means if a variable is declared, but not assigned, then its value is `undefined`:

Example:

```javascript
var x;
console.log(typeof x);

//output - undefined
```

Without initialization we try to access it here, so that it throws us `undefined`.

### Boolean:

Booleans can only have two values: `true` or `false`.

Example:

```javascript
var x = true;
console.log(typeof x);

//output - boolean
```

### Number:

JavaScript has only one type of number and it can be written with or without decimals.

Example:

```javascript
var age = 18;
console.log(typeof age);

//output - number
```

### String:

A string is a series of characters like "Sunil Pradhan".

Example:

```javascript
var name = 'Sunil';
console.log(typeof name);

//output - string
```

### BigInt:

In JavaScript, the `number` type cannot represent integer values larger than 2<sup>53</sup> (or less than -2<sup>53</sup> for negatives), that’s a technical limitation caused by their internal representation. That’s about 16 decimal digits, so for most purposes the limitation isn’t a problem, but sometimes we need really big numbers, e.g. for cryptography or microsecond-precision timestamps.

`BigInt` type is recently added to the JavaScript language to represent integers of arbitrary length.

A `BigInt` is created by appending `n` to the end of an integer literal:

Example:

```javascript
const x = 123n;
// the 'n' at the end means it's a BigInt

console.log(typeof x);

//output - BigInt
```

### Symbol:

Symbol is used to generate primitives which are unique in nature.

```javascript
var x = Symbol();
console.log(typeof x);

//output - Symbol
```

### Null:

It’s just a special value which represents “nothing”, “empty” or “value unknown”.

Example:

```javascript
var x = null;
console.log(typeof x);

//output - object
```

Here variable is empty so that it is at the beginning behave as a placeholder which you will use to put something inside of it.

The value does not go to `undefined` so that you have to put initially `null` which later you can change it to a value.

:bulb: **TIP:** Difference between `undefined` and `null` in JavaScript

`undefined` means the value has not been set, whereas `null` means the value has been set to empty.

```javascript
var a = null; //null example
var a; //undefined example
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

### Type Conversions OR Typecasting OR Coercion

Typecasting or coercion in simple terms means to change the data type of a value to another data type like for example, integer to a string or a string to a boolean etc.

There are two types of type casting, **implicit** and **explicit**.

Implicit type casting is when there is automatic conversion of data type, whereas when a developer expresses the intention to convert between types by writing the appropriate code, it’s called explicit type casting.

JavaScript supports three type of conversion

- to string
- to number
- to boolean

**String Conversion**

You can use `String()` function to convert a value to a string:

Example:

```javascript
var value = true;
alert(typeof value); //boolean

value = String(value); //now value is a string 'true'
alert(typeof value); //string
```

**Numeric Conversion**

You can use `Number()` function to explicitly convert a value to a number:

Example:

```javascript
var str = '123';
alert(typeof str); //string

var num = Number(str); //becomes a number 123
alert(typeof num); //number
```

Rules:

![js-numeric-conversion-rules](/img/js-numeric-conversion-rules.jpg)

**Boolean Conversion**

It happens in logical operations but can also be performed explicitly with a call to `Boolean()` function.

Rules:

![js-boolean-conversion-rules](/img/js-boolean-conversion-rules.jpg)

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

<a name="js-operators"></a>

## JavaScript Operators

### Operator Precedence:

Operator precedence describes the order in which operations are performed in an arithmetic expression.

The operator with the lowest number is said to have the highest precedence.

When an expression contains two or more operators that have the same precedence, they are evaluated according to their **associativity** (Associativity determines whether the operators are evaluated from left to right or right to left).

:bulb: **TIP:** Find operator precedence table at [MDN web docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence).

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

### Comparison Operators:

![js-comparison-operators](/img/js-comparison-operators.png)

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

### Bitwise Operators:

Bitwise operators compare bit to bit.

![js-bitwise-operators](/img/js-bitwise-operators.png)

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

### Assignment Operators:

**Basic assignment:**

```javascript
var a = 10;
console.log(a);

//output 10
```

**Addition assignment:**

```javascript
var a = 10;
a += 2; // a = a+2
console.log(a);

//output 12
```

**Subtraction assignment:**

```javascript
var a = 10;
a -= 2; // a = a-2
console.log(a);

//output 8
```

**Multiplication assignment:**

```javascript
var a = 10;
a *= 2; // a = a*2
console.log(a);

//output 20
```

**Division assignment:**

```javascript
var a = 10;
a /= 2; // a = a/2
console.log(a);

//output 5
```

**Modulus assignment:**

```javascript
var a = 10;
a %= 2; // a = a%2
console.log(a);

//output 0
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

### Exponentiation Operator:

The exponentiation operator `**` is a recent addition to the JavaScript language.

The result of `a ** b` is `a` multiplied by itself `b` times.

Example:

```javascript
alert(2 ** 2);

//output 4 (2*2)
```

Example:

```javascript
alert(2 ** 3);

//output 8 (2*2*2)
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

### Increment and decrement Operators:

**Increment Example:**

```javascript
var a = 20;
a++;
var b = 10;
var c = a + b;
console.log(c);

//output 31
```

**Decrement Example:**

```javascript
var a = 20;
a--;
var b = 10;
var c = a + b;
console.log(c);

//output 29
```

Increment/decrement can only be applied to variables. Trying to use it on a value like `5++` will give an error.

The operators `++` and `--` can be placed either before or after a variable.

When the operator goes after the variable, it is in “postfix form”: `counter++`

The “prefix form” is when the operator goes before the variable: `++counter`

Both of these statements do the same thing: increase counter by 1.

**Is there any difference?**

Yes, but you can only see it if you use the returned value of `++/--`.

Let’s clarify. As we know, all operators return a value. Increment/decrement is no exception. The prefix form returns the new value while the postfix form returns the old value (prior to increment/decrement).

Example(prefix):

```javascript
var counter = 1;
var a = ++counter;
console.log(a);

//output 2
```

Example(postfix):

```javascript
var counter = 1;
var a = counter++;
console.log(a);

//output 1
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

### `typeof` operator:

The `typeof` operator is used to get the data type of its operand. The operand can be either a literal or a data structure such as a variable, a function, or an object.

```javascript
var a = 10;
console.log(typeof a);

//output - number
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

<a name="js-branch-loops"></a>

## Branches and Loops

### Branching Out:

#### if statement

It is used to execute an instruction or block of instructions only if a condition is fulfilled i.e True.

Syntax:

```javascript
if (condition) {
  // Statements to execute if condition is true
}
```

Example:

```javascript
var x = 10;
if (x == 10) {
  console.log(x);
}
//if the value is true then display 10 on the screen

//output - 10
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### if...else statement

if...else statement is used when a different sequence of instructions is to be executed depending on the logical value(true, false) of the conditions evaluated.

Syntax:

```javascript
if (condition) {
  // Executes this block if condition is true
} else {
  // Executes this block if condition is false
}
```

Example:

```javascript
var x = 10;
if (x == 11) {
  console.log('Hello World!');
} else {
  console.log('Sorry!');
}
//if statement false then display else statement

//output - sorry!
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### Nested if statement

Embedding if statement inside another if statement is called nested if statement. Here, else statement allows you to print different statements depending upon the expression result (true, false).

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

```javascript
var firstName = 'Sunil';
var lastName = 'Pradhan';

if (firstName == 'Sunil') {
  if ((lastName = 'Pradhan')) {
    console.log('Hello! Sunil Pradhan');
  } else {
    console.log('Hello! you are someone else');
  }
}

//output - Hello! Sunil Pradhan
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### if-else-if ladder or else...if statement

Use else...if to specify a new condition to test, if the first condition is false.

Syntax:

```javascript
if (condition_1) {
  //statement_1_block;
} else if (condition_2) {
  //statement_2_block;
} else if (condition_n) {
  //statement_n_block;
}
.
.
.
else statment;
```

First check if statement condition 1, if it's not true then go to condition 2 and check. Still it’s not true then go to condition 3 and so on, until you are not getting any true value, otherwise show the else statement.

Example:

```javascript
var result = 38;
if (result <= 30) {
  console.log('You are failed');
} else if (result <= 40) {
  console.log('You are passed');
} else if (result <= 60) {
  console.log('You are good');
} else {
  console.log('You are very good');
}

//output - You are passed
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### Switch statement

The `switch` statement chooses between multiple statements to execute based on possible values of a single expression. Each of these values in a `switch` statement is called a `case`.

Syntax:

```javascript
switch (expression)
{
    case value1:
        statement1;
        break;
    case value2:
        statement2;
        break;
    .
    .
    case valueN:
        statementN;
        break;
    default:
        statementDefault;
}
```

:bulb: **TIP:** All the cases will be evaluated if you do not use a `break` statement.

Example: (Without default)

```javascript
var day = 1;
switch (day) {
  case 1:
    console.log('Sun');
    break;

  case 2:
    console.log('Mon');
    break;
}

//output - Sun
```

Example: (With default)

```javascript
var day = 5;
swtich(day) {
  case 1:
  console.log('Sun');
  break;

  case 2:
  console.log('Mon');
  break;

  default:
  console.log('It is wrong!');
}

//output - It is wrong!
```

Sometimes it is also possible or necessary to execute the same statement for **multiple expressions**.

Syntax:

```javascript
switch (expression)
{
    case value1:
        statement1;
        break;
    case value2:
    case value3:
        statement3;
        break;
    .
    .
    case valueN:
        statementN;
        break;
    default:
        statementDefault;
}
```

Example: In a week, if you have two days off then in that case you can use `switch` statements where you need to execute the same statement multiple times.

Example: (With multiple options)

```javascript
var day = 4;
switch (day) {
  case 1:
    console.log('Mon - Office day');
    break;

  case 2:
    console.log('Tue - Office day');
    break;

  case 3:
  case 4:
    console.log('Wed/Thu - Off day');
    break;

  default:
    console.log('You do not have off');
}

//output - Wed/Thu - Off day
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### Conditional (Ternary) operator

Example: (By if statement)

```javascript
function findGreater(a, b) {
  if (a > b) {
    return 'a is greater';
  } else {
    return 'b is greater';
  }
}

console.log(findGreater(3, 1));

//output - a is greater
```

Example: (By ternary operator)

```javascript
function findGreater(a, b) {
  return a > b ? 'a is greater' : 'b is greater';
}
console.log(findGreater(3, 1));

//output - a is greater
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### Multiple conditional (Ternary) operators

Example: (By if statement)

```javascript
function findGreaterOrEqual(a, b) {
  if (a === b) {
    return 'a and b are equal';
  } else if (a > b) {
    return 'a is greater';
  } else {
    return 'b is greater';
  }
}
console.log(findGreaterOrEqual(1, 1));

//output - a and b are equal
```

Example: (By ternary operator)

```javascript
function findGreaterOrEqual(a, b) {
  return a === b
    ? 'a and b are equal'
    : a > b
    ? 'a is greater'
    : 'b is greater';
}
console.log(findGreaterOrEqual(1, 1));

//output - a and b are equal
```

:bulb: **TIP:** A ternary operator returns the first value if the expression is true, or else returns the second value.

```javascript
expression ? ifTrue : ifFalse;
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

### Loop De Loop:

JavaScript supports the following kinds loops:

- **for -** loops through a block of code a number of times
- **while -** loops through a block of code while a specified condition is true
- **do...while -** loops through a block of code while a specified condition is true
- **for...in -** loops through the properties of an object
- **for...of -** loops through the values of an iterable object

#### for loop

The `for` loop is usually used where the loop will be repeated a fixed number of times.

**Type 1:**

Syntax:

```javascript
for (initialization condition; testing condition; increment/decrement)
{
    statement(s);
}
```

First `for` loop initialize a variable then enter into a test condition. If the condition is true then it will execute the block of statement. After this step, it will reach at the end of the block `}` but before it goes to the second time looping, it increases one value with the help of an increment operator.

When the loop runs for a second time, it does not even look at the initialized variable because its job has been over.

When the test condition is false then it stops executing the statement.

Example:

```javascript
var i = 5;
for (i = 0; i <= 5; i++) {
  console.log(i);
}

//output - 0, 1, 2, 3, 4, 5
```

**Type 2:**

Example:

```javascript
var i = 0;
for (; i < 5; i++) {
  console.log(i);
}

//output - 0, 1, 2, 3, 4
```

Here you define a variable first but in the `for` loop you are still keeping `;` at the initialization stage.

**Type 3:**

Example:

```javascript
var i = 0;
for (; i < 5; ) {
  i++;
  console.log(i);
}

//output - 1, 2, 3, 4, 5
```

**Type 4:**

Example:

```javascript
var i = 0;
for (; ; i++) {
  if (i == 3) {
    break;
  }
  console.log(i);
}

//ouput - 0, 1, 2
```

What it tells us. We have initialized a variable then we have our test condition within the if statement. It checks the condition upto equality 3 then it break the statement and exit from the loop.

#### Nested for loop

In nested `for` loop, you are using a `for` loop inside of another `for` loop.

Syntax:

```javaScript
for (initialization condition; testing condition; increment/decrement) {

            statement(s);

            for (initialization condition; testing condition; increment/decrement) {
              statement(s);
            }
      }
```

Example:

```javascript
for (i = 0; i < 2; i++) {
  console.log('Outer loop i: ' + i);

  for (j = 0; j < 2; j++) {
    console.log('inner loop j: ' + j);
  }
}

//output -
// Outer loop i: 0
// inner loop j: 0
// inner loop j: 1
// Outer loop i: 1
// inner loop j: 0
// inner loop j: 1
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### while loop

The while loop keeps repeating an action until an associated condition returns false. The while loop can be thought of as a repeating if statement.

**Type 1:**

Syntax:

```javaScript
while (test condition) {

    statement(s);
    increment/decrement;
}
```

We put one test condition at the beginning of the program. Then it will go to the body of the loop, once it finishes its work then it will increment or decrement the value. Finally it will reach the end of the loop where it can start again from starting until the condition is false.

Example:

![js-while-loop-type-one](/img/js-while-loop-type-one.png)

**Type 2:**

In other cases you can use a while loop when the condition is true forever but you do not know when the loop is going to close.

Example:

![js-while-loop-type-two](/img/js-while-loop-type-two.png)

#### Nested while loop

In nested while loop, you are using a while loop inside of another while loop.

Example:

![js-while-loop-nested](/img/js-while-loop-nested.png)

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### do...while loop

The do...while loop is similar to while loop, but the condition is checked after the loop body is executed. This ensures that the loop body is run at least once.

**Type 1:**

Syntax:

```javaScript
do
{
    statement(s)
}
while (condition);
```

Example:

![js-do-while-loop](/img/js-do-while-loop.png)

:bulb: **TIP:** In while statement we check condition first but in do..while statement we check condition last.

**Type 2:**

Example:

![js-do-while-loop-type-two](/img/js-do-while-loop-type-two.png)

#### Nested do...while loop

In nested do...while loop, you are using a do...while loop inside of another do...while loop.

Example:

![js-do-while-loop-nested](/img/js-do-while-loop-nested.png)

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### `break` and `continue` keyword in loop

**`break` - stop the loop:**

Example:

```javascript
for (i = 1; i <= 5; i++) {
  if (i == 3) {
    break; //stop loop
  }
  console.log(i);
}

//output - 1, 2
```

**`continue` - skip the loop:**

Example:

```javascript
for (i = 1; i <= 5; i++) {
  if (i == 3) {
    continue; //skip 3
  }
  console.log(i);
}

//output - 1, 2, 3, 4, 5
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### for...in Loop

The `for...in` loop is used to loop through an object’s properties and methods.

When you want to visit all object properties like its keys then you need to use `for..in` loop.

Syntax:

```javascript
for (var variable_name in object_name) {
  //code block
}
```

Example:

```javascript
function Mobile(model_no) {
  this.model = model_no;
  this.color = 'white';
  this.ram = '4GB';
}

var samsung = new Mobile('Galaxy');

for (var specs in samsung) {
  console.log(samsung[specs]);
}

//output - Galaxy, white, 4GB
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### for...of Loop

The `for..of` statement creates a loop iterating over iterable objects.

Syntax:

```javascript
for (var variable_name of array) {
}
```

Example:

```javascript
var stu = ['Sunil', 'Ram', 56, 66];

for (var value of stu) {
  console.log(value);
}

//output - Sunil
//output - Ram
//output - 56
//output - 66
```

**Difference between ( for… in ) and ( for… of ) statements in JavaScript:**

Both `for..in` and `for..of` are looping constructs which are used to iterate over data structures. The only difference is over what they iterate:

`for..in` iterates over all enumerable property keys of an object
`for..of` iterates over the values of an iterable object. Examples of iterable objects are arrays, strings, and NodeLists.

Example:

```javascript
let arr = ['el1', 'el2', 'el3'];

arr.addedProp = 'arrProp';

// elKey are the property keys
for (let elKey in arr) {
  console.log(elKey);
}

// elValue are the property values
for (let elValue of arr) {
  console.log(elValue);
}

//output
//0
//1
//2
//addedProp
//el1
//el2
//el3
```

###### Reference

https://stackoverflow.com/questions/29285897/what-is-the-difference-between-for-in-and-for-of-statements-in-jav#:~:text=Difference%20for..in%20and%20for,values%20of%20an%20iterable%20object.

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

<a name="js-function"></a>

## JavaScript Function

Functions are subprograms which are used to compute a value or perform a task.

**Type of function:**

- Built-in functions
- User-defined functions

#### Creating and calling a function

Syntax:

```javascript
function function_name() {
  //code block
}
function_name();
```

Example:

```javascript
function display() {
  console.log('Hello! Sunil');
}
display();

//output - Hello! Sunil
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### Function with parameters

Syntax:

```javascript
function function_name(parameter1, parameter2) {
  //code block
}
```

:bulb: **Note:**

- JavaScript function definitions do not specify data types for parameters.
- JavaScript functions do not perform type checking on the passed arguments
- JavaScript functions do not check the number of arguments received.

#### Call function with parameter

Syntax:

```javascript
function function_name(parameter1, parameter2) {
  //code block
}

function_name(argument1, argument2);
```

Example:

```javascript
function display(name) {
  console.log(name);
}
display('Sunil');

//output - Sunil
```

In JavaScript function parameters behave as variables. So when the display function is called [display(‘Sunil’)], it moves to the top of the function and meets display(name).

display(name) says - I have a parameter(variable) and expecting an argument which I can pass through. Do you have any?

display(‘Sunil’) says - Yes! I have an argument(Sunil). I am giving you.

Now the display(name) is replaced by its argument - display(Sunil).

It goes down to the console and show the output.

**Example: (Same number of arguments and parameters)**

```javascript
function display(fname, lname) {
  console.log(fname, lname);
}
display('Sunil', 'Pradhan');

//output - Sunil Pradhan
```

**Example: (different data types in arguments)**

```javascript
function display(fname, age) {
  console.log(fname, age);
}
display('Sunil', 20);

//output - Sunil 20
```

**Example: (argument missing)**

```javascript
function display(fname, age, zip) {
  console.log(fname, age, zip);
}
display('Sunil', 20);

//output - Sunil 20 undefined
```

If a function is called with missing arguments, the missing values are set to `undefined`.

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### Arguments object in JavaScript

When you call a function and pass the arguments, these arguments are stored in an object.

Example:

```javascript
function display(fname, lname) {
  console.log(arguments[0]);
  console.log(arguments[1]);
}
display('Sunil', 'Pradhan');

//output
//Sunil
//Pradhan
```

:bulb: **Note:**

The object contains an entry for each argument passed to the function, the first entry’s index starting at 0.

The arguments object is not an Array. It is similar to an Array, but does not have any Array properties except length.

**Example: (Change arguments value internally while execution)**

```javascript
function display(fname, lname) {
  arguments[0] = 'Anil';
  console.log(arguments[0]);
  console.log(arguments[1]);
}
display('Sunil', 'Pradhan');

//output
//Anil
//Pradhan
```

**Example: (Length property)**

```javascript
function display(fname, lname) {
  console.log(arguments.length);
}
display('Sunil', 'Pradhan');

//output - 2
```

Here the length property will show you how many arguments it contains when called by the function.

**Example: (Arguments object and for loop)**

By using for loop inside arguments object you can retrieve all of the arguments content.

```javascript
function display(fname, lname) {
  for (var i = 0; i < arguments.length; i++) {
    console.log(arguments[i] + '');
  }
}
display('Sunil', 'Pradhan');

//Output
//Sunil
//Pradhan
```

**Example: (Too many arguments)**

If you want to pass many arguments which are originally not present in your parameters then also you can display it on your output screen with the help of argument object.

```javascript
function num(num1, num2) {
  console.log(num1, num2);
  console.log(num1, num2, arguments[2]);
}
num(1, 2, 3);

//Output
// 1 2
// 1 2 3
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### Default parameter in JavaScript

When the function called and if it doesn't hold any value inside of it then it will use its default value from parameters to display its output.

Default parameter values always come on last, otherwise it returns `undefined`. Once default value start then rest of parameters should be default value only.

Syntax:

```javascript
function function_name(para1, para2 = 'value1', para3 = 'value2') {
  //code block
}
```

Example:

```javascript
function num(a, b, c = 70) {
  //c is defined as default value

  console.log(a);
  console.log(b);
  console.log(c);
}
num(10, 20); //two args

//output - 10, 20, 70
```

Here we have passed two arguments so that after `a` and `b`. It took the default value to show the result of `c`, i.e 70.

**Example: (Three arguments values, default value declared at last)**

```javascript
function num(a, b, c = 70) {
  //c is defined as default value

  console.log(a);
  console.log(b);
  console.log(c);
}
num(10, 20, 30); //three args

//output - 10, 20, 30
```

Here we have passed three arguments so that we don’t need to use the default value.

**Example: (One arguments value, default value declared at last)**

```javascript
function num(a, b, c = 70) {
  //c is defined as default value

  console.log(a);
  console.log(b);
  console.log(c);
}
num(10); //one args

//output - 10, undefined, 70
```

Here we have passed only one argument so that it successfully console out `a` but when it arrives at `b`, it doesn’t find any arguments. Hence, it shows `undefined`.

Due to the default value of `c` we are getting a result of 70 in the third console statement.

**Example: (Three arguments value, default value declared at middle)**

```javascript
function num(a, b = 50, c) {
  //b is defined as default value

  console.log(a);
  console.log(b);
  console.log(c);
}
num(10, 20, 30); //three args

//output - 10, 20, 30
```

Here we have passed three arguments and in the middle of parameters we have defined our default value. It still doesn't show `undefined` because we have passed three arguments.

Hence, it is fetching data from its arguments. But if it misses one argument value then it will again show `undefined`.

```javascript
function num(a, b = 50, c) {
  //b is defined as default value

  console.log(a);
  console.log(b);
  console.log(c);
}
num(10, 20); //30 missing

//output - 10, 20, undefined
```

If only one argument then it takes default value from `b` and `c` would be `undefined`.

```javascript
function num(a, b = 50, c) {
  //b is defined as default value

  console.log(a);
  console.log(b);
  console.log(c);
}
num(10); //one args

//output - 10, 50, undefined
```

**Example: (Multiple default values)**

```javascript
function num(a, b = 50, c = 70) {
  //b and c is defined as default value

  console.log(a);
  console.log(b);
  console.log(c);
}
num(10); //one args

//output - 10, 50, 70
```

:bulb: **TIP:** JavaScript also allows the use of array and null as default values.

<br>

**In case of `null`:**

```javascript
function num(a, b, c = null) {
  //c is defined as null but default value

  console.log(a);
  console.log(b);
  console.log(c);
}
num(10, 20); //two args

//output - 10, 20, null
```

**In case of `Array`:**

```javascript
function num(a, b = [101]) {
  console.log(a);
  console.log(b);
}
num(5, [10]);
//Passing 10 as an array

//output - 5, 10
```

Here it doesn't even look at default value because we have passed 10 in our argument.

```javascript
function num(a, b = [101]) {
  console.log(a);
  console.log(b);
}
num(5);

//output - 5, 101
```

No value passed so that it is displaying default value.

**Example: (Multidimensional array)**

```javascript
function person(age, name = ['Sunil', 'Pradhan']) {
  console.log(age);
  console.log(name);
}
person(20, ['Anil', 'Sahu']);

//Output - 20, Anil Sahu
```

**Example: (with index array number)**

```javascript
function person(age, name = ['Sunil', 'Pradhan']) {
  console.log(age);
  console.log(name[0]);
  console.log(name[1]);
}
person(20, ['Anil', 'Sahu']);

//Output - 20, Anil Sahu
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### Return statement in JavaScript function

A return statement in JavaScript function may return any type of data, including arrays and objects.

Syntax:

```javascript
function function_name(para1, para2,...) {
  //code block
  return (expression);
  //expression can be variable, arrays or objects
}
```

It says - I am going to return some expression where I am being called for.

```javascript
function add(a, b) {
  return a + b;
}

var x = add(10, 20);
console.log(x);

//output = 30
```

But what is the benefit of using return statement:

If you want to pass different arguments but with the same parameters then it can be a helpful.

```javascript
function add(a, b) {
  return a + b;
}

console.log(add(10, 20));
console.log(add(1, 2));
console.log(add(2, 2));

//output = 30
//output = 3
//output = 4
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### Variable scope in JavaScript function

It has two types:

- Global Scope
- Local Scope

**Global Scope:**

- A variable that is declared outside a function definition is a global variable, and its value is accessible and modifiable throughout your program.

- In a web browser, global variables are deleted when you close the browser window (or tab), but remain available to new pages loaded into the same window.

Example:

```javascript
var x = 'I am global variable';
function show() {
  console.log(x); //inside function
}
show();
console.log(x); //outside function

//output - I am global variable
//output - I am global variable
```

**Local Scope:**

- A variable that is declared inside a function definition is local. It is created and destroyed every time the function is executed, and it cannot be accessed by any code outside the function.
- Inside a function, if a variable has not been declared with `var` keyword it is created as a global variable.

Example:

```javascript
function show() {
  var j = 'I am local variable';
  //local variable
  console.log(j);
}
show();

//output - I am local variable
```

If try from outside function then:

Example:

```javascript
function show() {
  var j = 'I am local variable';
  //local variable
  console.log(j);
}
show();
console.log(j);

//output - I am local variable
//output - Error - ReferenceError: j is not defined
```

But when you try to access other functions local variables from one other function, you would get an error.

Example:

```javascript
var i = 'I am global';
function show() {
  var j = 'I am local variable';
  //local variable
  console.log(j);
}
show();
console.log(i);

if (true) {
  console.log(j);
}

//output - I am local variable
//output - I am global
//output - ReferenceError: j is not defined
```

Now try an example where you are not declaring a variable but assign it. In this case it turns into a global variable even if it is a local variable.

Example:

```javascript
function show() {
  j = 'I am now global variable';
  //it's now global
  console.log(j);
}
show();

console.log(j);

//output - I am now global variable
//output - I am now global variable
```

:bulb: **TIP:** If there is a function inside a function the inner function can access the outer function’s variables but the outer function can not access the inner function’s variables.

<br>

:bulb: **TIP:** Function arguments (parameters) work as local variables inside functions.

Example:

```javascript
function show() {
  //local variable

  var j;
  j = 'J a local variable of outer function';
  console.log(j);

  function innerFun() {
    //local variable
    var i;
    i = 'I a local variable of inner function';
    console.log(i);
    console.log(j);
  }
  innerFun();
  console.log(i);
}
show();

//output - J a local variable of outer function
//output - I a local variable of inner function
//output - J a local variable of outer function
//output - ReferenceError: i is not defined
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### Block scope in JavaScript function:

Block scope is achieved by JavaScript's two new keyword for variable - `let` and `const`.

```javascript
//block scope
if (true) {
  let i = 10; //local variable
  console.log(i);
}
console.log(i);

//output - 10
//output - ReferenceError: i is not defined
```

Variable 10 is only available for this if block, outside of this block if you try to access 10 then it would throw an error.

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### Closure in JavaScript function

A closure is an inner function that has access to the outer function’s variables.

For every closure we have three scopes:

- Local scope (Own scope)
- Outer functions scope
- Global scope

**Outer functions scope**

When an inner function variable is able to access an outer function variable then it is called **outer function scope**.

Example:

```javascript
var i = 10;
function show() {
  var j = 20;
  console.log(j);
  console.log(i);
  //outer scope
}
show();

//output - 20, 10
```

:bulb: **TIP:** Nested function is closure and closure is also a nested function

Example:

```javascript
function show() {
  var j = 'j - Local variable of outer function';
  console.log(j);

  function innerFun() {
    var k = 'k - Local variable of inner function';
    console.log(k);
  }
  innerFun();
}
show();

//output - j - Local variable of outer function
//output - k - Local variable of inner function
```

This is the basic concept of nested function. But where is the closure ??

It is when you are accessing the outer function variable inside of your inner function then its called closure.

```javascript
function show() {
  var j = 'j - Local variable of outer function';
  console.log(j);

  function innerFun() {
    var k = 'k - Local variable of inner function';
    console.log(k);
    console.log(j);
  }
  innerFun();
}
show();

//output - j - Local variable of outer function
//output - k - Local variable of inner function
//output - j - Local variable of outer function
```

Here closure is able to access local variables as well as outer function variable and more it can even access global variable in your program too.

Example:

```javascript
var a = 'Global variable';
console.log(a);
function show() {
  var j = 'j - Local variable of outer function';
  console.log(j);

  function innerFun() {
    var k = 'k - Local variable of inner function';
    console.log(k);
    console.log(j);
    console.log(a);
  }
  innerFun();
}
show();

//output - j - Local variable of outer function
//output - k - Local variable of inner function
//output - j - Local variable of outer function
//output - Global variable
```

But outer function can not access the inner function variable.

```javascript
function show() {
  var j = 'j - Local variable of outer function';
  console.log(j);

  function innerFun() {
    var k = 'k - Local variable of inner function';
    console.log(k);
    console.log(j);
  }
  innerFun();
  console.log(k);
}
show();

//output - j - Local variable of outer function
//output - k - Local variable of inner function
//output - j - Local variable of outer function
//output - ReferenceError: k is not defined
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### Function expression

When we create a function and assign it to a variable then its called as function expression.

:bulb: **TIP:** When you are creating function expression you need to close it by semicolon (;).

Example:

```javascript
var myfun = function show() {
  console.log('Hello Sunil');
};
myfun();

//output - Hello Sunil
```

Remember you can not call function expression before function definition else it would throw an error.

Why so?

Function expressions in JavaScript are not hoisted, unlike function declarations.

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### Anonymous function

Anonymous functions allow the creation of functions which have no specified name.

In other words, a JavaScript function which does not have any name.

Anonymous function can:

- Stored in a variable
- Returned in a function
- Pass in a function

:bulb: **TIP:** When you are creating an anonymous function you need to close it by semicolon (;).

**Store anonymous function in a variable:**

Example:

```javascript
var a = function () {
  console.log('Hello Sunil');
};
a();

//output - Hello Sunil
```

Passing some parameters then;

```javascript
var a = function (x, y) {
  console.log(x + ' ' + y);
};
a(10, 20);

//output - 10 20
```

**Returning anonymous function**

Example:

```javascript
function test() {
  return function () {
    alert('hi');
  };
}
test()();

//output - hi
```

###### Reference

- https://stackoverflow.com/questions/17382041/how-to-return-anonymous-function-in-javascript/17382060

**Passing anonymous function as argument:**

```javascript
function disp(myfun) {
  return myfun;
}
console.log(disp('Hello Sunil'));

//output - Hello Sunil
```

In this example we have passed a string in function as an argument. But now we need to see how to pass an anonymous function as an argument.

```javascript
function disp(myfun) {
  return myfun();
}
console.log(
  disp(function () {
    return 'Hello Sunil';
  })
);

//Output - Hello Sunil
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### Arrow function

An arrow function expression has a shorter syntax compared to function expression. Arrow functions are always anonymous in nature.

In other words, arrow function syntax will be small and it will be anonymous means this function will not have any name.

Syntax:

```javascript
() => {
  statements;
};
```

Example:

```javascript
var myFun = () => {
  console.log('Hello Sunil');
};
myFun();

//output - Hello Sunil
```

:bulb: **TIP:** You can not call arrow function before declaration.

**Arrow function with parameters**

Example:

```javascript
var myfun = (a) => {
  console.log(a);
};
myfun(10);

//output - 10
```

When passing a single parameter it is not mandatory to have `( )`, without it also work.

```javascript
var myfun = (a) => {
  console.log(a);
};
myfun(10);

//output - 10
```

But if you have multiple parameters then you should use `()`.

```javascript
var myfun = (a, b) => {
  console.log(a, b);
};
myfun(10, 20);

//output - 10, 20
```

If you don't have any parameters then you need to keep `()`.

```javascript
var myfun = () => {
  console.log('Sunil');
};
myfun();

//output - Sunil
```

:bulb: **TIP:** If you have a single parameter then it is not mandatory to have `()` as well as `{}`. But if you have a block of statement then you need to put `{}`.

**Arrow function with default parameter**

Example:

```javascript
var myfun = (a, b = 20) => {
  console.log(a + ' ' + b);
};

myfun(10);

//output - 10, 20
```

**Arrow function with Rest operator**

Example:

```javascript
var myfun = (a, ...args) => {
  console.log(a + ' <rest---> ' + args);
};

myfun(10, 20, 30, 40, 50);

//output - 10 <rest---> 20,30,40,50
```

:bulb: **Note:** Arrow function with return statement:

**No parameter**

If our function has just a single statement within the body then we can remove curly braces `{}` and we can also remove `return` keyword.

Example:

```javascript
const getArrowvalue = () => 10;
console.log(getArrowvalue());

//output - 10
```

Here we have the fat arrow syntax. On the left hand side you have the parameter list to the function and on the right hand side you have an implicit return value.

So no parameters right now and we are returning 10.

**Single parameter**

```
const getArrowvalue = m => 10 * m;
console.log(getArrowvalue(5));

//output - 50
```

When you pass a single argument you can omit `()`:

few other examples;

```
var myfunN = c => c;             //work
var myfunN = c => {c};           //not work
var myfunN = c => {return c};    //work
```

**Two or more parameter**

But when you pass two or more argument then you need to keep `()`:

```javascript
const getArrowvalue = (m, bonus) => 10 * m + bonus;
console.log(getArrowvalue(5, 50));

//output - 100
```

few other examples;

```
var myfunN = (a,b) => a+b;            //work
var myfunN = (a,b) => {a+b};          //not work - undefined
var myfunN = (a,b) => {return a+b};   //work
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### Immediately invoked functions expression in JavaScript(IIFE)

- IIFE (Immediately invoked function expression) is a JavaScript function that runs as soon as it is defined.
- It is a design pattern which is also known as **Self-Executing Anonymous Function**.

:bulb: **TIP:** IIFE function is like an anonymous function only but it is self executing.

It means IIFE allows you to avoid creation of global variables and functions.

- As it doesn’t define variables and functions globally so there will be no name conflicts.
- Scope is limited to that particular function

Example:

```javascript
(function () {
  console.log('Hello Sunil');
})();

//output - Hello Sunil
```

Here `var` is only limited to this function only. You can't access this variable outside of it.

**Example(With variable):**

```javascript
(function () {
  var a = 10;
  console.log(a);
})();

//output - 10
```

**Example(With parameter):**

```javascript
(function (a, b) {
  console.log(a, b);
})(30, 20);

//output - 30, 20
```

:bulb: **TIP:** IIFE function is self-executing

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### Callback function

Any function that is passed as an argument is called a callback function.

In other words, A callback is a function that is to be executed after another function has finished executing — hence the name ‘call back’.

Simply put: Callbacks are a way to make sure certain code doesn’t execute until other code has already finished execution.

Call back function is of two types:

- Synchronous : It waits for each operation to complete, after that it executes the next operation.
- Asynchronous : It never waits for each operation to complete, rather it executes all operations in the first go only.

**Example(Synchronous):**

```javascript
function show() {
  console.log('I am show function');
}
function geeky(callback) {
  callback();
}
geeky(show);
console.log('End');

//output - I am show function
//output - End
```

**Example(Asynchronous):**

```javascript
setTimeout(function show() {
  console.log('I am show function');
}, 5000);

console.log('End');

//output - End
//output - I am show function
```

**Example(without parameter):**

```javascript
function show() {
  console.log('I am show function');
}

function geeky(callback) {
  callback();
}
geeky(show);

//output - I am show function
```

**Example(with parameter):**

```javascript
function show(a) {
  console.log('I am show function ' + a);
}

function geeky(callback) {
  var a = 101;
  callback(a);
}
geeky(show);

//output - I am show function 101
```

**Example(Arrow function style):**

```javascript
function geeky(callback) {
  var a = 101;
  callback(a);
}
geeky((a) => console.log('I am show function ' + a));

//output - I am show function 101
```

###### References

- https://www.javascripttutorial.net/javascript-callback/

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

<a name="js-object"></a>

## Object

An object is a collection of properties, and a property is an association between a name (or key) and a value.

A property’s value can be a function, in which case the property is known as a method.

:bulb: **TIP:** Objects are variables too. But objects can contain many values.

<br>

Declare and initialize an object in JavaScript

- By using Object Literal
- By using Object Constructor

#### Object Literal in JavaScript

Syntax:

```javascript
var object_name = {};
```

Two ways you can write: `[]` or `.`

**Example(using `[]` operator):**

```javascript
var fees = {};

fees['Rahul'] = 100;
fees['Sunil'] = 200;
console.log(fees['Rahul']);
console.log(fees['Sunil']);

//output - 100, 200
```

If you want to give a space between your property then you need to use double quote and try to access it via `[]` operator rather than `.` operator.

```javascript
var fees = {};
fees['Sunil Pradhan'] = 100;
```

**Example(using `.` operator):**

```javascript
var fees = {};

fees['Rahul'] = 100;
fees['Sunil'] = 200;
console.log(fees.Rahul);
console.log(fees.Sunil);

//output - 100, 200
```

**Example(access methods):**

```javascript
var fees = {};
fees['total'] = function () {
  return 300;
};

fees.total(); //by using . operator
fees['total'](); //by using [] operator

console.log(fees.total());
console.log(fees['total']());

//output - 300, 300
```

**Declare and initialization of object together:**

Example:

```javascript
var fees = {
  Rahul: 100,
  Sunil: 200,
  total: function () {
    return 300;
  },
};
console.log(fees.Rahul);
console.log(fees.Sunil);
console.log(fees.total());

//output - 100, 200, 300
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### Object Constructor in JavaScript

Syntax:

```javascript
var object_name = new Object();
```

`Object()` is a constructor which creates a reference of that object and it later assigns it to `object_name`. Then we write its properties and access it.

:bulb: **TIP:** A constructor is a function that initializes an object.

 <br>

Two ways you can write: `[]` or `.`

**Example(using `[]` operator):**

```javascript
var fees = new Object();

fees['Rahul'] = 100;
fees['Sunil'] = 200;
console.log(fees['Rahul']);
console.log(fees['Sunil']);

//output - 100, 200
```

If you want to give a space between your property then you need to use double quote and try to access it via `[]` operator rather than `.` operator.

```javascript
var fees = new Object();
fees['Sunil Pradhan'] = 100;
```

**Example(using `.` operator):**

```javascript
var fees = new Object();

fees['Rahul'] = 100;
fees['Sunil'] = 200;
console.log(fees.Rahul);
console.log(fees.Sunil);

//output - 100, 200
```

**Example(access methods):**

```javascript
var fees = new Object();
fees['total'] = function () {
  return 300;
};

fees.total(); //by using . operator
fees['total'](); //by using [] operator

console.log(fees.total());
console.log(fees['total']());

//output - 300, 300
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### Adding Object properties and methods in JavaScript

Syntax:

```javascript
Object_name.Property_name = value;
Object_name['Property_name'] = value;
```

**Example (add props):**

```javascript
var fees = {
  Sunil: 100,
  Anil: 200,
};

console.log(fees.Sunil + ' ' + fees.Anil);
fees.Rahul = 400; //added one props
console.log(fees);

//output - 100, 200
//output - { Sunil: 100, Anil: 200, Rahul: 400 }
```

**Example (add methods):**

```javascript
var fees = {
  Sunil: 100,
  Anil: 200,
};

console.log(fees.Sunil + ' ' + fees.Anil);
fees.show = function () {
  return 300; // add methods
};
console.log(fees);
console.log(fees.show());

//output - 100, 200
//output - { Sunil: 100, Anil: 200, show: [Function (anonymous)] }
//output - 300
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### Deleting Object properties and methods in JavaScript

Delete operator is used to delete instance properties.

Syntax:

```javascript
delete object_name.property_name;
```

Example:

```javascript
var fees = {
  Sunil: 100,
  Anil: 200,
};

console.log(fees.Sunil + ' ' + fees.Anil);

delete fees.Sunil;

console.log(fees.Sunil + ' ' + fees.Anil);
console.log(fees);

//output - 100, 200
//output - undefined 200
//output - { Anil: 200 }
```

After removal with the `delete` operator, the property has an `undefined` value.

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### Factory function in JavaScript object

When a function returns an object, we call it a factory function. It can produce object instances without new keywords or classes.

```javascript
function mobile() {
  return {
    model: 'iphone',
    price: function () {
      return 'Price - ₹1000';
    },
  };
}
var Apple = mobile();
console.log(Apple.model + ' ' + Apple.price());

//output - iphone Price - ₹1000
```

It looks like a simple function but in reality it isn’t. It is a factory function because it returns an object. Through this method we can create multiple object instances without using new keywords.

:bulb: **TIP:** Factory function reduces code repetition.

**Example(with parameter):**

```javascript
function mobile(model_no) {
  return {
    model: model_no,
    price: function () {
      return 'Price - ₹1000';
    },
  };
}
var Apple = mobile('iphoneX');
console.log(Apple.model + ' ' + Apple.price());

var Apple = mobile('iphone 11');
console.log(Apple.model + ' ' + Apple.price());

//output - iphoneX Price - ₹1000
//output - iphone 11 Price - ₹1000
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### Constructor in JavaScript

Object instances are created with constructor, which are basically special functions that prepare new instances of an object for use.

**Remember:**

- Constructor is a special type of function that prepares a new instance of an object.
- With factory functions you can create object instances in the same manner you can use constructor to create object instances.
- When you are creating a constructor its first letter is always the capital letter.

Example:

```javascript
function Mobile() {
  //write constructor name always capital
  this.model = 'iphoneX';
  //this points newly created object: example - iphonex
  this.price = function () {
    console.log(this.model + ' ' + 'Price - ₹1000');
  };
}

var Apple = new Mobile();
Apple.price();

//output - iphoneX Price - ₹1000
```

Globally this keyword points to window object but here `this` keyword points to a new instance of an object.

**Remember:**

`Mobile()` is a constructor whereas, `price()` is a function here.

**Example(with parameter):**

```javascript
function Mobile(model_no) {
  //write constructor name always capital
  this.model = model_no;
  //this points newly created object: example - iphonex
  this.price = function () {
    console.log(this.model + ' ' + 'Price - ₹1000');
  };
}

var Apple = new Mobile('iphoneX');
Apple.price();

//output - iphoneX Price - ₹1000
```

This function is simply a constructor which behaves as a blueprint for all other mobile (samsung, lg). Because every mobile has a model, price and so.

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### How to check properties exists in JavaScript

**Method #1: By using `typeof` operator**

```javascript
function Mobile(model_no) {
  this.model = model_no;
  this.memory = 4;
}

var samsung = new Mobile('Galaxy');
var nokia = new Mobile('3310');

if (typeof nokia.memory !== 'undefined') {
  console.log('Available');
} else {
  console.log('Does not exit');
}

//output - Available
```

This program checks whether memory properties present in our program or not.

**Method #2: By using `in` operator**

```javascript
function Mobile(model_no) {
  this.model = model_no;
  this.memory = 4;
}

var samsung = new Mobile('Galaxy');
var nokia = new Mobile('3310');

if ('memory' in nokia) {
  console.log('Available');
} else {
  console.log('Does not exit');
}

//output - Available
```

**Method #3: By using `hasOwnProperty()`**

```javascript
function Mobile(model_no) {
  this.model = model_no;
  this.memory = 4;
}

var samsung = new Mobile('Galaxy');
var nokia = new Mobile('3310');

if (nokia.hasOwnProperty('memory')) {
  console.log('Available');
} else {
  console.log('Does not exit');
}

//output - Available
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### Object keys(object_name)

Example:

```javascript
function Mobile(model_no) {
  this.model = model_no;
  this.color = 'white';
  this.ram = '4GB';
  this.price = function () {
    console.log(this.model + 'Price - ₹3000');
  };
}

var samsung = new Mobile('Galaxy');

console.log(Object.keys(samsung));

//output - [ 'model', 'color', 'ram', 'price' ]
```

Object keys only show object instance members (model, color) but can not show prototype members.

By using `for..in` loop, it shows both object instance members and prototype members.

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

<a name="js-arrays"></a>

## Array

Arrays are collections of data items stored under a single name.

Arrays provide a mechanism for declaring and accessing several data items with only one identifier, thereby simplifying the task of data management.

We use arrays when we have to deal with multiple data items.

Arrays are a special type of object in JavaScript.

Example:

```javascript
var stu = ['Sunil', 'Anil', 'Rupa'];
console.log(stu);
console.log(typeof stu);

//output - [ 'Sunil', 'Anil', 'Rupa' ]
//output - object
```

In javascript you can create arrays in two ways:

- Array literal
- Array constructor

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### Array Literal

Syntax:

```javascript
var array_name = [];
```

:bulb: **TIP:** By default, array starts with index 0.

Example:

```javascript
var stu = [];
//empty array
stu[0] = 'Sunil';
stu[1] = 'Rahul';
stu[2] = 'Anil';

console.log(stu); //access all array
console.log(stu[0]); //access Sunil

//output - [ 'Sunil', 'Rahul', 'Anil' ]
//output - Sunil
```

Example:

```javascript
var stu = [, , , ,];
console.log(stu[0]);

//output - undefined
```

Example:

```javascript
var a = 10,
  b = 20,
  c = 30;
var num = [a, b, c];
console.log(num);

//output - [ 10, 20, 30 ]
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### Array Constructor

Syntax:

```javascript
var array_name = new Array();
```

Example:

```javascript
var stu = new Array();
//empty array

stu[0] = 'Sunil';
stu[1] = 'Rahul';
stu[2] = 'Rula';

console.log(stu);
console.log(stu[0]);

//output - [ 'Sunil', 'Rahul', 'Rula' ]
//output - Sunil
```

**Demerits of using `new` keyword**

Example:

```javascript
var num = new Array(5);
console.log(num[0]);

//output - undefined
```

This will create an empty array with length five. So this is not a good idea to use an array constructor if you have only a single numeric value.

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### Modifying array elements

Example:

```javascript
var stu = ['Sunil', 'Ram'];
console.log(stu);

stu[0] = 'Rula';
console.log(stu);

//output - [ 'Sunil', 'Ram' ]
//output - [ 'Rula', 'Ram' ]
```

Example:

```javascript
var stu = ['Sunil', 'Ram'];
var male = stu;
//storing array into a variable

console.log(male);
console.log(stu);

male[0] = 'Rula';
console.log(stu);

//output - [ 'Sunil', 'Ram' ]
//output - [ 'Sunil', 'Ram' ]
//output - [ 'Rula', 'Ram' ]
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### Removing array elements

Array elements can be removed using the `delete` operator. This operator sets the array element it is invoked on to `undefined` but does not change the arrays’ length.

Example:

```javascript
var stu = ['Sunil', 'Ram'];
console.log(stu);
delete stu[0];
console.log(stu);

//output - [ 'Sunil', 'Ram' ]
//output - [ undefined, 'Ram' ]
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### Array length property

The length property retrieves the index of the next available position at the end of the array. The length property is automatically updated as new elements are added to the array. For this reason, length is commonly used to iterate through all elements of any array.

:bulb: **TIP:** In array index it counts from 0 but in array length property it counts from 1.

```javascript
var stu = ['Sunil', 'Ram'];
console.log(stu.length);

//output - 2
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### Iteration of array using for loop

Example:

```javascript
var stu = ['Sunil', 'Ram', 56, 66];
for (let i = 0; i <= 3; i++) {
  console.log(stu[i]);
}

//output - Sunil, Ram, 56 , 66
```

Example:

```javascript
var stu = ['Sunil', 'Ram', 56, 66];
for (let i = 0; i <= stu.length - 1; i++) {
  console.log(stu[i]);
}

//output - Sunil, Ram, 56 , 66
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### forEach Loop

The `forEach` loop calls a provided function once for each element in an array, in order.

In other words,

ES6 provides the `forEach` loop to iterate over array elements. So let's say we have an array of numbers 2, 4, 6, 8 then we can call the `forEach` loop on this numbers array by passing a function.

Syntax:

```javascript
array.forEact(function (value, index, arr) {});
```

Where,

- value - It is the current value of array index and it's a variable so that you can name it anything like value, name or other. It is mandatory.
- index - Array's index number. Here also you can give any other name index, i or any other. It is not mandatory.
- arr - The array object the current element belongs to. It is not mandatory.

Example:

```javascript
var stu = ['Sunil', 'Ram', 56, 66];
stu.forEach(function (name) {
  console.log(name);
});

//output - Sunil, Ram, 56, 66
```

Example:

```javascript
var stu = ['Sunil', 'Ram', 56, 66];
stu.forEach(function (value, index) {
  console.log(value, index);
});

//output - Sunil 0
//output - Ram 1
//output - 56 2
//output - 66 3
```

`forEach` loop worked out pretty well with arrays but from ES6 you can use `forEach` with `maps` and `sets` too.

So over here we have created a new map and this contains two key value pairs first name `Sunil` and last name `Pradhan`.

```javascript
let myMap = new Map([
  ['fname', 'Sunil'],
  ['lname', 'Pradhan'],
]);

myMap.forEach(mapFunction);
function mapFunction(value, key, callingMap) {
  console.log(key + ' ' + value);
  console.log(myMap === callingMap);
}

//output - fname Sunil
//output - true
//output - lname Pradhan
//output - true
```

Similar to arrays we call the `forEach` loop on the `map` and we have a function passed into the parentheses.

Now this `map` function is going to again accept three parameters, the value so `Sunil` and `Pradhan`, the key `fname` and `lname`.

And then the `callingMap`, so the map on which the `forEach` method is called.

So that is how the `forEach` loop works with `maps` now, similarly we also have the `forEach` loop with `sets`:

Just create a new set and it has three unique values 1 2 & 3.

Again we are calling the `forEach` loop on mySet by passing a function called `set` function.

And the `set` function is going to accept three parameters again: `value`, `key` and `callingSet`.

```javascript
let mySet = new Set([1, 2, 3]);
mySet.forEach(setFunction);
function setFunction(value, key, callingSet) {
  console.log(key + ' ' + value);
  console.log(mySet === callingSet);
}

//output - 1 1
//output - true
//output - 2 2
//output - true
//output - 3 3
//output - true
```

So in `sets` the `key` and `value` are both the same but we have those three parameters here, because they wanted to maintain the standard across arrays, maps and sets.

Now if you have a look array has three parameters, map has three parameters and they wanted to continue the same and that is why they have three parameters even for a `set`.

So the `key` and `value` are going to be the same. You can just log out either one of them and when we do a `mySet` triple equal to the `callingSet` we have true.

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### MultiDimensional array

Multidimensional array is Arrays of Arrays.In other words, an array that contains an array is called a multidimensional array.

Multidimensional array can be 2D, 3D, 4D etc.

2D Array Example:

```javascript
var name[[], [], []];
```

| Student | Computer | Qt. |
| ------- | -------- | --- |
| Rahul   | Dell     | 10  |
| Sonam   | HP       | 20  |
| Sumit   | Zen      | 30  |

In computer memory:

| Student     | Computer   | Qt.      |
| ----------- | ---------- | -------- |
| [0][0]Rahul | [0][1]Dell | [0][2]10 |
| [1][0]Sonam | [1][1]HP   | [1][2]20 |
| [2][0]Sumit | [2][1]Zen  | [2][2]30 |

Example:

```javascript
var stu = [
  ['Sunil', 'Dell', 10],
  ['Anil', 'HP', 20],
  ['Rula', 'Zen', 50],
];

//for rows
for (let i = 0; i < 3; i++) {
  //for coloumns
  for (let j = 0; j < 3; j++) {
    console.log(stu[i][j]);
  }
}

//output - Sunil, Dell, 10
//output - Anil, HP, 20
//output - Rula, Zen, 50
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

### Array Methods

#### `concat()` Method

Syntax:

```javascript
new_array = old_array.concat(value1, value2, value_n);
```

The `concat()` method is used to merge two or more arrays. This method does not change the existing arrays, but instead returns a new array.

**Example(concat with new values):**

```javascript
var stu = ['Sunil', 'Hari', 'Ram'];
//concat values
var new_stu = stu.concat('Rula', 'Hari');
console.log(new_stu);

//output - [ 'Sunil', 'Hari', 'Ram', 'Rula', 'Hari' ]
```

**Example(merge two arrays and make a new array):**

```javascript
var stu1 = ['Sunil', 'Ram', 'Sumit'];
var stu2 = ['Raj', 'Rohan'];

var new_stu = stu1.concat(stu2);
console.log(new_stu);

//output - [ 'Sunil', 'Ram', 'Sumit', 'Raj', 'Rohan' ]
```

**Example(merge three arrays and make a new array):**

```javascript
var stu1 = ['Sunil', 'Ram', 'Sumit'];
var stu2 = ['Raj', 'Rohan'];
var stu3 = ['Pinku'];

var new_stu = stu1.concat(stu2, stu3);
console.log(new_stu);

//output - [ 'Sunil', 'Ram', 'Sumit', 'Raj', 'Rohan', 'Pinku' ]
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### `join()` Method

The `join()` method joins the elements of an array into a string, and returns the string. The elements will be separated by a specified separator. The default separator is comma `,`.

Syntax:

```javascript
array_name.join(separator);
```

Example:

```javascript
var stu = ['Sunil', 'Ram'];
var new_stu = stu.join(' / ');
console.log(stu);
console.log(new_stu);

//output - [ 'Sunil', 'Ram' ]
//output - Sunil / Ram
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### `reverse()` Method

The `reverse()` method reverses the order of the elements in an array.

Syntax:

```javascript
array_name.reverse();
```

Example:

```javascript
var stu = ['Sunil', 'Anil'];
console.log(stu);
stu.reverse();
console.log(stu);

//output - [ 'Sunil', 'Anil' ]
//output - [ 'Anil', 'Sunil' ]
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### `slice()` Method

The `slice()` method returns a shallow copy of a portion of an array into a new array object selected from beginning to end(end not included). The original array will not be modified.

Syntax:

```javascript
array_name.slice(start, end);
```

**Remember:**

- Returns a portion of the array as a second array
- Does not modify the array
- First argument specifies starting element
- Second argument specifies ending argument
- Second argument is optional

**Start:**

- If begin is `undefined`, slice begins from index 0.
- If the beginning is greater than the length of the sequence, an empty array is returned.
- A negative index can be used, indicating an offset from the end of the sequence. `slice(-2)` extracts the last two elements in the sequence.

**End:**

- If the end is omitted, slice extracts through the end of the sequence(arr.length).
- If the end is greater than the length of the sequence, slice extracts through to the end of the sequence (arr.length).
- A negative index can be used, indicating an offset from the end of the sequence. slice(2,-1) extracts the third element through the second-to-last element in the sequence.

**Example(start, end):**

```javascript
var arr = [1, 2, 3, 4, 5, 6];
var arr1 = arr.slice(0, 2);
console.log(arr1);

//output - [ 1, 2 ]
```

Here 0 is the starting point and position 2 is the end point but it is not included.

**Example(start):**

```javascript
var arr = [1, 2, 3, 4, 5, 6];
var arr1 = arr.slice(2);
console.log(arr1);

//output - [ 3, 4, 5, 6 ]
```

**Example(negative value - start):**

```javascript
var stu = ['Sanjay', 'Aman', 'Rehman', 'Rahul', 'Karan'];
console.log(stu);

var new_stu = stu.slice(-3);
console.log(new_stu);

//output - [ 'Sanjay', 'Aman', 'Rehman', 'Rahul', 'Karan' ]
//output - [ 'Rehman', 'Rahul', 'Karan' ]
```

In memory:

'Sanjay' ->5, 'Aman' ->4, 'Rehman'-> -3, 'Rahul'-> -2, 'Karan' -> -1

**Example(negative value - start, end):**

```javascript
var stu = ['Sanjay', 'Aman', 'Rehman', 'Rahul', 'Karan'];
console.log(stu);

var new_stu = stu.slice(-3, -1);
console.log(new_stu);

//output - [ 'Sanjay', 'Aman', 'Rehman', 'Rahul', 'Karan' ]
//output - [ 'Rehman', 'Rahul' ]
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### `splice()` Method

The `splice()` method changes the contents of an array by removing existing elements and/or adding new elements. This method changes the original array.

Syntax:

```javascript
array_name.splice(start, delete_count, replace_values);
```

**Start -** The first argument start specifies at what position to add/remove items, use negative values to specify the position from the end of the array.

**delete_count -** The second argument “delete_count”, is the number of elements to delete beginning with index start.

**replace_values -** “replace_values” are inserted in place of the deleted elements. If more than one separates it by comma.

**Remember:**

- Modifies the array on which it is invoked
- The first argument specifies the array postion for insertion or deletion
- The second argument indicates the number of elements to delete
- The deleted elements are returned as an array
- The second argument is optional
- Each additonal argument is inserted into the array

Example:

```javascript
var arr = [1, 2, 3, 4, 5, 6];
//delete few elements:

var arr1 = arr.splice(2, 2);
console.log(arr1);

//check old array
console.log(arr);

//output - [ 3, 4 ]
//output - [ 1, 2, 5, 6 ]
```

Example:

```javascript
var arr = [1, 2, 3, 4, 5, 6];
//delete few elements:

var arr1 = arr.splice(2, 2);
console.log(arr1);

//doesn't find any element
var arr2 = arr.splice(4);
console.log(arr2);

//check old array
console.log(arr);

//output - [ 3, 4 ]
//output - []
//output - [ 1, 2, 5, 6 ]
```

Example:

```javascript
var arr = [1, 2, 3, 4, 5, 6];
//inserting

let arr3 = arr.splice(2, 0, 'a', 'b');

console.log(arr3);
console.log(arr);

//output - []
//output - [
//          1, 2, 'a', 'b',
//          3, 4, 5,   6
//         ]
```

Example:

```javascript
var arr = [1, 2, 3, 4, 5, 6];
//inserting & deleting both

let arr4 = arr.splice(2, 1, 'a', 'b');

console.log(arr4);
console.log(arr);

//output - [3]
//output - [
//          1, 2, 'a', 'b',
//          4, 5, 6
//         ]
```

Example:

```javascript
var a = ['Sanjay', 'Aman', 'Rehman', 'Rahul'];

console.log(a);

a.splice(-2, 1, 'Neha', 'Karan');
//negative
console.log(a);

//output - [ 'Sanjay', 'Aman', 'Rehman', 'Rahul' ]
//output - [ 'Sanjay', 'Aman', 'Neha', 'Karan', 'Rahul' ]
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### `toString()` Method

The `toString()` Method returns a string containing the comma-separated values of the array. This method is invoked automatically when you print an array.

It is equivalent to invoking `join()` method without any arguments. The returned string will separate the elements in the array with commas.

Syntax:

```javascript
array_name.toString();
```

Example:

```javascript
var stu = ['Sunil', 'Ram', 'Gopal'];
stu.toString();
console.log(stu);

//output - [ 'Sunil', 'Ram', 'Gopal' ]
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### `Array.isArray()` Method

The `Array.isArray()` method determines whether the passed value is an Array. This function returns true if the object is an array, and false if not.

Syntax:

```javascript
Array.isArray(value);
```

Example:

```javascript
var result1 = Array.isArray(['Rahul', 'Sonam']);
console.log(result1);

//output - true

var result2 = Array.isArray('I am String');
console.log(result2);

//output - false
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### `indexOf()` Method

This method allows you to easily find the occurrence of an item in an array.

- If the item is not found, it returns -1
- The search will start at the specified position, or at the beginning if no start position is specified, and end the search at the end of the array.
- If the item is present more than once, the `indexOf` method returns the position of the first occurrence.

Syntax:

```javascript
var position = array_name.indexOf(item, start);
```

Example:

```javascript
var stu = ['Rahul', 'Sonam', 'Sumit', 'Raj', 'Raj'];

var position = stu.indexOf('Sunil');
console.log(position);

//output -1
```

Example:

```javascript
var stu = ['Rahul', 'Sonam', 'Sumit', 'Raj', 'Raj'];

var position = stu.indexOf('Sumit');
console.log(position);

//output - 2
```

Example:

```javascript
var stu = ['Rahul', 'Sonam', 'Sumit', 'Raj', 'Raj'];

var position = stu.indexOf('Raj');
console.log(position);

//output - 3
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### `fill()` Method

The `fill()` method fills all the elements in an array with a static value.

Syntax:

```javascript
array_name.fill(value, start, end);
```

Example:

```javascript
var stu = ['Rahul', 'Sonam', 'Sumit', 'Raj', 'Raj'];

stu.fill('Manu');

//no start and no end
console.log(stu);

//output - [ 'Manu', 'Manu', 'Manu', 'Manu', 'Manu' ]
```

Example:

```javascript
var stu = ['Rahul', 'Sonam', 'Sumit', 'Raj', 'Raj'];

stu.fill('Manu', 1, 3);

//fill Manu starting with index 1 to 3 but 3 not included
console.log(stu);

//output - [ 'Rahul', 'Manu', 'Manu', 'Raj', 'Raj' ]
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### `unshift()` Method

The `unshift()` method adds one or more elements to the beginning of an array and returns the new length of the array.

This method changes the length of an array.

Syntax:

```javascript
Array_name.unshift(value1, value2, value_n);
```

Example:

```javascript
var stu = ['Rahul', 'Sonam', 'Sumit', 'Raj', 'Raj'];

stu.unshift('Sunil');
console.log(stu);

//output - [ 'Sunil', 'Rahul', 'Sonam', 'Sumit', 'Raj', 'Raj' ]
```

Example:

```javascript
var stu = ['Rahul', 'Sonam', 'Sumit', 'Raj', 'Raj'];

var stu_length = stu.unshift('Sunil');
console.log(stu);
console.log(stu_length);

//output - [ 'Sunil', 'Rahul', 'Sonam', 'Sumit', 'Raj', 'Raj' ]
//output - 6
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### `push()` Method

The `push()` method adds one or more elements to the end of an array and returns the new length of the array.

The new item will be added at the end of the array.

This method changes the length of the array.

Syntax:

```javascript
Array_name.push(value1, value2, value_n);
```

Example:

```javascript
var stu = ['Rahul', 'Sonam', 'Sumit', 'Raj', 'Raj'];

stu.push('Sunil');
console.log(stu);

//output - [ 'Rahul', 'Sonam', 'Sumit', 'Raj', 'Raj', 'Sunil' ]
```

Example:

```javascript
var stu = ['Rahul', 'Sonam', 'Sumit', 'Raj', 'Raj'];

var stu_length = stu.push('Sunil');
console.log(stu);
console.log(stu_length);

//output - [ 'Rahul', 'Sonam', 'Sumit', 'Raj', 'Raj', 'Sunil' ]
//output - 6
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### `shift()` Method

The `shift()` method removes the first element from an array and returns that removed element. This method changes the length of the array.

Syntax:

```javascript
array_name.shift();
```

Example:

```javascript
var stu = ['Rahul', 'Sonam', 'Sumit', 'Raj', 'Raj'];

stu.shift();
console.log(stu);

//output - [ 'Sonam', 'Sumit', 'Raj', 'Raj' ]
```

Example:

```javascript
var stu = ['Rahul', 'Sonam', 'Sumit', 'Raj', 'Raj'];

var stu_removed = stu.shift();
console.log(stu);
console.log(stu_removed);

//output - [ 'Sonam', 'Sumit', 'Raj', 'Raj' ]
//output - Rahul
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### `pop()` Method

The `pop()` method removes the last element from an array and returns that removed element. This method changes the length of the array.

Syntax:

```javascript
array_name.pop();
```

Example:

```javascript
var stu = ['Rahul', 'Sonam', 'Sumit', 'Raj', 'Raj'];

stu.pop();
console.log(stu);

//output - [ 'Rahul', 'Sonam', 'Sumit', 'Raj' ]
```

Example:

```javascript
var stu = ['Rahul', 'Sonam', 'Sumit', 'Raj', 'Raj'];

var stu_removed = stu.pop();
console.log(stu);
console.log(stu_removed);

//output - [ 'Rahul', 'Sonam', 'Sumit', 'Raj' ]
//output - Raj
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### `Boolean()` Method

Boolean is the built-in object corresponding to the primitive Boolean data type. JavaScript boolean can have one of two values: true or false.

**Primitive values:**

```javascript
var primitiveTrue = true;
var primitiveFalse = false;
```

**Boolean function:**

```javascript
var functionTrue = Boolean(true);
var functionFalse = Boolean(flase);
```

**Boolean constructor:**

```javascript
var constructorTrue = new Boolean(true);
var constructorFalse = new Boolean(false);
```

Example:

```javascript
var a = Boolean(); //false
var a = Boolean(0); //false
var a = Boolean(-0); //false
var a = Boolean(NaN); //false
var a = Boolean(null); //false
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

<a name="js-string"></a>

## String

String is a group of characters.

```javascript
var name = 'Sunil';
console.log(name);
console.log(typeof name);

//output - Sunil
//output - String
```

**Store a string value in a variable:**

**Example(Primitive):**

```javascript
var str = 'Hello World!';
console.log(typeof str);

//output - string
```

**Example(Constructor):**

```javascript
var str = new String('Hello World');
console.log(typeof str);

//output - object
```

**Access string value:**

**Example(Primitive):**

```javascript
var str = 'Hello World!';
console.log(str);

//output - Hello World!
```

**Example(Constructor):**

```javascript
var str = new String('Hello World');
console.log(str);

//output - Hello World!
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### String Concatenation

Connect two different strings and make it one.

**Example(+ operator):**

```javascript
var str1 = 'Hello';
var str2 = ' Sunil';

console.log(str1 + str2);

//output - Hello Sunil
```

**Example(`concat()` method):**

The `concat()` method accepts any number of arguments and returns the string obtained by concatenating the arguments to the string on which it was invoked.

Syntax:

```javascript
string.concat(string1, string2, string_n);
```

```javascript
var new_str = 'A'.concat('B', 'C');
console.log(new_str);

var str1 = 'Hello';
var str2 = ' World!';
var str3 = ' ABC';
var new_str = str1.concat(str2, str3, ' XY');
console.log(new_str);

//output - ABC
//output - Hello World! ABC XY
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### Template Literal/String Templates

Template literals allow us to embed expressions. You can use multi-line strings and string interpolation features with them.

Template literals are enclosed by the back-tick (\` \`) character instead of double or single quotes.

Example:

```javascript
var user = 'Sunil';

var greet = `Welcome ${user} to ES6 course!`;
console.log(greet);

//output - Welcome Sunil to ES6 course!
```

If you want to use a value that is assigned to a variable within a string we can use the dollar`$` and wrap the variable name within curly braces.

:bulb: **TIP:** String Interpolation - Template literals can contain placeholders. These are indicated by the dollar sign and curly braces `${expression}`.

<br>

String template also allows you to use single quotes and double quotes within the string.

Example:

```javascript
var user = 'Sunil';

var greet = `Welcome 'single' "double" ${user} to ES6 course!`;
console.log(greet);

//output - Welcome 'single' "double" Sunil to ES6 course!
```

String template also supports multi-line strings so now you can have multiple lines without having to use the string concatenation.

Example:

```javascript
var user = 'Sunil';

var greet = `Welcome 'single' "double" ${user} to ES6 course!
              This is the second line.
              Third and so   on.
`;
console.log(greet);

//output - Welcome 'single' "double" Sunil to ES6 course!
//This is the second line.
//Third and so   on.
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### String length

The length property returns the length of a string

Example:

```javascript
var str = 'Sunil Pradhan';
console.log(str.length);
//including space

//output - 13
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

### String Methods

#### `charAt()` Method

The `charAt()` method returns the character at a specified index (position) in a string.

Example:

```javascript
var str = 'Hello Sunil';
console.log(str.charAt(9));

//output - i
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### `charCodeAt()` Method

The `charCodeAt()` method returns the unicode of the character at a specified index in a string.

```javascript
var str = 'Hello Sunil';
console.log(str.charCodeAt(9));

//output - 105
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### `toUpperCase()` & `toLowerCase()` Method

Convert string to uppercase and lowercase.

Example:

```javascript
var str = 'Hello Sunil';
console.log(str.toUpperCase());

//output - HELLO SUNIL
```

Example:

```javascript
var str = 'Hello Sunil';
console.log(str.toLowerCase());

//output - hello sunil
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### `trim()` Method

It removes white space from both side of string (starting and ending part only).

Example:

```javascript
var str = '      Hello Sunil    ';
console.log(str.trim());

//output - Hello Sunil
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### `replace()` Method

The `replace()` method replaces a specified value with another value in a string, `replace()` method replaces only the first match.

- replace (old, new) method
- case sensitive this method
- It's good to use in reg. expression

Example:

```javascript
var str = 'Hello Sunil';
console.log(str.replace('Sunil', 'World'));

//output - Hello World
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### `split()` Method

The `split()` method breaks the string up into a separate string according to a delimiter passed as its first argument. The result is returned in an array.

Example:

```javascript
var str = 'Hello';
console.log(str.split(''));

//output - [ 'H', 'e', 'l', 'l', 'o' ]
```

Example:

```javascript
var str = 'Hello World, I am Sunil';
console.log(str.split(','));

//output - [ 'Hello World', ' I am Sunil' ]
```

Example:

```javascript
var str = 'Hello World, I am Sunil';
var arr = str.split(' ');
console.log(arr[4]);

//output - Sunil
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### `indexOf()` Method

The `indexOf()` method takes a string argument and returns the index of the first occurance of the argument in a string. If the argument is not found returns -1.

This method also accepts an optional second argument that specifies the index at which to start the search.

Example:

```javascript
var str = 'Hi guys! I am Sunil';
console.log(str.indexOf('i'));
console.log(str.indexOf('i', 10));

//output - 1
//output - 17
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### `search()` Method

The `search()` method searches for a string for a specified value and returns the position of the match.

The `search()` method cannot take a second start position argument. It can use in reg. expression and bit advance of `indexOf()`.

Example:

```javascript
var str = 'Hi guys! I am Sunil';
console.log(str.search('i'));

//output - 1
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### `slice()` Method

The `slice()` extracts a part of a string and returns the extracted part in a new string.

The method takes two parameters: the starting index(position), and the ending index(position). The method returns a string containing the string beginning at the given index up to but not including the character at the index specified by the second argument.

If a parameter is negative, the position is counted from the end of the string.

Example:

```javascript
var str = 'Hi guys! I am Sunil';
console.log(str.slice(14, 19));

//output - Sunil
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### `substring()` Method

The `substring()` is similar to `slice()`. The first argument specifies the index at which the desired substring begins. The optional second argument indicates the index at which the desired substring ends.

The method returns a string containing the substring beginning at the given index up to but not including the character at the index specified by the second argument.

_The difference between slice and substring is that `substring()` cannot accept negative indexes._

Example:

```javascript
var str = 'Hi guys! I am Sunil';
console.log(str.substring(14, 19));

//output - Sunil
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### `substr()` Method

The `substr()` is similar to `slice()`. The `substr()` method returns the part of a string between the start index and a number of characters after it.

`substr()` extracts length characters from a string, counting from the start index. If the start is a positive number, the index starts counting at the start of the string. If the start is a negative number, the index starts counting from the end of the string.

Example:

```javascript
var str = 'Hi guys! I am Sunil';
console.log(str.substr(14, 19));

//output - Sunil
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

<a name="js-number"></a>

## Number

Number type in JavaScript includes both integer and floating point values. JavaScript numbers are always stored as double precision floating point numbers, following the international IEEE 754 standard.

JavaScript also provides an object representation of numbers.

**Example(Primitive):**

```javascript
//typeof - number

var a = 10; //Whole number
var a = 10.45; //Decimal number
var a = 5e3; //5000 - 5x10^3 exponent
var a = 34e-5; //0.00034 exponent
```

**Example(Constructor):**

```javascript
//typeof - Object

var a = new Number(10);
var a = new Number(10.45);
var a = new Number(5e3);
```

**Accessing number:**

Example:

```javascript
var a = 10;
console.log(a);
console.log(typeof a);

//output - 10
//output - number
```

Example:

```javascript
var x = new Number(100);
console.log(x);
console.log(typeof x);

//output - 100
//output - object
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### Number with String

Example:

```javascript
var a = '50';
var b = 10;
console.log(a + b);
console.log(typeof a, typeof b);

//output - 5010
//output - string number
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### NaN - Not a Number

The NaN property represents “Not-a-Number” value. This property indicates that a value is not a legal number. NaN never compares equal to anything, even itself.

The NaN property is the same as the Number.

Example:

```javascript
var c = 20; //number
var d = 'Hello'; //string
console.log(c / d);

//output - NaN
```

**NaN is not equal to anything in JavaScript:**

**Example:**

```javascript
if ('Hello' == NaN) {
  console.log('Equal');
} else {
  console.log('Not equal');
}

//output - Not equal
```

**Example:**

```javascript
if (NaN == NaN) {
  console.log('Equal');
} else {
  console.log('Not equal');
}
```

**Global `isNaN()` Method:**

- The `isNaN()` function is used to determine whether a value is an illegal number (Not-a-Number).
- This function returns true if the value equates to `NaN`. Otherwise it returns false.
- This function is different from the Number specific `Number.isNaN()` method.
- The global `isNaN()` function, converts the tested value to a Number, then tests it.

Example:

```javascript
var a = '50';
if (isNaN(a)) {
  console.log('Not a number');
} else {
  console.log('Legal number');
}

//output - Legal number
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### Infinity and Negative Infinity

Infinity or -Infinity is the value JavaScript will return if a number is too large or too small. All infinity values compare equal to each other.

Example:

```javascript
console.log(5 / 0); //Infinity
console.log(-5 / 0); //-Infinity
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

### Number Methods

#### `toString()` Method

`toString()` method returns a number as a string in other words it converts the number into string.

We can use this method to output numbers as hexadecimal(16), octal(8), binary(2).

Example:

```javascript
var a = 10;
console.log(typeof a);
console.log(a.toString());
console.log(typeof a.toString());

//output - number
//output - 10
//output - string
```

Example:

```javascript
var a = 10;
console.log(typeof a);
console.log(a.toString(2));
console.log(a.toString(8));
console.log(a.toString(16));

//output - number
//output - 1010
//output - 12
//output - a
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### `toExponential()` Method

The `toExponential()` method converts a number into an exponential notation.

Syntax:

```javascript
variable_name.toExponential(y);
```

Where y is an integer between 0 and 20 representing the number of digits in the notation after the decimal point. If omitted, it is set to as many digits as necessary to represent the value.

Example:

```javascript
var a = 58975.98745;
console.log(a.toExponential());
console.log(a.toExponential(2));
console.log(a.toExponential(4));

//output - 5.897598745e+4
//output - 5.90e+4
//output - 5.8976e+4
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### `toFixed()` Method

`toFixed()` method converts a number into a string, keeping a specified number of decimals; also it rounds the decimal. If the desired number of decimals are higher than the actual number, nulls are added to create the desired decimal length.

Syntax:

```javascript
a.toFixed(y);
```

Where y is the number of digits after the decimal point. Default is 0 (no digits after the decimal point).

Example:

```javascript
var a = 19.65823;
console.log(a.toFixed());
console.log(a.toFixed(2));
console.log(a.toFixed(3));

//output - 20
//output - 19.66
//output - 19.658
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### `toPrecision()` Method

`toPrecision()` method formats a number to a specified length. A decimal point and nulls are added (if needed), to create the specified length.

Syntax:

```javascript
variable_name.toPrecision(y);
```

Where y is the number of digits. If omitted, it returns the entire number (without any formatting)

Example:

```javascript
var a = 19.65823;
console.log(a.toPrecision());
console.log(a.toPrecision(2));
console.log(a.toPrecision(3));

//output - 19.65823
//output - 20
//output - 19.7
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### `isInteger()` Method

`Number.isInteger()` method determines whether a value is an integer or not.

This method returns true if the value is of the type `Number`, and an integer, Otherwise it returns false.

Example:

```javascript
console.log(Number.isInteger());
console.log(Number.isInteger(100));
console.log(Number.isInteger(-100));
console.log(Number.isInteger(100.45));
console.log(Number.isInteger(200 - 100));

//output - false
//output - true
//output - true
//output - false
//output - true
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### `isSafeInteger()` Method

`Number.isSafeInteger()` method determines whether a value is a safe integer.

A safe integer is an integer that can be exactly all integers from (2<sup>53</sup> - 1) to - (2<sup>53</sup> - 1).

This method returns true if the value is of the type `Number`, and a safe integer. Otherwise it returns false.

Example:

```javascript
console.log(Number.isSafeInteger(100));
console.log(Number.isSafeInteger(-100));
console.log(Number.isSafeInteger(0.1));

//output - true
//output - true
//output - false
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### Global JavaScript methods

Global JavaScript methods can be used on all JavaScript data types.

- Number()
- parseInt()
- parseFloat()

**Number() -** The `Number()` function converts the object argument to a number that represents the object’s value.

If the value can’t be converted to a legal number, `NaN` is returned.

If the parameter is a `Date` object, the `Number()` function returns the number of milliseconds since midnight January 1, 1970 UTC.

Example:

```javascript
console.log(Number(true));
console.log(Number('100'));
console.log(Number(100 / 'Hello'));

//output - 1
//output - 100
//output - NaN
```

Example:

```javascript
var f = new Date();
console.log(Number(f));

//output - 1591545077754
```

**parseInt() -** The parseInt() function parses a string and returns an integer.

Syntax:

```javascript
parseInt(string, radix);
```

Example:

```javascript
console.log(parseInt('10'));
console.log(parseInt('10.45'));
console.log(parseInt('10 20 30'));

//output - 10
//output - 10
//output - 10
```

**parseFloat() -** The `parseFloat()` function parses a string and returns a floating point number. This function determines if the first character in the specified string is a number.

If it is, it parses the string until it reaches the end of the number, and returns the number as a number, not as a string.

Syntax:

```javascript
parseFloat(string);
```

Example:

```javascript
console.log(parseFloat('10'));
console.log(parseFloat('10.45'));
console.log(parseFloat('10 20 30'));

//output - 10
//output - 10.45
//output - 10
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### Math object

The Math object holds a set of constants and methods that enable more complex mathematical operations than the basic arithmetic operators.

We can not instantiate a Math Object. The Math object is static so it’s properties and methods are accessed directly.

```javascript
console.log(Math.PI);

//output - 3.141592653589793
```

**`Min()` and `Max()` Method:**

`Min()` - find minimum value
`Max()` - find maximum value

Example:

```javascript
console.log(Math.min(50, 5, 90, 6));
console.log(Math.max(50, 5, 90, 6));

//output - 5
//output - 90
```

**`floor()` Method:**

The `floor()` method rounds a number downwards to the nearest integer, and returns the result.

Example:

```javascript
console.log(Math.floor(2.1));
console.log(Math.floor(6.65));
console.log(Math.floor(0.4));
console.log(Math.floor(-2.1));
console.log(Math.floor(-6.65));

//output - 2
//output - 6
//output - 0
//output - -3
//output - -7
```

**`round()` Method:**

The `round()` method rounds a number to the nearest integer. 6.4 will be rounded down, 6.5 will be rounded up.

Example:

```javascript
console.log(Math.round(2.1));
console.log(Math.round(6.65));
console.log(Math.round(0.4));
console.log(Math.round(-2.1));
console.log(Math.round(-6.65));

//output - 2
//output - 7
//output - 0
//output - -2
//output - -7
```

:bulb: **TIP:** floor and round is used when you are dealing with price or need to create a random number.

**`random()` Method:**

It generate random number.

Example:

```javascript
console.log(Math.random() * 100 + 1);
var x = Math.floor(Math.random() * 100 + 1);
console.log(x);

//output - 54.631881910377864
//output - 81
```

###### Reference

https://www.w3schools.com/jsref/jsref_obj_math.asp

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### Date object

The date object provides a sophisticated set of methods for manipulating dates and times.

- It reads the client machine date and time so if the client’s date or time is incorrect, your script will reflect this fact.
- Days of week and months of the year are enumerated beginning with zero.

0 - Sunday, 1 - Monday and so on.
0 - January, 1 - February and so on.

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### Creating date object

Date objects are created with the `new Date()` constructor. Date Objects created by programmers are static. They do not contain a ticking clock.

Syntax:

```javascript
new Date();
new Date(milliseconds);
new Date(year, month, day, hours, minutes, seconds, milliseconds);
new Date(dateString);
```

**Create Date object using `Date()`:**

`new Date()` creates a new date object with the current date and time.

Example:

```javascript
var today = new Date();
console.log(today);

//output - 2020-06-08T16:02:40.621Z
```

**Create Date object using `Date(millisecond)`:**

`new Date(millisecond)` - It creates a new date object as January 1,1970, 00:00:00 Universal Time (UTC).

Example:

```javascript
var today = new Date(1530867166586);
console.log(today);

//output - 2018-07-06T08:52:46.586Z
```

It is used for converting milliseconds to normal date format.

**Create Date object using `Date(year, month, day, hours, minutes, seconds, milliseconds)`:**

It creates an object with the date specified by the integer values for the year, month, day, hours, minutes, second, milliseconds. You can omit some of the arguments.

Example:

```javascript
var today = new Date(2020, 4, 25, 9, 45, 35, 0);
console.log(today);

//output - 2020-05-25T04:15:35.000Z
```

Month and Week day start with 0.

0 - Sunday
0 - January

Month day starts with 1

1 - 1

**Create Date object using `Date(dateString)`:**

`new Date(dateString)` - It creates a new date object from a date string.

Example:

```javascript
var today = new Date('May 12, 2020 10:16:05');
console.log(today);

//output - 2020-05-12T04:46:05.000Z
```

It is divided into three category:

| Date Type  | Formate     | Example                                 |
| ---------- | ----------- | --------------------------------------- |
| ISO Date   | YYYY-MM-DD  | 2020-06-21 (The International Standard) |
| Short Date | MM/DD/YYYY  | 06/21/2020                              |
| Long Date  | MMM DD YYYY | June 21 2020 or 21 June 2020            |

**ISO Date:**

ISO 8601 is the international standard for the representation of dates and times.

| Description    | Formate              | Example              |
| -------------- | -------------------- | -------------------- |
| Year and Month | YYYY-MM              | 2020-06              |
| Only Year      | YYYY                 | 2020                 |
| Date and Time  | YYYY-MM-DDTHH:MM:SSZ | 2020-06-21T12:00:00Z |

- Date and Time is separated with a capital T
- UTC time is defined with a capital letter Z
- If you want to modify the time relative to UTC, remove the Z and add +HH:MM or -HH:MM instead

Example:

```javascript
var today = new Date('2020-06');
console.log(today);

//output - 2020-06-01T00:00:00.000Z
```

**Short Date:**

- Short dates are written with an 'MM/DD/YYYY' format.
- In some browsers, months or days with no leading zeroes may produce an error.
- The behavior of 'YYYY/MM/DD' is undefined. Some browsers will try to guess the format.Some will return NaN.
- The behavior of 'DD-MM-YYYY' is also undefined. Some browsers will try to guess the format. Some will return NaN.

Example:

```javascript
var today = new Date('06-12-2020');
console.log(today);

//output - 2020-06-11T18:30:00.000Z
```

**Long Date:**

- Long dates are most often written with a 'MMM DD YYYY' format.
- Month and day can be in any order.
- Month can be written in full(January), or abbreviated(Jan).
- If you write 'June, 21, 2020' commas are ignored and Names are case insensitive.

Example:

```javascript
var today = new Date('Mar 25 2020');
console.log(today);

//output - 2020-03-24T18:30:00.000Z
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### Set Date Methods

This is used to set date.

- `setDate()` - Set the day as a number (1-31)
- `setFullYear()` - Set the year (optionally month and day)
- `setHours()` - Set the hour(0-23)
- `setMilliseconds()` - Set the milliseconds (0-999)
- `setMinutes()` - Set the minutes (0-59)
- `setMonth()` - Set the month (0-11)
- `setSecond()` - Set the seconds(0-59)
- `setTime()` - Set the time(milliseconds since January 1, 1970)

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### Get Date Methods

This is used to get date.

- `getFullYear()` - Get the year as a four digit number (yyyy)
- `getMonth()` - Get the month as a number (0-11)
- `getDate()` - Get the day as a number(1-31)
- `getHours()` - Get the hour(0-23)
- `getMinutes()` - Get the minute (0-59)
- `getSeconds()` - Get the second (0-59)
- `getMilliseconds()` - Get the millisecond (0-999)
- `getTime()` - Get the time (millisecond since January 1, 1970)
- `getDay()` - Get the weekday as a number(0-6)

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### Retrieve Month name and Day name

**For month:**

```javascript
var tarikh = new Date();
var month = tarikh.getMonth();
var day = tarikh.getDay();

console.log(getMonthName(month));

function getMonthName(monthnumber) {
  var monthname = [
    'January',
    'February',
    'March',
    'April',
    'May',
    'June',
    'July',
    'August',
    'September',
    'October',
    'November',
    'December',
  ];

  return monthname[monthnumber];
}

//output - June
```

**For day:**

```javascript
var tarikh = new Date();
var month = tarikh.getMonth();
var day = tarikh.getDay();

console.log(getDayName(day));

function getDayName(daynumber) {
  var dayname = [
    'Sunday',
    'Monday',
    'Tuesday',
    'Wednesday',
    'Thursday',
    'Friday',
    'Saturday',
  ];

  return dayname[daynumber];
}

//output - Monday
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### Format Date and Time

Example:

```javascript
var tarikh = new Date();
console.log(formateDate(tarikh));

function formateDate(pd) {
  var date = pd.getDate();
  var month = pd.getMonth();
  month++;
  var year = pd.getFullYear();
  return date + '-' + month + '-' + year;
}

//output - 8-6-2020
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### Convert Date to String

If you want to create a string in a standard format, Date provides three methods: -

- toString()
- toUTCString()
- toGMTString()

`toUTCString()` and `toGMTString()` format the string according to Internet (GMT) standards, whereas `toString()` creates the string according to local time.

Example:

```javascript
var today = new Date();
console.log(today.toString());
console.log(today.toUTCString());
console.log(today.toGMTString());

//output - Mon Jun 08 2020 22:38:27 GMT+0530 (India Standard Time)
//output - Mon, 08 Jun 2020 17:08:27 GMT
//output - Mon, 08 Jun 2020 17:08:27 GMT
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

<a name="js-prototype"></a>

## Prototype

By prototype, write once the code, it will be available for you to use on all other objects.

Syntax:

```javascript
classname.prototype.key = 'value';
```

Let's take one example:

```javascript
var Mobile = function (model_no) {
  this.model = model_no;
  this.price = 3000;
};

var samsung = new Mobile('Galaxy');
var nokia = new Mobile('G8');

//add a new object
samsung.color = 'White';
nokia.color = 'White';
console.log(samsung);
console.log(nokia);

//output - Mobile { model: 'Galaxy', price: 3000, color: 'White' }
//output - Mobile { model: 'G8', price: 3000, color: 'White' }
```

Here we have created a constructor and later we added an object such as color. Now doing console, it is clear new object is reflecting for samsung as well as for nokia. But the problem is we are here repeating code which looks much similar.

Do we have any other solution for it. Yes!, by prototype.

```javascript
var Mobile = function (model_no) {
  this.model = model_no;
  this.price = 3000;
};

var samsung = new Mobile('Galaxy');
var nokia = new Mobile('G8');

Mobile.prototype.color = 'white';
console.log(samsung);
console.log(nokia);
```

Output:

![js-prototype-nokia-samsung](/img/js-prototype-nokia-samsung.png)

**Instance member and Prototype member:**

When you are writing properties simply by using `key` and `value` pairs then it's called instance member.

But when you are writing propories by using a prototype then it's called prototype member.

Secondly, instance members are visible on console but prototype members does not visible on console.

```javascript
var Mobile = function (model_no) {
  this.model = model_no;
  this.price = 3000;
};

var samsung = new Mobile('Galaxy');
var nokia = new Mobile('G8');

Mobile.prototype.color = 'white';
console.log(samsung.color);
console.log(nokia);

//output - white
//output - Mobile { model: 'G8', price: 3000 }
```

:bulb: **TIP:** The simple meaning of prototype - it's a parent class or super class or base case.

<br>

**Iterate Instance and Prototype member using `for...in` loop:**

```javascript
var Mobile = function (model_no) {
  //instance member
  this.model = model_no;
  this.price = 3000;
};

var samsung = new Mobile('Galaxy');
var nokia = new Mobile('G8');
//prototype member

Mobile.prototype.color = 'white';
console.log(Object.keys(samsung));
//it tell us in our object how many properties present

//output - [ 'model', 'price' ]
```

Here you are able to see only instance members, not prototype members.

Remember if you are using `Object.keys` and trying to iterate for your object then those object which is related to its only visible. i.e only instance members not prototype members.

If you want to see prototype members too then you need to use `for..in` loop.

```javascript
var Mobile = function (model_no) {
  //instance member
  this.model = model_no;
  this.price = 3000;
};

var samsung = new Mobile('Galaxy');
var nokia = new Mobile('G8');
//prototype member

Mobile.prototype.color = 'white';

for (var key in samsung) {
  console.log(key);
}

//output - model, price, color
```

#### Prototype Object

In JavaScript we achieve inheritance by using a prototype.

:bulb: **TIP:** Every object is associated with another object in JavaScript and its root object is associated with `null`.
<br>

#### Prototype Inheritance

In JavaScript constructor does not inherit, its prototype inherits only.

```javascript
//Super class
var Mobile = function () {
  this.a = 10;
};

Mobile.prototype.z = 30;

//sub class

var samsung = function () {
  Mobile.call(this);
  this.b = 20;
};

var s = new samsung();
console.log(s.a);

//output - 10
```

Here it is calling its parent constructor and initializing it so that we are able to access it.

```javascript
//Super class
var Mobile = function () {
  this.a = 10;
};

Mobile.prototype.z = 30;

//sub class

var samsung = function () {
  Mobile.call(this);
  this.b = 20;
};

//Prototype inheritance

samsung.prototype = Object.create(Mobile.prototype);
samsung.prototype.constructor = samsung;

var s = new samsung();
console.log(s.a);
console.log(s.b);
console.log(s.z);

//output - 10, 20, 30
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

<a name="js-this"></a>

## JavaScript `this`

The JavaScript `this` keyword refers to the object it belongs to.

```javascript
// Create an object
var person = {
  firstName: 'Sunil',
  lastName: 'Pradhan',
  id: 5566,
  fullName: function () {
    return this.firstName + ' ' + this.lastName;
  },
};

// Display data from the object
console.log(person.fullName());

//output - Sunil Pradhan
```

In this example, `this` represents the person object because the person object "owns" the fullName method.

It has different values depending on where it is used:

- In a method, `this` refers to the owner object.
- Alone, `this` refers to the global object.
- In a function, `this` refers to the global object.
- In a function, in strict mode, `this` is undefined.
- In an event, `this` refers to the element that received the event.
- Methods like `call()`, and `apply()` can refer `this` to any object.

**`this` in a Method:**

In an object method, `this` refers to the "owner" of the method.

```javascript
// Create an object
var person = {
  firstName: 'Sunil',
  lastName: 'Pradhan',
  id: 5566,
  fullName: function () {
    return this.firstName + ' ' + this.lastName;
  },
};

// Display data from the object
console.log(person.fullName());

//output - Sunil Pradhan
```

The person object is the owner of the fullName method.

**`this` Alone:**

When used alone, the owner is the Global object, so this refers to the Global object.

In a browser window the Global object is `[object Window]`:

```javascript
var x = this;
alert(x);

//output - [object Window]
```

In this example, `this` refers to the window Object.

In strict mode, when used alone, `this` also refers to the Global object `[object Window]`:

```javascript
'use strict';
var x = this;
alert(x);

//output - [object Window]
```

In this example, `this` refers to the window Object.

**`this` in a Function (Default)**

In a JavaScript function, the owner of the function is the default binding for `this`. So, in a function, `this` refers to the Global object `[object Window]`.

```javascript
function myFunction() {
  return this;
}
alert(myFunction());

//output - [object Window]
```

In this example, `this` represents the object that "owns" myFunction.

**`this` in a Function (Strict):**

JavaScript strict mode does not allow default binding. So, when used in a function, in strict mode, `this` is `undefined`.

```javascript
'use strict';
function myFunction() {
  return this;
}
alert(myFunction());

//output  undefined
```

In a function, by default, `this` refers to the Global object. In strict mode, `this` is `undefined`, because strict mode does not allow default binding.

**`this` in Event Handlers:**

In HTML event handlers, `this` refers to the HTML element that received the event:

```html
<button onclick="this.style.display='none'">Click to Remove Me!</button>
```

**Object Method Binding:**

In these examples, `this` is the person object (The person object is the "owner" of the function):

```javascript
// Create an object
var person = {
  firstName: 'Sunil',
  lastName: 'Pradhan',
  id: 5566,
  myFunction: function () {
    return this;
  },
};

// Display data from the object
console.log(person.myFunction());

//output -

/*{
  firstName: 'Sunil', 
  lastName: 'Pradhan',
  id: 5566,
  myFunction: [Function: myFunction]
}*/
```

Here `this` represents the person object that "owns" the myFunction method.

```javascript
// Create an object
var person = {
  firstName: 'Sunil',
  lastName: 'Pradhan',
  id: 5566,
  fullName: function () {
    return this.firstName + ' ' + this.lastName;
  },
};

// Display data from the object
console.log(person.fullName());

//output - Sunil Pradhan
```

Here `this` represents the person object, because the person object "owns" the fullName method. In other words: `this.firstName` means the firstName property of this (person) object.

**Explicit Function Binding:**

The `call()` and `apply()` methods are predefined JavaScript methods. They can both be used to call an object method with another object as argument.

In the example below, when calling person1.fullName with person2 as argument, `this` will refer to person2, even if it is a method of person1:

```javascript
var person1 = {
  fullName: function () {
    return this.firstName + ' ' + this.lastName;
  },
};
var person2 = {
  firstName: 'Sunil',
  lastName: 'Pradhan',
};

console.log(person1.fullName.call(person2)); // Will return "Sunil Pradhan"

//output - Sunil Pradhan
```

Here `this` refers to person2, even if it is a method of person1.

###### References

- https://www.w3schools.com/Js/js_this.asp
- https://www.w3schools.com/Js/js_function_call.asp
- https://www.w3schools.com/Js/js_function_apply.asp

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

<a name="js-mixins"></a>

## Composition or Mixins

Let you create functions for humans which can eat, walk and talk. Again we want to extend it to Animal and Robot. All are ok, but robots can not eat whereas animals can eat, walk and talk but robots only walk and talk. Here we can not inherit all properties from human to Robot.

Because the eat() method will be a waste for us. To avoid this we can use Mixins.

With mixins you are allowed to attach a particular method() to your program.

```javascript
//mixin

var eating = {
  eat: function () {
    return 'I can eat';
  },
};

var walking = {
  walk: function () {
    return 'I can walk';
  },
};

var talking = {
  talk: function () {
    return 'I can talk';
  },
};

var Rahul = Object.assign({}, eating, walking, talking);

//Object.assign = mixins

console.log(Rahul.eat());
console.log(Rahul.walk());
console.log(Rahul.talk());

//output - I can eat
//output - I can walk
//output - I can talk
```

Let now you want to create a Robot;

```javascript
//mixin

var eating = {
  eat: function () {
    return 'I can eat';
  },
};

var walking = {
  walk: function () {
    return 'I can walk';
  },
};

var talking = {
  talk: function () {
    return 'I can talk';
  },
};

var Rahul = Object.assign({}, eating, walking, talking);

var RoboCop = Object.assign({}, walking, talking);

//Object.assign = mixins

console.log(Rahul.eat());
console.log(Rahul.walk());
console.log(Rahul.talk());

//output - I can eat
//output - I can walk
//output - I can talk

console.log(RoboCop.walk());
console.log(RoboCop.talk());

//output - I can walk
//output - I can talk
```

In future let you want to add a new feature to your robot which can start, then you will follow in such a way:

```javascript
//mixin

var eating = {
  eat: function () {
    return 'I can eat';
  },
};

var walking = {
  walk: function () {
    return 'I can walk';
  },
};

var talking = {
  talk: function () {
    return 'I can talk';
  },
};

var starting = {
  start: function () {
    return 'RoboCop Start';
  },
};

var Rahul = Object.assign({}, eating, walking, talking);

var RoboCop = Object.assign({}, starting, walking, talking);

//Object.assign = mixins

console.log(Rahul.eat());
console.log(Rahul.walk());
console.log(Rahul.talk());

//output - I can eat
//output - I can walk
//output - I can talk

console.log(RoboCop.walk());
console.log(RoboCop.talk());
console.log(RoboCop.start());

//output - I can walk
//output - I can talk
//output - RoboCop Start
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

<a name="js-class"></a>

## JavaScript Class

JavaScript classes, introduced in ES6, Classes are in fact “Special functions”.

There are two way to define class in JavaScript:

- Class Declaration
- Class Expression

#### Class Declaration

Syntax:

```javascript
class class_name {
  constructor() {
    Properties;
  }
  Methods;
}
```

The constructor method is a special method for creating and initializing an object created within a class. There can be only one special method with the name “constructor” in a class.

Example:

```javascript
//Class declaration

class Mobile {
  constructor() {
    //Instance member
    this.a = 12;
    this.show = function () {
      return 'Instance member';
    };
  }

  //prototype memeber
  display() {
    return 'Prototype member';
  }
}

//need to create an object

var samsung = new Mobile();
console.log(samsung.a);
console.log(samsung.show());
console.log(samsung.display());

//output - 12
//output - Instance member
//output - Prototype member
```

**Default Constructor:**

If you do not specify a constructor method a default constructor is used.

```javascript
//class declaration

class Mobile {
  display() {
    return 'Prototype memeber';
  }
}
var samsung = new Mobile();
console.log(samsung.display());

//output - Prototype memeber
```

**Parameterized Constructor:**

The constructor which has a parameter is called a parameterized constructor.

```javascript
//class declaration

class Mobile {
  constructor(model_no) {
    this.model = model_no;
  }
  show() {
    return this.model + 'Price - 3000';
  }
}
var samsung = new Mobile('Galaxy');
console.log(samsung.show());

//output - GalaxyPrice - 3000
```

#### Class Expression

Class expressions can be named or unnamed.

Syntax(Unnamed):

```javascript
var Mobile = class {
  constructor() {
    Properties;
  }
};
```

Example:

```javascript
//unnamed

var Mobile = class {
  constructor(model_no) {
    this.model = model_no;
  }
  show() {
    return this.model + 'Price - 3000';
  }
};

var samsung = new Mobile('Galaxy');
console.log(samsung.show());

//output - GalaxyPrice - 3000
```

Syntax(Named):

```javascript
var Mobile = class Mobile2 {
  constructor() {
    Properties;
  }
};
```

Example:

```javascript
//named

var Mobile = class Mobile2 {
  constructor(model_no) {
    this.model = model_no;
  }
  show() {
    return this.model + 'Price - 3000';
  }
};

var samsung = new Mobile('Galaxy');
console.log(samsung.show());

//output - GalaxyPrice - 3000
```

Both are the same.

**Class Hoisting in JavaScript:**

Class declarations and Class expression are not hoisted. You first need to declare your class and then access it.

**Class Inheritance:**

Through prototype you can achieve inheritance but it's more complicated. ES6 makes it more easy through class inheritance.

The `extends` keyword is used in class declarations or class expressions to create a class which is a child of another class.

The `extends` keyword can be used to subclass, custom classes as well as built-in objects.

Example:

```javascript
class Father {
  showFMoney() {
    return 'Father Money';
  }
}

class Son extends Father {
  showSMoney() {
    return 'Son Money';
  }
}

var s = new Son();
console.log(s.showFMoney());

//output - Father Money
```

:bulb: **Note:**
<br>

Base class/Super Class/Parent Class - all are same

Child class/Derived class/sub class - all are same

**Super Method:**

`Super()` is used to initialize the parent class constructor. If there is a constructor present in subclass, it needs to first call `super()` before using `this`.

:bulb: **TIP:** Derive class duty is to initialize the super class constructor before using it.
<br>

A constructor can use the `super` keyword to call the constructor of a parent class.

```javascript
class Father {
  constructor(money) {
    this.Fmoney = money;
  }
  showFmoney() {
    return this.Fmoney + ' Father Money';
  }
}

class Son extends Father {
  constructor(money) {
    super(money);
  }
  showSMoney() {
    return 'Son Money';
  }
}

var s = new Son(1000);
console.log(s.showFmoney());
console.log(s.showSMoney());

//output - 1000 Father Money
//output - Son Money
```

**Method Overriding**

Same function name with different implementation.

```javascript
class Father {
  show() {
    return 'Super Class';
  }
}

class Son extends Father {
  show() {
    return 'Sub Class';

    //redefined
  }
}
var s = new Son();
console.log(s.show());

//output - Sub Class
```

**Static Method**

The `static` keyword is used to define a `static` method for a class. `static` methods are called without creating objects and can’t be called through a class instance (Object).

Static methods are often used to create utility functions for an application.

:bulb: **Note:**

- `static` method is related to full class, remember it is not related to object.It depends on class not on specific Object.
- When we create function methods, it is for objects not for class.

```javascript
class Mobile {
  static disp() {
    return 'Static method';
  }
}
//Mobile.disp();
console.log(Mobile.disp());

//output - Static method
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

<a name="js-variable-hosting"></a>

## Variable Hoisting

Hoisting is JavaScript's default behavior of moving declarations to the top of the function, if defined in a function, or the top of the global context, if outside a function.

_It means if you have declared a variable inside a function then its declaration part will move to the top._

_But if you have not declared a variable inside any function simply declare it in your program then it globally moves to the top._

```javascript
var a; //variable declaration
a = 10; //variable initialization
```

Example:

We write code

```javascript
var a = 10;
document.write(a);
var b = 20;
```

JavaScript understand internally this way at compile phase

```javascript
var a;
var b;
a = 10;
document.write(a);
b = 20;
```

:bulb: In summary first declaration and then initialization.

This is the reason why we are able to use variables in JavaScript even before it has been declared. But remember, only variable declarations are hoisted to the top, not variable initialization.

But due to this nature of hosting you can come across into problem;

**Example(Variable):**

```javascript
var a = 10;
console.log(a + ' ' + b);
var b = 20;

//output 10 undefined
```

Why are you getting `undefined`?

Because JavaScript read your code:

```javascript
var a;
var b;

a = 10;
console.log(a  + “ “ +b);
b = 20;
```

`b` has been declared but later initialized. So that once console statment displayed then it reaches to `b= 20` which result into undefined.

**Example(Function):**

We write code

```javascript
var i = 'Hello';
console.log(i);

function show() {
  console.log(i);
}
show();

//output - Hello
//output - Hello
```

JavaScript understand internally this way at compile phase

```javascript
var i;
i = 'Hello';
console.log(i);
function show() {
  console.log(i);
}
```

Lets create a new variable inside the function:

```javascript
var i = 'Hello';
console.log(i);

function show() {
  console.log(i);
  var i = 'Sunil';
}
show();

//output - Hello
//output - undefined
```

JavaScript understand internally this way at compile phase

```javascript
var i;
i = 'Hello';
console.log(i);
function show() {
  var i;
  console.log(i);
  i = 'Sunil';
}
```

Here variable declaration takes top of the function so that we are getting value of `undefined`.

Fix:

```javascript
var i = 'Hello';
console.log(i);

function show() {
  var i = 'Sunil';
  console.log(i);
}
show();

//output - Hello
//output - Sunil
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

<a name="js-rest-spread"></a>

## Rest & Spread Operator

### Rest operator

The Rest operator allows you to represent an indefinite number of arguments as an array.

Syntax:

```javascript
function function_name(...args) {
  //code block
}
```

You can also pass some sample parameters while declaring Rest operator(...).

Syntax:

```javascript
function function_name(a, ...args) {
  //code block
}
```

:bulb: **TIP:** The Rest operator(...) must be the last parameter to a function.

**Example(Without parameter):**

```javascript
function show(...args) {
  console.log(args);
}

show(10, 20, 30, 40);

//output [ 10, 20, 30, 40 ]
```

**Example(With parameter):**

```javascript
function show(a, ...args) {
  console.log(a);
  console.log(args);
}

show(10, 20, 30, 40);

output; //10
output; //[ 20, 30, 40 ]
```

Here you can see it assigns `a = 10` and the rest of the arguments are assigned to 20, 30, 40.

This is the reason why it's called a Rest operator. Rest arguments for Rest parameters(...).

If you want to access only 20 or 30 then how can you do it?

Rest operator is just an array so by using index value you can access the value 20 or 30 it.

**Example(Using index value):**

```javascript
function show(a, ...args) {
  console.log(a);
  console.log(args[1]);
}

show(10, 20, 30, 40);

//output 10
//output 30
```

**Difference between Rest operator and Arguments object:**

Arguments object is not a real Array, while Rest operator are Array instances, meaning methods like `sort`, `map`, `forEach` or `pop` can be applied on it directly.

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

### Spread operator

Spread operator is kind of the opposite of the Rest operator so while the Rest operator takes a variable as number of parameters or arguments and puts them into a single array.

The spread operator takes an array and splits it into the individual elements so Rest is to combine whereas spread is to split.

Syntax:

```javascript
...stu;
```

Rest operator you will see mostly in functions whereas spread operator works in array and object.

**Example(array):**

```javascript
//array
var a = [10, 20, 30];
var b = a;
console.log(a);
console.log(b);

//output - [ 10, 20, 30 ]
//output - [ 10, 20, 30 ]
```

Change in a code slighlty;

```javascript
//array
var a = [10, 20, 30];
var b = a;
a[0] = 50;
console.log(a);
console.log(b);

//output - [ 50, 20, 30 ]
//output - [ 50, 20, 30 ]
```

You can see both values have been changed to 50. But why?

In Javascript array values never copy, it copies only references on the index.

```javascript
//array
var a = [10, 20, 30];
var b = a;
a[0] = 50;
console.log(a[0]);
console.log(b[0]);

//output - 50
//output - 50
```

To remove this issue you can use the spread operator.

```javascript
var a = [10, 20, 30];
var b = [...a]; //var b = [10, 20, 30]
a[0] = 50;
console.log(a[0]);
console.log(b[0]);

//output - 50
//output - 10
```

After using the spread operator you can see the changes.

```javascript
//array
var a = [10, 20, 30];
var b = [...a]; //var b = [10, 20, 30]
a[0] = 50;
b[0] = 80;
console.log(a[0]);
console.log(b[0]);

//output - 50
//output - 80
```

Try with few more values;

```javascript
//array
var a = [10, 20, 30];
var b = [...a, 40, 50];
console.log(a);
console.log(b);

//output - [ 10, 20, 30 ]
//output - [ 10, 20, 30, 40, 50 ]
```

Example:

```javascript
//array
var a = [10, 20, 30];
var b = [5, ...a, 40, 50];
console.log(a);
console.log(b);

//output - [ 10, 20, 30 ]
//output - [ 5, 10, 20, 30, 40, 50 ]
```

Example:

```javascript
//array
var a = [10, 20, 30];
var b = [40, 50, 60];
var c = [...a, ...b];
console.log(a);
console.log(b);
console.log(c);

//output - [ 10, 20, 30 ]
//output - [ 40, 50, 60 ]
//output - [ 10, 20, 30, 40, 50, 60 ]
```

Array creates reference but by using spread operators you will not face any issue of reference which creates an array.

**Example(object):**

```javascript
//Object

var a = {
  courseName: 'JavaScript',
  tutor: 'Sunil',
};

var b = a;
console.log(a);
console.log(b);

//output - { courseName: 'JavaScript', tutor: 'Sunil' }
//output - { courseName: 'JavaScript', tutor: 'Sunil' }
```

Object is also a reference type.

```javascript
//Object

var a = {
  courseName: 'JavaScript',
  tutor: 'Sunil',
};

var b = a;
a.courseName = 'React';
console.log(a);
console.log(b);

//output - { courseName: 'React', tutor: 'Sunil' }
//output - { courseName: 'React', tutor: 'Sunil' }
```

The value of `b` has also changed. We can use here the spread operator.

```javascript
//Object

var a = {
  courseName: 'JavaScript',
  tutor: 'Sunil',
};

var b = { ...a };
a.courseName = 'React';
console.log(a);
console.log(b);

//output - { courseName: 'React', tutor: 'Sunil' }
//output - { courseName: 'JavaScript', tutor: 'Sunil' }
```

Here the value `a` has only change not `b`.

If you want to add something.

```javascript
//Object

var a = {
  courseName: 'JavaScript',
  tutor: 'Sunil',
};

var b = { ...a, duration: 'TwoMonths' };
a.courseName = 'React';
console.log(a);
console.log(b);

//output - { courseName: 'React', tutor: 'Sunil' }
//output - { courseName: 'JavaScript', tutor: 'Sunil', duration: 'TwoMonths' }
```

Try to merge it;

```javascript
//Object

var a = {
  courseName: 'JavaScript',
  tutor: 'Sunil',
};

var b = { duration: 'TwoMonths' };
var c = { ...a, ...b };

console.log(c);

//output - { courseName: 'JavaScript', tutor: 'Sunil', duration: 'TwoMonths' }
```

Here reference are not being copied rather value copy.

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

<a name="js-module"></a>

## Module - Import & Export

**What are JavaScript Module?**

If you go through any book you will notice that the author divides the book into **chapters** and **sections**, but why?

Because this makes it possible for a reader to understand the progression in the book and to easily find a specific part that they are interested in, also the author is able to clearly indicate what the focus is on.

Now just like how a book is divided into chapters; JavaScript Module divide a program into sections of code that by some criteria belong together.

The benefit of organizing a program into modules is that it helps people who aren't yet familiar with the code to find what they are looking for.

In short: _Module is a JavaScript file where we write codes. The objects in a module are not available for use, unless the module file exports them._

In ES6 the Module syntax has been standardized. So let's say we have two files `ModuleA.js` and `ModuleB.js` then each of these files become a JavaScript Module.

So if we have a function in `ModuleB.js` to use it in `ModuleA.js` we `export` from `ModuleB.js` and `import` in `ModuleA.js`.

![js-module](/img/js-module.jpg)

And that's the basic idea behind JavaScript Module - Export and Import

#### Module Setup

**index.html**

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>JavaScript Module</title>
    <script type="module" src="ModuleA.js"></script>
  </head>
  <body>
    <h1>Learn JavaScript Module</h1>
  </body>
</html>
```

Two more files: **ModuleA.js**, **ModuleB.js**

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### Exporting Module

`export` - The export statement is used when creating JavaScript modules to export functions, objects, or primitive values from the module so they can be used by other programs with the `import` statement.

There are two different types of `export` - `named` and `default`. You can have multiple named exports per module but only one default export.

#### Named Exports

You can have multiple named exports per module. Named exports are useful to export several values. During the import, it is mandatory to use the same name of the corresponding object.

We have two files **ModuleA.js** & **ModuleB.js**, now let's head over to **ModuleB.js** and create a new variable.

**ModuleB.js**

```javascript
let fname = 'Sunil';
```

Now let's say we want to export this variable `fname` so that it can be used in other modules. So for that we just need to use the `export` keyword. So add `export` at the beginning of the statement.

**ModuleB.js**

```javascript
export let fname = 'Sunil';
```

So now our variable `fname` is ready to be accessed in other modules.

So how do we import that over to `ModuleA.js`?

So to import variables we use the keyword `import` followed by name of the variable, type `fname` within curly braces.

But from where are we importing it? From a file called `ModuleB.js` in the current directory(./)

**ModuleA.js**

```javascript
import { fname } from './ModuleB.js';
```

Try log to the console `fname`:

```javascript
import { fname } from './ModuleB.js';
console.log(fname);
```

**index.html**

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>JavaScript Module</title>
    <script type="module" src="ModuleA.js"></script>
  </head>
  <body>
    <h1>Learn JavaScript Module</h1>
  </body>
</html>
```

Let's save all files and head over to the browser to see console of `index.html`. There you go - Sunil.

![js-named-exports](/img/js-named-exports.jpg)

So we have created a variable `fname` equals `Sunil` in `ModuleB.js` and importing it into `ModuleA.js`, and we have displayed it on the log of `index.html`.

But how do JavaScript modules communicate with each other?

Let’s create one more variable in `ModuleB.js`:

**ModuleB.js**

```javascript
export let fname = 'Sunil';
export let lname = 'Pradhan';
```

Now to import this we can just specify with the comma the name of the variable so `lname` over here:

**ModuleA.js**

```javascript
import { fname, lname } from './ModuleB.js';
console.log(fname);
```

In console log use backticks for `fname` and `lname`.

**ModuleA.js**

```javascript
import { fname, lname } from './ModuleB.js';
console.log(`${fname} ${lname}`);
```

Output:

![js-named-exports-two](/img/js-named-exports-two.jpg)

Now let's say we have 10 variables to export, in such a case this export keyword can be replaced from every sentence and we can just have one export.

**ModuleB.js**

```javascript
let fname = 'Sunil';
let lname = 'Pradhan';

export { fname, lname };
```

So if we had 10 variables we just would specify all 10 variables separated by a comma. So now when we export it and import it, everything else remains the same.

**ModuleA.js**

```javascript
import { fname, lname } from './ModuleB.js';
console.log(`${fname} ${lname}`);
```

Output:

![js-named-exports-two](/img/js-named-exports-two.jpg)

Sunil Pradhan, so nothing changed.

So that's another way to export your variables. You can either do it in the same line or you can have a single export at the end specifying the list of variables.

The next point about importing is that we can specify an alias.

**ModuleA.js**

```javascript
import { fname as f, lname as l } from './ModuleB.js';
console.log(`${fname} ${lname}`);
```

So when you use an alias for an import you must use that alias else it would throw an error, so we need to change this to `f` and `l`.

**ModuleA.js**

```javascript
import { fname as f, lname as l } from './ModuleB.js';
console.log(`${f} ${l}`);
```

Output:

![js-named-exports-two](/img/js-named-exports-two.jpg)

:bulb: **TIP:** JavaScript Module imports are hoisted and read-only.

_That means whenever you have an import statement it is always going to be hoisted to the top and more `fname` and `lname` can be imported but can never be changed but what you can change is the properties of objects._

**ModuleB.js**

```javascript
let fname = 'Sunil';
let lname = 'Pradhan';

let obj = {
  name: 'Rula',
};

export { fname, lname, obj };
```

**ModuleA.js**

```javascript
import { fname, lname, obj } from './ModuleB.js';
obj.name = 'Anil';
console.log(obj.name);
console.log(`${fname} ${lname}`);
```

So let's save this and the name has been changed from `Rula` to `Anil`.

![js-named-exports-three](/img/js-named-exports-three.jpg)

#### Default Exports

Whenever we have modules that **export only a single value or a function** then, we can make use of the `default` keyword while exporting.

:bulb: **TIP:** You can have only one `default` `export` per module and it can be imported with any name.

So consider this example, in our `ModuleB.js`, I am going to have a new variable:

**ModuleB.js**

```javascript
let fname = 'Sunil';

export default fname;
```

And now since this is going to be the only export from this particular file or module we can use export `default` and then without curly braces the name of the variable.

While importing it there are few changes the first thing is you can leave out the curly braces so we don't have to use the curly braces while importing `default` export.

And the second thing is unlike `named` export where the name of the variable while exporting has to match the name while importing in module but in `default` export and import the name doesn't have to match.

So over here we can just call it `firstName` :

**ModuleA.js**

```javascript
import firstName from './ModuleB.js';

console.log(firstName);
```

This is going to work because we are going to be exporting only a single value from `ModuleB.js` and that is going to be captured in whatever we are importing.

So `firstName` is going to be mapped onto `fname`, so if we go ahead and log to the console our output would be same i.e Sunil.

![js-named-exports](/img/js-named-exports.jpg)

So that's how `default` export work. Another thing to keep in mind as we can also provide alias for importing `default` but the only thing is we need to use curly braces.

So `default as f`, so this default is going to be the default import from `ModuleB.js` and we just going to alias it with `f`.

**ModuleA.js**

```javascript
import { default as f } from './ModuleB.js';

console.log(f);
```

So when we save this and refresh we will get the same output.

![js-named-exports](/img/js-named-exports.jpg)

So aliases work with `default` imports as well.

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### Exporting Functions and Classes

As we exported variables we can also export functions and classes in ES6.

Let's take an example:

Over here in `ModuleB.js` we are going to create a new function `greet` and this is going to accept a parameter and all it does is going to log to the console.

**ModuleB.js**

```javascript
function greet(message) {
  console.log(message);
}
```

Then to export the function just like exporting a variable we can attach `export` keyword at the beginning.

**ModuleB.js**

```javascript
export function greet(message) {
  console.log(message);
}
```

So our function is ready to be exported, let's go ahead and `import` it in `ModuleA.js`.

Within curly braces the name of the function so `greet` and where are we importing it from the current directory i.e `ModuleB.js`, so now that we have the function we can go ahead and call it.

**ModuleA.js**

```javascript
import { greet } from './ModuleB.js';

greet('Hello Sunil');
```

let's pass `Hello Sunil`. So when we save this our output would be:

![js-function-module-export-import](/img/js-function-module-export-import.jpg)

So that's the basic idea behind exporting functions and importing them. Just add the `export` keyword and you `import` it and you can call it in the module where you have imported it.

So next let's have a look at how to `export` and `import` classes.

For this we are going to create a new class `GreetMessage` and this is going to have a `constructor` and within the constructor,let's just log "Constructor."

And let's also have a simple function greet and it's just going to log to the console "Greet Function."

**ModuleB.js**

```javascript
export function greet(message) {
  console.log(message);
}

class GreetMessage {
  constructor() {
    console.log('Constructor');
  }
  greet() {
    console.log('Greet Function');
  }
}
```

Now to export the class we can use the `export` keyword again and attach it at the very beginning.

**ModuleB.js**

```javascript
export function greet(message) {
  console.log(message);
}

export class GreetMessage {
  constructor() {
    console.log('Constructor');
  }
  greet() {
    console.log('Greet Function');
  }
}
```

So let's go back to `ModuleA.js` and by next to `greet` we need to specify `GreetMessage`.

And over here let's create a new instance of the class, so `let` `gm` is equal to a `new GreetMessage` and then call `gm.greet()`.

**ModuleA.js**

```javascript
import { greet, GreetMessage } from './ModuleB.js';

greet('Hello Sunil');

let gm = new GreetMessage();
gm.greet();
```

And when we save this and head over to the browser our output would be:

![js-class-module-export-import](/img/js-class-module-export-import.jpg)

So we have `Hello Sunil` which is the function and then we have the `constructor` invoked and then we have the `greet` function log to the console.

Here we have the `constructor` and the `greet` function both of them were imported and invoked when we created this instance of the class.

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### Summary - Module - Import & Export

**Importing defaults:**

You can have only one `default` `export` per module. A `default` `export` can be imported with any name.

![js-importing-defaults](/img/js-importing-defaults.jpg)

**Importing named:**

You can have multiple named exports per module. Named exports are useful to export several values. During the import, it is mandatory to use the same name of the corresponding object.

![js-importing-named](/img/js-importing-named.jpg)

**Named export and import for variable:**

**Mobile.js**

```javascript
//Named export variable

export const a = 10;
```

**App.js**

```javascript
//Named import variable
import { a } from './mobile.js';
console.log(a);
```

Same but different way to represent:

**Mobile.js**

```javascript
//Named export variable

const a = 10;
export { a };
```

**Named export function:**

**Mobile.js**

```javascript
//Named export function

export function show() {
  console.log('Hello Sunil');
}
```

**App.js**

```javascript
//Named import function
import { show } from './mobile.js';
show();
```

Same but different way to represent:

**Mobile.js**

```javascript
//Named export function

function show() {
  console.log('Hello Sunil');
}

export { show };
```

**Named export class:**

**Mobile.js**

```javascript
//Named export class

export class Nokia {
  volumeup() {
    console.log('High Volume');
  }
}
```

**App.js**

```javascript
//Named import class
import { Nokia } from './mobile.js';
const n = new Nokia();
n.volumeup();
```

Same but different way to represent:

**Mobile.js**

```javascript
//Named export class

class Nokia {
  volumeup() {
    console.log('High Volume');
  }
}

export { Nokia };
```

**App.js**

```javascript
//Named import class
import { Nokia } from './mobile.js';
const n = new Nokia();
n.volumeup();
```

**Multiple named export:**

**Mobile.js**

```javascript
//Multiple Named export

class Nokia {
  volumnUp() {
    console.log('High Volume');
  }
}

function show() {
  console.log('Hello Module');
}

export const a = 10;

export { Nokia, show };
```

**App.js**

```javascript
//Multiple Named import
import { Nokia, show, a } from './mobile.js';
const n = new Nokia();
n.volumnUp();
show();
console.log(a);
```

**Importing all:**

**Mobile.js**

```javascript
//Multiple Named export

class Nokia {
  volumnUp() {
    console.log('High Volume');
  }
}

function show() {
  console.log('Hello Module');
}

export const a = 10;

export { Nokia, show };
```

**App.js**

```javascript
//Multiple Named import
import * as device from './mobile.js';
const n = new Nokia();
n.volumnUp();
show();
console.log(a);
```

**Use default and named together:**

**Mobile.js**

```javascript
//default and named export

class Nokia {
  volumnUp() {
    console.log('High Volume');
  }
}

function show() {
  console.log('Hello Module');
}

export const a = 10;
export default Nokia;
export { show };
```

**App.js**

```javascript
// Named import
import Nokia, { show, a } from './mobile.js';
const n = new Nokia();
n.volumnUp();
show();
console.log(a);
```

**Default import and export for variable:**

**Mobile.js**

```javascript
//Default export variable

const a = 10;
export default a;
```

**App.js**

```javascript
//Default import variable
import a from './mobile.js';
console.log(a);
```

**Function import and export:**

**Mobile.js**

```javascript
//Default export function

export default function show() {
  console.log('Hello Module');
}
```

**App.js**

```javascript
//Default import function
import show from './mobile.js';
show();
```

Same but different way to represent:

**Mobile.js**

```javascript
//Default export function

function show() {
  console.log('Hello Module');
}

export default show;
```

**Class import and export:**

**Mobile.js**

```javascript
//Default export class

export default class Nokia {
  volumnUp() {
    console.log('High Volume');
  }
}
```

**App.js**

```javascript
//Default import class
import Nokia from './mobile.js';

const n = new Nokia();
n.volumnUp();
```

Same but different way to represent:

**Mobile.js**

```javascript
//Default export class

class Nokia {
  volumnUp() {
    console.log('High Volume');
  }
}

export default Nokia;
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

<a name="js-destructuring"></a>

## Destructuring - Array & Object

Destructuring is a convenient way of extracting multiple values from data stored in objects and Arrays.

### Array Destructuring:

Create a simple employee array and is going to hold three values first one is `Sunil`, which is first name then we will have `Pradhan` which is the last name and then we will have `Male` which is the gender.

```javascript
let employee = ['Sunil', 'Pradhan', 'Male'];
```

Next within square brackets we are going to say `fname` as first name, `lname` which is last name and then `gender` and this is going to be assigned to this employee array.

```javascript
let [fname, lname, gender] = employee;
```

So what looks like an array creation is actually the destructuring of this employee array.

So the first three elements of the employee array are assigned to these three variables so `Sunil` gets assigned `fname`, `Pradhan` to `lname` and `Male` to `gender`.

Here we are destructuring this employee array by splitting up this individual elements and assigning them to these variables.

```javascript
let employee = ['Sunil', 'Pradhan', 'Male'];
let [fname, lname, gender] = employee;

console.log(fname);
console.log(lname);
console.log(gender);

//output

//Sunil
//Pradhan
//Male
```

So that's a basic idea in array destructuring. We take the individual elements from an array and assign it to individual variables.

Now let's consider the second example, this time we don't have this male gender anymore.

```javascript
let employee = ['Sunil', 'Pradhan'];
let [fname, lname, gender] = employee;

console.log(fname);
console.log(lname);
console.log(gender);

//output

//Sunil
//Pradhan
//undefined
```

So we can still specify any number of variables on the left hand side while destructuring an array but once the mapping is done in this case `Sunil` to first name `Pradhan` to last name and we don't have any more values to assign to the variable so `undefined` is going to be the value for this gender and so on.

We can also omit variables on the left hand side, that means:

```javascript
let employee = ['Sunil', 'Pradhan', 'Male'];
let [fname, lname, gender] = employee;

console.log(fname);
console.log(lname);
console.log(gender);

//output

//Sunil
//Pradhan
//Male
```

Here in this case we only want to save this `male` into this `gender` variable, we don't want to unnecessarily have memory for a first name and last name since we are not going to be using it.

In such a scenario we can just omit it but this comma right here is essential.

```javascript
let employee = ['Sunil', 'Pradhan', 'Male'];
let [, , gender] = employee;

console.log(gender);

//output - Male
```

We can also destructure using the Rest operator which helps us to have a single variable that can contain a group of elements;

```javascript
let employee = ['Sunil', 'Pradhan', 'Male'];
let [fname, ...elements] = employee;

console.log(fname);
console.log(elements);

//output

//Sunil
//[ 'Pradhan', 'Male' ]
```

So we have `Sunil` which is assigned to first name and now since we have a Rest operator the remaining values are getting stored into an array and assigned to this element.

We can also use destructuring with default values;

```javascript
let employee = ['Sunil', 'Pradhan'];

let [fname, lname, gender] = employee;

console.log(fname);
console.log(lname);
console.log(gender);

//Output - Sunil, Pradhan, undefined
```

We don't have the gender anymore here so can specify a default value;

```javascript
let employee = ['Sunil', 'Pradhan'];

let [fname, lname, gender = 'Male'] = employee;

console.log(fname);
console.log(lname);
console.log(gender);

//Output - Sunil, Pradhan, Male
```

We have `Sunil` being a `Male` since we are not specifying `Male` or a third value in our employee array. There is no destructuring for this `gender` variable so it is going to take `Male` as a default value and it's going to log on to the console.

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

### Object Destructuring:

Let employee there's going to be an object first name is going to be `Sunil` and then we'll have a last name which is going to be `Pradhan` and they will have gender which is going to be `Male`.

```javascript
let employee = {
  fname: 'Sunil',
  lname: 'Pradhan',
  gender: 'Male',
};
```

Now destructure this employee object we need to use curly braces `{}`. We need to specify the variable names and we have to ensure that the property name is the same as this variable name.

So we need to have `fname`, `lname`, `gender` and this is going to be equal to an employee.

```javascript
let employee = {
  fname: 'Sunil',
  lname: 'Pradhan',
  gender: 'Male',
};

let { fname, lname, gender } = employee;

console.log(fname);
console.log(lname);
console.log(gender);

//output - Sunil, Pradhan, Male
```

So we have destructure this employee object by taking these individual property values and assigning them to the variables.

Now let's say our property name is huge and so we don't want to use such a variable name throughout in our code. So in such a case we can create an alias.

```javascript
let employee = {
  fname: 'Sunil',
  lname: 'Pradhan',
  gender: 'Male',
};

let { fname: f, lname: l, gender: g } = employee;

console.log(f);
console.log(l);
console.log(g);

//output - Sunil, Pradhan, Male
```

So that's pretty much how destructure works in JavaScript objects.

You have an object and then you use the curly braces and assign it to the object and each property name should match the variable name and then the value will get assigned to it.

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

<a name="js-symbols"></a>

## JavaScript Symbols

The purpose of a symbol is to generate a unique ID but the funny thing is that we never get access to that ID.

```javascript
let s = Symbol();
console.log(typeof s);

//output - symbol
```

We can also pass an optional symbol description while creating a symbol. So within parentheses we can specify a string so we can just call this first symbol.

```javascript
let s = Symbol('First Symbol');
console.log(typeof s);
console.log(s.toString());

//output- symbol
//output - Symbol(First Symbol)
```

So when we call the `toString()` method on the symbol we get the description. Okay so now let's create two more symbols.

```javascript
let s = Symbol('First Symbol');
console.log(typeof s);
console.log(s.toString());

let s2 = Symbol();
let s3 = Symbol();

console.log(s2 === s3);

//output- symbol
//output - Symbol(First Symbol)
//false
```

Therefore a symbol always creates a unique ID.

Now let's pass a description 'Test';

```javascript
let s = Symbol('First Symbol');
console.log(typeof s);
console.log(s.toString());

let s2 = Symbol('Test');
let s3 = Symbol('Test');

console.log(s2 === s3);

//output- symbol
//output - Symbol(First Symbol)
//false
```

It's still false. So it doesn't matter what the description is, a symbol is always going to create a unique ID.

Now let's say that we have created a new symbol but we need to get hold of that symbol so that we can use the same symbol again in a different or the same file. So for that purpose we have a built in symbol registry.

So to add a symbol to the registry we use the `symbol.for()` method.

```javascript
let s = Symbol('First Symbol');
console.log(typeof s);
console.log(s.toString());

let s2 = Symbol('Test');
let s3 = Symbol('Test');

console.log(s2 === s3);

let s4 = Symbol.for('RegSymbol');
```

Here's the thing though `Symbol.for` doesn't add the symbol right away it checks if a symbol with the key RegSymbol already exists in the registry if it does it will return that symbol over
here to `s4`.

If it doesn't exist then it will create a new symbol in the registry.

```javascript
let s = Symbol('First Symbol');
console.log(typeof s);
console.log(s.toString());

let s2 = Symbol('Test');
let s3 = Symbol('Test');

console.log(s2 === s3);

let s4 = Symbol.for('RegSymbol');
let s5 = Symbol.for('RegSymbol');
console.log(s4 === s5);

//output - symbol
//output - Symbol(First Symbol)
//output - false
//output - true
```

There you go it's true so what happened here is that when we did a `Symbol.for` on the first time a new symbol was created in the global registry with this description.

And when `Symbol.for` was called again with the same description this symbol was retrieved and stored in `s5` file so.

Now `s4` and `s5` both the symbols are the same we have no clue as to what the ID for these two symbols are but we just know that they are equal.

Now let's say we want the key that was associated with the symbol when the symbol was added to the global registry. So for that we have another method called `Symbol.keyFor`.

```javascript
let s = Symbol('First Symbol');
console.log(typeof s);
console.log(s.toString());

let s2 = Symbol('Test');
let s3 = Symbol('Test');

console.log(s2 === s3);

let s4 = Symbol.for('RegSymbol');
let s5 = Symbol.for('RegSymbol');
console.log(s4 === s5);
console.log(Symbol.keyFor(s4));

//output - symbol
//output - Symbol(First Symbol)
//output - false
//output - true
//output - RegSymbol
```

Here `Symbol.keyFor` is going to give us a key for a symbol.

So when we come across a symbol and we are not sure what it is used for we can use this method to get the description. Now you know that this symbol was actually used to set up a symbol in the global registry.

Okay now that we know symbol is used to create a unique ID a good place to use them or use symbols is in object properties.

So we can have a new symbol `let fname = Symbol()` and then we can create a new object that person is equal to and by using the bracket notation we can use the symbol over here `[fname]` as the property.

```javascript
let s = Symbol('First Symbol');
console.log(typeof s);
console.log(s.toString());

let s2 = Symbol('Test');
let s3 = Symbol('Test');

console.log(s2 === s3);

let s4 = Symbol.for('RegSymbol');
let s5 = Symbol.for('RegSymbol');
console.log(s4 === s5);
console.log(Symbol.keyFor(s4));

let fname = Symbol();
let person = {
  [fname]: 'Sunil',
};
console.log(Object.getOwnPropertyNames(person));

//output - symbol
//output - Symbol(First Symbol)
//output - false
//output - true
//output - RegSymbol
//output - []
```

Now we have created a unique property inside this object so we never have to worry about our code conflicting with existing methods or being accidentally overwritten. Because this property is always going to be unique.

So now when we try to log the console `Object.getOwnPropertyNames(person)`, we don't get this property first name listed out because it is in fact a symbol, so we need to use another static method which is now present in ES6, namely `getOwnPropertySymbols`.

```javascript
let s = Symbol('First Symbol');
console.log(typeof s);
console.log(s.toString());

let s2 = Symbol('Test');
let s3 = Symbol('Test');

console.log(s2 === s3);

let s4 = Symbol.for('RegSymbol');
let s5 = Symbol.for('RegSymbol');
console.log(s4 === s5);
console.log(Symbol.keyFor(s4));

let fname = Symbol();
let person = {
  [fname]: 'Sunil',
};
console.log(Object.getOwnPropertyNames(person));
console.log(Object.getOwnPropertySymbols(person));

//output - symbol
//output - Symbol(First Symbol)
//output - false
//output - true
//output - RegSymbol
//output - []
//output - [ Symbol() ]
```

And if we pass, let's say `FirstName`

```javascript
let s = Symbol('First Symbol');
console.log(typeof s);
console.log(s.toString());

let s2 = Symbol('Test');
let s3 = Symbol('Test');

console.log(s2 === s3);

let s4 = Symbol.for('RegSymbol');
let s5 = Symbol.for('RegSymbol');
console.log(s4 === s5);
console.log(Symbol.keyFor(s4));

let fname = Symbol('FirstName');
let person = {
  [fname]: 'Sunil',
};
console.log(Object.getOwnPropertyNames(person));
console.log(Object.getOwnPropertySymbols(person));

//output - symbol
//output - Symbol(First Symbol)
//output - false
//output - true
//output - RegSymbol
//output - []
//output - [ Symbol(FirstName) ]
```

So this is the new static method in ES6 which we can use to list the symbols used for an object.

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

### Symbol iterator:

As we know ES6 provides a new way to iterate over objects and that is the `for...of` loop but the `for...of` loop can be used with all types of objects. For an object to work with the `for...of` loop it needs to have a special method and the special method is called as the iterator method.

But how do we know if the object has an iterator method? By checking to see if the object has a method defined for the key `Symbol.iterator` so this is where this well-known `Symbol.iterator` comes into action.

What we are doing here is checking to see if a method exists for
the object at this particular key so at `Symbol.iterator` if typeof string of symbols iterator returns a method or a function then this object can be used with the `for...of` loop.

Now let's have a look which of these types can be used with the `for...of` loop.

```javascript
let str = 'Hello';
let arr = [1, 2, 3];
let num = 5;
let obj = { name: 'Sunil' };

console.log('For string -' + typeof str[Symbol.iterator]);
console.log('For array -' + typeof arr[Symbol.iterator]);
console.log('For number -' + typeof num[Symbol.iterator]);
console.log('For object -' + typeof obj[Symbol.iterator]);

//output - For string - function
//output - For array - function
//output - For number -undefined
//output - For object -undefined
```

So for `string` it's a `function` that means we can use a `string` in a `for...of` loop, for `array` we can use a `for...of` loop because the type of the method is `function` or the type of method add similar iterator is a `function`.

But for `number` and `object` it is `undefined` so that means to say that we cannot use the `for...of` loop with `number` and `object`.

Now that is the main use of `Symbol.iterator` to check a `for...of` loop can be used with a particular object or not.

Now does that mean that objects are not iterable well ? no!

We can write our own special iterator method, so that even an object can be used with the `for...of` loop.

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

### Iterables and Iterators:

ES6 introduces iteration which is a new way to traverse data and iteration revolves around two key concepts namely `iterables` and `iterators`.

Now an iterable is any object that implements a method whose key is `Symbol.iterator` so we will have an iterable which is nothing but an object, which has a property `Symbol.iterator` method and
this method is going to return an iterator.

```javascript
Iterable {
  [Symbol.iterator()]: iterator
}
```

What is an iterator? An iterator is an object that is going to implement a `next` method. So it is going to have a `next` method and this `next` method knows how to access elements in a collection, be it an `array` or a `string` or `maps` or `sets`.

```javascript
Iterable {
  [Symbol.iterator()]: Iterator
}

Iterator{
  next():
}
```

And its returns an object, let's call this iterator `IResultObj` and this iterator `IResultObj` is nothing but an object that contains two properties.

So let us copy this and the first property is a `value` property and this can be of any data type so this `value` is going to be the actual `value` within the collection.

And the second property is a `boolean` flag called done, so this done indicates if the iteration is complete or not complete.

So if done is true the iteration is complete.

```javascript
Iterable {
  [Symbol.iterator()]: Iterator
}

Iterator{
  next(): IResultObj
}

IResultObj{
  value: any
  done: bool
}
```

If it is false then there are more elements to be iterated over.

As we already mentioned in ES6 array, strings, maps and sets are all iterables but to understand better about iterators let's create our own iterator that works with arrays.

Let's go over here and let's create a new array and call this iterable then create our iterator, now it's going to be a function and let's name it `createIterator` and this is going to accept an array and let's have a count variable that we used to iterate or keep track of each element within the array.

```javascript
let iterable = [1, 2, 3];

function createIterator(array) {
  let count = 0;
  return {
    next: function () {
      return count < array.length?
      {value: array[count++], done:false};
    },
  };
}
```

And if you see over here an iterator this contains a `next` method so it's going to return something and that is a `next` method so this `next` is going to be a function. And it's going to return this result object.

Now there are two conditions while returning this object.

If the count of the array or the current count is less than `array.length` then we are going to return the value is going to be an array of count, but we also need to move on to the `next` element so `count++` and `done` is going to be false.

So the count is less than `array.length` which means to say that we have more elements that need to be iterated. We are not yet done with the iteration and if the count is equal to or greater than `array.length` that means we have hit the end of our iteration. So we are going to be returning value `undefined` and `done` true.

Now let us create `let myIterator` and assign it to the function so `createIterator` and pass the iterable array.

We have a reference to this function and by making use of the `next` method we can iterate through each of these elements.

```javascript
let iterable = [1, 2, 3];

function createIterator(array) {
  let count = 0;
  return {
    next: function () {
      return count < array.length
        ? { value: array[count++], done: false }
        : { value: undefined, done: true };
    },
  };
}

let myIterator = createIterator(iterable);
console.log(myIterator.next());

//output - { value: 1, done: false }
```

We are getting an object `value` is one and `done` as false so the first element. If we repeat this two more times;

```javascript
let iterable = [1, 2, 3];

function createIterator(array) {
  let count = 0;
  return {
    next: function () {
      return count < array.length
        ? { value: array[count++], done: false }
        : { value: undefined, done: true };
    },
  };
}

let myIterator = createIterator(iterable);
console.log(myIterator.next());
console.log(myIterator.next());
console.log(myIterator.next());

//output - { value: 1, done: false }
//output - { value: 2, done: false }
//output - { value: 3, done: false }
```

And we get value two three and we are not yet done with the iteration and finally when we call this again;

```javascript
let iterable = [1, 2, 3];

function createIterator(array) {
  let count = 0;
  return {
    next: function () {
      return count < array.length
        ? { value: array[count++], done: false }
        : { value: undefined, done: true };
    },
  };
}

let myIterator = createIterator(iterable);
console.log(myIterator.next());
console.log(myIterator.next());
console.log(myIterator.next());
console.log(myIterator.next());

//output - { value: 1, done: false }
//output - { value: 2, done: false }
//output - { value: 3, done: false }
//output - { value: undefined, done: true }
```

We get value `undefined` and we are `done` with the iteration. This functionality in fact is what the `for...of` loop uses it internally calls
the `next` method until this `done` is true.

So until the iteration is completed it keeps calling this `next` method and that is how it iterates through the elements of a collection.

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

### Iterating Objects:

If we have an object say `person` with the first name and last name as the properties and when we try to use a `for...of`loop;

```javascript
let person = {
  fname: 'Sunil',
  lname: 'Pradhan',
};

for (let p of person) {
  console.log(p);

//output - TypeError: person is not iterable
```

So the `for...of` loop doesn't work with objects by default.

```javascript
let person = {
  fname: 'Sunil',
  lname: 'Pradhan',
};

for (let p of person) {
  console.log(p);
}

person[Symbol.iterator] = function () {
  let properties = Object.keys(person);
  let count = 0;
  let isDone = false;
  let next = () => {
    if (count >= properties.length) {
      isDone = true;
    }
    return { done: isDone, value: this[properties[countK++]] };
  };
  return { next };
};

//output - TypeError: person is not iterable
```

So we start off by defining a function at the key `Symbol.iterator` for this person object so our first line is going to be a person of `Symbol.iterator` is equal to a function.

And this function we start off by declaring three variables that we are going to be making use of in this `next` method.

So initially we are going to have the properties equal to object keys and pass this person object. So properties is going to contain first name and lastname.

And then we have a count variable initialized to zero to keep track of the count and we also have `isDone` variable which is going to be boolean and set to `false` and that is going to indicate if the iteration is complete or not.

At the key `Symbol.iterator` implements a `next` function which returns an object so what this `next` function is going to do is if the count is greater than the number of property for the person object it is going to say `isDone` equals true, which means that the iteration is complete.

And then we are going to return `done` is going to be the same as `isDone` variable, it's going to be the true or false and the `value` is going to be for this object the property add count or the value at this particular property so the property the value at first name and value at last name.

```javascript
let person = {
  fname: 'Sunil',
  lname: 'Pradhan',
};

person[Symbol.iterator] = function () {
  let properties = Object.keys(person);
  let count = 0;
  let isDone = false;
  let next = () => {
    if (count >= properties.length) {
      isDone = true;
    }
    return { done: isDone, value: this[properties[count++]] };
  };
  return { next };
};

for (let p of person) {
  console.log(p);
}

//output - Sunil
//output - Pradhan
```

That is how you use objects with the `for...of` loop, you need to define your own method at `Symbol.iterator` key.

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

<a name="js-generators"></a>

## Generators

We know about function that once they start executing it will always run to completion before any other code can run, however ES6 generator is a special type of function which can be paused in the middle of execution run some other code and then resume the same function from where we left off.

And this pausing of execution is possible with the help of a new keyword known as the `yield` keyword.

So let's understand this with an example now the syntax of a generator is very much alike a function so we just have the function keyword but the only differences after the function keyword we have an asterisk.

Syntax:

```javascript
function *
```

So function asterisk and then name of the function, so let's have create generator as the name and this is going to you make use
of this `yield` keyword.

```javascript
function* createGenerator() {
  yield 1;
  console.log('After 1st yield');
  yield 2;
}
```

After first `yield` and then we are also going to have `yield` two. So what we are basically doing here is that in this generator first we are going to `yield` the value one and then the execution is going to pause and the generator is going to resume its execution when we again tell it to continue its execution.

Then it's going to execute these two lines of code, so `console.log` as well as `yield` two. So basically with every execution it is going to hit the next `yield` point.

This is going to be the point where this function is going to pause.So now we can create a reference to this generator.

```javascript
function* createGenerator() {
  yield 1;
  console.log('After 1st yield');
  yield 2;
}

let myGen = createGenerator();
```

Let `myGen= createGenerator()`, and this is going to provide an reference and it's not going to start executing this function.

Now to invoke this function or start execute we need to call the `next` method on the generator so `myGen.next()`.

```javascript
function* createGenerator() {
  yield 1;
  console.log('After 1st yield');
  yield 2;
}

let myGen = createGenerator();
console.log(myGen.next());

//output - { value: 1, done: false }
```

We are provided with an object the value is one and done this boolean flag set default and this is very much like what we saw with iterators.

So over here the only difference is that done will be set to false when it reaches the last yield statement or there are no more yield statements in this generator.

So we can call this again so let's call it twice and more.

```javascript
function* createGenerator() {
  yield 1;
  console.log('After 1st yield');
  yield 2;
}

let myGen = createGenerator();
console.log(myGen.next());
console.log(myGen.next());
console.log(myGen.next());

//output - { value: 1, done: false }
//output - After 1st yield
//output - { value: 2, done: false }
//output - { value: undefined, done: true }
```

So object value one done false so that was called after this first next method and the execution was paused.

And then these two lines were executed for the next method so we have after first yield an object value - done false.

And finally when we call this next method again it identifies that there are no more yield statements and hence done is set to true and the value is undefined.

So only when there are no more yields done is set to true and the value is undefined **so basically generator is a special function capable of pausing and resuming execution with the help of this yield keyword.**

Now if you look here a generator returns an object that provides the same next method that is expected by a `for...of` loop. So generators can be used to simplify our code when we write our custom iterators.

```javascript
let person = {
  fname: 'Chandler',
  lname: 'Bing',
};

person[Symbol.iterator] = function () {
  let properties = Object.keys(person);
  let count = 0;
  let isDone = false;
  let next = () => {
    if (count >= properties.length) {
      isDone = true;
    }
    return { done: isDone, value: this[properties[count++]] };
  };
  return { next };
};

for (let p of person) {
  console.log(p);
}
```

To iterate over a simple object and instead of having to write so much of code we can use a generator to simplify this and we can replace it.

```javascript
let person = {
  fname: 'Sunil',
  lname: 'Pradhan',
};

person[Symbol.iterator] = function* () {
  let properties = Object.keys(person);
  for (let t of properties) {
    yield this[t];
  }
};

for (let p of person) {
  console.log(p);
}

//ouput - Sunil
//output - Pradhan
```

So over here the person `Symbol.iterator` remains the same and we obtained all the properties but from then on so count is done an implementation of the next method all that is handled by this generator so we replaced function by just a function as tricks and properties remains the same.

And now since we have a collection of properties we can use a `for..of` loop let `t` of properties and then yield is going to be made use of.

So this is going to yield each key and we are going to be making use of the value at each key. So this is basically yield first name and yield last name.

This is one really useful feature of generator to be made use when we write our custom iterators.

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

<a name="js-sets-maps"></a>

## Sets & Maps

### JavaScript Sets

A set is nothing but a list of values but this list cannot contain any duplicates. Unlike arrays where we access the individual elements in sets we just check if a value is present or not we don't really access the value.

:bulb: **TIP:** A set is a data structure which contains a list of values that are unique.
<br>

So to create a new set we need to follow the following pattern:

```javascript
let mySet = new Set();
```

Now once we have a new set we can add elements to the set by calling the `add()` method on the set.

Now to check the size of the set or how many elements are present in the set we use the `size` property.

```javascript
let mySet = new Set();
mySet.add('Hello');
console.log(mySet.size);

//output - 1
```

The values we store in a set are not restricted to string values so we can have also a numeric value.

```javascript
let mySet = new Set();

mySet.add('Hello');
mySet.add(1);
console.log(mySet.size);

//output - 2
```

Let's try to add the same value again;

```javascript
let mySet = new Set();

mySet.add('Hello');
mySet.add(1);
mySet.add(1);
console.log(mySet.size);

//output - 2
```

Its size still remains 2. So a set can only contain unique values that means when you try to insert or add a duplicate value it is going to ignore that particular value.

Now let's create two new objects.

```javascript
let mySet = new Set();
let ob1 = {};
let ob2 = {};

mySet.add('Hello');
mySet.add(1);

console.log(mySet.size);
```

But when we try to add `mySet.add(ob1)` and `mySet.add(ob2)` we get the result of 4.

```javascript
let mySet = new Set();
let ob1 = {};
let ob2 = {};

mySet.add('Hello');
mySet.add(1);

mySet.add(ob1);
mySet.add(ob2);
console.log(mySet.size);

//output - 4
```

Here we are getting the result 4 because objects are not converted to strings the two objects will be unique.

We can also initialize values using an array during the creation of a set.

```javascript
let mySet = new Set();
let ob1 = {};
let ob2 = {};

mySet.add('Hello');
mySet.add(1);

mySet.add(ob1);
mySet.add(ob2);
console.log(mySet.size);

let newSet = new Set([1, 2, 3, 4, 4, 4]);
console.log(mySet.size);

//output - 4
//output - 4
```

The first four values were unique and were saved into new set but the last two values were duplicate values and were ignored. So that is how the size of new set is 4.

You can also change the add method to add elements to a set so we can have:

```javascript
let mySet = new Set();
let ob1 = {};
let ob2 = {};

mySet.add('Hello');
mySet.add(1);

mySet.add(ob1);
mySet.add(ob2);
console.log(mySet.size);

let newSet = new Set([1, 2, 3, 4, 4, 4]);
console.log(mySet.size);

let chainSet = new Set().add('Hello').add('World');
console.log(chainSet.size);

//output - 4
//output - 4
//output - 2
```

So when we log to the console `chainSet.size` should have two.

To check for existence of a value in a set we use the `has` method. So we are here a newSet, let's see if the value 1 is present or not.

```javascript
let mySet = new Set();
let ob1 = {};
let ob2 = {};

mySet.add('Hello');
mySet.add(1);

mySet.add(ob1);
mySet.add(ob2);
console.log(mySet.size);

let newSet = new Set([1, 2, 3, 4, 4, 4]);
console.log(mySet.size);

let chainSet = new Set().add('Hello').add('World');
console.log(chainSet.size);
console.log(newSet.has(1));

//output - 4
//output - 4
//output - 2
//output - true
```

As we use `has` method to check for an existence of a value similarly to delete a value from a set we use the `delete` method. So let's delete the value 1.

Initially it was 4 now we are deleting an element so the new size should be 3.

```javascript
let mySet = new Set();
let ob1 = {};
let ob2 = {};

mySet.add('Hello');
mySet.add(1);

mySet.add(ob1);
mySet.add(ob2);
console.log(mySet.size);

let newSet = new Set([1, 2, 3, 4, 4, 4]);
console.log(mySet.size);

let chainSet = new Set().add('Hello').add('World');
console.log(chainSet.size);
console.log(newSet.delete(1));
console.log(newSet.size);

//output - 4
//output - 4
//output - 2
//output - true
//output - 3
```

In a nutshell, we create a `set` using `new` and then we can add using `add` method. We can check for an existence using the `has` method and delete using the `delete` method and the size of the set can be found out using the `size` property.

#### WeakSets

On the last section you saw the set type but it can also be called as a strong set because of the way in which it stores object references.

So let's try to understand with an example. Let's first create a new set.

```javascript
let mySet = new Set();
```

We are also going to have an object so `let key` is equal to a pair of curly braces and let's try to `add` that.

```javascript
let mySet = new Set();
let key = {};
mySet.add(key);

console.log(mySet.size);

//output - 1
```

Now we are going to set key is equal to null and then log the size again.

```javascript
let mySet = new Set();

let key = {};
mySet.add(key);
console.log(mySet.size);

key = null;
console.log(mySet.size);

//output - 1
//output - 1
```

So what we can conclude from the above example is that even though the key was set to null.

A reference to the key object still existed in our set and we can just as easily retrieve it by saying `key` is equal to the spread operator on `mySet` and we can have of 0.

```javascript
let mySet = new Set();

let key = {};
mySet.add(key);
console.log(mySet.size);

key = null;
console.log(mySet.size);

key = [...mySet][0];

//output - 1
//output - 1
```

This is going to give us that object back. And what sometimes to aid with garbage collection and avoid memory leaks we would prefer that the reference in a `set` to disappear when all other references disappear.

And for this purpose ES6 introduced, WeakSets. A weak set is very much like a strong set.

It has the `add`, `has`, `delete` method but two main differences are it can store only object references and not primitive values and the object references are weak.

So if all other references are removed then a WeakSets allows
for garbage collection.

Now to create a WeakSets;

```javascript
let set = new WeakSet();
let key = {};
set.add(key);
console.log(set.has(key));

//output - true
```

So `key` is a value in this `set`, now when we have `key` is equal to `null` and when we run this code the reference to key in the WeakSets is no longer accessible.

```javascript
let set = new WeakSet();
let key = {};
set.add(key);
console.log(set.has(key));
key = null;

//output - true
```

And the funny thing here is, it is not even possible to verify if the reference is removed because we need at least one reference to this object to pass in the `has` method.

So we just have to put our faith in the JavaScript engine.

The only advantage of WeakSets over a strong set is memory is handled properly with WeakSets.

So let's say if we have to only track the references the object and nothing more than that then a WeakSets should be preferred over
a strong set.

### JavaScript Maps

A map is nothing more than a collection of key value pairs.

Unlike sets where we check if a value exists or not, with maps we actually want to retrieve the value.

In maps both the key and the value can be of any type unlike objects where the type of the property is always a string.

To create a new map;

```javascript
let myMap = new Map();
```

To add an item we use the `set` method, so `myMap.set` and within parentheses we specify the key value pair.

```javascript
let myMap = new Map();

myMap.set('fname', 'Sunil');
```

We can also have numeric values too;

```javascript
let myMap = new Map();

myMap.set('fname', 'Sunil');
myMap.set('age', 18);
```

To retrieve a value we need to use the `get` method.

```javascript
let myMap = new Map();

myMap.set('fname', 'Sunil');
myMap.set('age', 18);

console.log(myMap.get('fname'));
console.log(myMap.get('age'));

//output - Sunil
//output - 18
```

We can also use objects as keys within a map;

```javascript
let myMap = new Map();

myMap.set('fname', 'Sunil');
myMap.set('age', 18);

console.log(myMap.get('fname'));
console.log(myMap.get('age'));

let ob1 = {};
let ob2 = {};

myMap.set(ob1, 10);
myMap.set(ob2, 20);

console.log(myMap.get(ob1));
console.log(myMap.get(ob2));

//output - Sunil
//output - 18

//output - 10
//output - 20
```

We can also use the `size` property to know how many key value pairs are present in a particular map.

```javascript
let myMap = new Map();

myMap.set('fname', 'Sunil');
myMap.set('age', 18);

console.log(myMap.get('fname'));
console.log(myMap.get('age'));

let ob1 = {};
let ob2 = {};

myMap.set(ob1, 10);
myMap.set(ob2, 20);

console.log(myMap.get(ob1));
console.log(myMap.size);

//output - Sunil
//output - 18

//output - 10
//output - 4
```

We can also use the `has` method to check if a key exists in a map.

```javascript
let myMap = new Map();

myMap.set('fname', 'Sunil');
myMap.set('age', 18);

console.log(myMap.get('fname'));
console.log(myMap.get('age'));

let ob1 = {};
let ob2 = {};

myMap.set(ob1, 10);
myMap.set(ob2, 20);

console.log(myMap.get(ob1));
console.log(myMap.size);
console.log(myMap.has('fname'));

//output - Sunil
//output - 18

//output - 10
//output - 4
//output - true
```

It returns `true` so if it did not exist it was going to return `false`.

Now we can also have a `delete` method to remove a key value pair.

```javascript
let myMap = new Map();

myMap.set('fname', 'Sunil');
myMap.set('age', 18);

console.log(myMap.get('fname'));
console.log(myMap.get('age'));

let ob1 = {};
let ob2 = {};

myMap.set(ob1, 10);
myMap.set(ob2, 20);

console.log(myMap.get(ob1));
myMap.delete('fname');

console.log(myMap.size);
console.log(myMap.has('fname'));

//output - Sunil
//output - 18

//output - 10
//output - 3
//output - false
```

So the number of elements or key value pairs was reduced by one and we don't have `fname` in the map anymore.

For this it has returned `false` and finally we have a `clear` method that removes all the key value pairs from a map.

```javascript
let myMap = new Map();

myMap.set('fname', 'Sunil');
myMap.set('age', 18);

console.log(myMap.get('fname'));
console.log(myMap.get('age'));

let ob1 = {};
let ob2 = {};

myMap.set(ob1, 10);
myMap.set(ob2, 20);

console.log(myMap.get(ob1));
myMap.delete('fname');
myMap.clear();

console.log(myMap.size);
console.log(myMap.has('fname'));

//output - Sunil
//output - 18

//output - 10
//output - 0
//output - false
```

#### Iterating over Maps

There is another way to add key value pairs to a map and that is by using arrays doing map initialization.

So we can have `let myMap` is equal to `new Map` but this time within parentheses we can specify an array. As a result this array is going to contain more arrays in turn.

```javascript
let myMap = new Map([
  ['fname', 'Sunil'],
  ['lname', 'Pradhan'],
]);
```

Now that we have a new map. Let's see now how to iterate over this map.

If we need to iterate only the keys of the map then we make use of map keys method in a `for..of` statement.

```javascript
let myMap = new Map([
  ['fname', 'Sunil'],
  ['lname', 'Pradhan'],
]);

for (let key of myMap.keys()) {
  console.log(key);
}

//output - fname
//output - lname
```

These are just the keys and similarly if we need only the values then we make use of my map dot values.

```javascript
let myMap = new Map([
  ['fname', 'Sunil'],
  ['lname', 'Pradhan'],
]);

for (let value of myMap.values()) {
  console.log(value);
}

for (let key of myMap.keys()) {
  console.log(key);
}

// output - Sunil
// output - Pradhan

// output - fname
// output - lname
```

But if you need both the key and value then we make use of `myMap.entries()`.

So for we can have let and entry of my map dot entries and in console dot log let's make use of backticks.

```javascript
let myMap = new Map([
  ['fname', 'Sunil'],
  ['lname', 'Pradhan'],
]);

for (let entry of myMap.entries()) {
  console.log(`${entry[0]} -> ${entry[1]}`);
}

//output - fname -> Sunil
//output - lname -> Pradhan
```

We can also make use of destructuring for the same cause;

```javascript
let myMap = new Map([
  ['fname', 'Sunil'],
  ['lname', 'Pradhan'],
]);

for (let [key, value] of myMap.entries()) {
  console.log(`${key} -> ${value}`);
}

//output - fname -> Sunil
//output - lname -> Pradhan
```

#### WeakMaps

In WeakMaps the keys can only be object and the object references are weak, meaning they don't interfere with the garbage collection.

Now to create a WeakMaps we say;

```javascript
let myMap = new WeakMap();
```

We can also have an object that we are going to be using as a key and then we can add this key value pair.

```javascript
let myMap = new WeakMap();
let ob1 = {};
myMap.set(ob1, 'Hello World');
console.log(myMap.get(ob1));

//ouput - Hello World
```

Now let us add `ob1` is equal to `null`, at this point the WeakMap is empty and there is no way really to verify this.

```javascript
let myMap = new WeakMap();
let ob1 = {};
myMap.set(ob1, 'Hello World');
console.log(myMap.get(ob1));
ob1 = null;

//ouput - Hello World
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

<a name="js-map-method"></a>

## Map method

By Map method we can quickly iterate over an array and return a new array with the desired changes applied.

Definition: _The map() method creates a new array populated with the results of calling a provided function on every element in the calling array._

Example:

```javascript
const array1 = [1, 4, 9, 16];

// pass a function to map
const map1 = array1.map((x) => x * 2);

console.log(map1);
// expected output: Array [2, 8, 18, 32]
```

Here we have an array of numbers then we call the map method on the array.

The map method accepts a function as an argument and of course what you see here is an arrow function. There is one parameter called "x" and in the function body we return x multiply by 2.

The entire operation is then assigned to a variable called `map1` which is then log to the console.

If we run this code you get the expected output i.e`[2, 8, 18, 32]`.

So what the map method does is go over each element in the array and apply a transformation specified in the function body.

In our example we have an array of four numbers so the transformation function is executed once for each of the four numbers.

On first execution the parameter "x" will contain a value of 1 it is
transformed to 1 multiplied by 2 which is 2, which you can see here in the output.

Second execution we have "x" is equal to 4 which is transformed to 4
into 2 which is 8 and similarly 9 into 2 which is 18 and 16 into 2 which is 32.

So we have a list of numbers and we are able to return a list of numbers after applying some transformation using the map method.

###### Reference

- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

<a name="js-promises"></a>

## JavaScript Promises

A promise is an object that may produce a single value some time in the future: either a resolved value, or a reason that it’s not resolved (e.g., a network error occurred).

A promise may be in one of 3 possible states: fulfilled, rejected, or pending.

**How Promises work**

It will be in one of 3 possible states:

- Fulfilled
- Rejected
- Pending

A promise is **settled** if it’s not pending (it has been resolved or rejected). Sometimes people use resolved and settled to mean the same thing: not pending.

Once settled, a promise can not be resettled. The immutability of a settled promise is an important feature.

Example:

```javascript
function func1() {
  return new Promise(function (resolve, reject) {
    setTimeout(() => {
      const error = true;
      if (!error) {
        console.log('Function: Your promise has been resolved');
        resolve();
      } else {
        console.log('Function: Your promise has not been resolved');
        reject('Sorry not fulfilled');
      }
    }, 2000);
  });
}
func1()
  .then(function () {
    console.log('Sunil!! - Thanks for resolving');
  })
  .catch(function (error) {
    console.log('Sunil!! - Very bad bro. Reason: ' + error);
  });

//output: 

//Function: Your promise has not been resolved
//Sunil!! - Very bad bro. Reason: Sorry not fulfilled
```

JavaScript Promises are better substitute of callback funtion.

###### References

- https://medium.com/javascript-scene/master-the-javascript-interview-what-is-a-promise-27fc71e77261
- https://www.youtube.com/watch?v=2IPw-mWe10U

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

<a name="async-await"></a>

## JavaScript Async/Await

Async and Await are extensions of promises.

#### Async

Async functions enable us to write promise based code as if it were synchronous, but without blocking the execution thread. It operates asynchronously via the event-loop.

Async functions will always return a value. Using async simply implies that a promise will be returned, and if a promise is not returned, JavaScript automatically wraps it in a resolved promise with its value.

Example:

```javascript
async function firstAsync() {
  return 27;
}

firstAsync().then(alert); // 27
```

Running the above code gives the alert output as 27, it means that a promise was returned, otherwise the .then() method simply would not be possible.

#### Await

The await operator is used to wait for a Promise. It can be used inside an Async block only. The keyword Await makes JavaScript wait until the promise returns a result.

It has to be noted that it only makes the async function block wait and not the whole program execution.

The code block below shows the use of Async Await together.

Example:

```javascript
async function firstAsync() {
  let promise = new Promise((res, rej) => {
    setTimeout(() => res("Now it's done!"), 1000);
  });

  // wait until the promise returns us a value
  let result = await promise;

  // "Now it's done!"
  alert(result);
}
firstAsync();
```

###### References

- https://javascript.info/async-await
- https://medium.com/javascript-in-plain-english/async-await-javascript-5038668ec6eb
- https://www.youtube.com/watch?v=AyJq1RRaY_k

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

<a name="js-oop"></a>

## Object Oriented Programming - OOP

Object oriented programming (OOP) is a programming language model organized around objects rather than “actions” and data rather than logic.

Four pillar of OOPS: Encapsulation, abstraction, inheritance,polymorphism

**Encapsulation:**

It encapsulates your data.

**Abstraction:**

Which is important only to show that much and rest needs to hide it.

**Inheritance:**

Inheritance means something you receive from your ancestry.

**Polymorphism:**

polymorphism means you are writing a single function() but it works differently for different situations.

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

<a name="js-dom"></a>

## Document Object Model - DOM

The Document Object Model (DOM) is a programming API for HTML and XML documents. With the HTML DOM, JavaScript can access and change all the elements of an HTML document.

The DOM model represents a document with a logical tree. According to DOM model every HTML-tag is an object, Nested tags are called “children” of the enclosing one.

All operations on the DOM start with the document object. From it can access any node.

###### Reference

- https://www.w3schools.com/js/js_htmldom.asp
- https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction
- https://www.w3.org/TR/WD-DOM/introduction.html

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

### Document tree in JavaScript:

Browser understands your code in following format;

![js-dom-tree](/img/js-dom-tree.png)

- Any element is called an **Element node** in JavaScript
- If you see any text then it would be called a **Text node**
- For attribute it will be called as **Attribute node**
- For comment - **Comment node**

**DOM node types**

Total 12 but 7 is only important

![js-dom-node-type](/img/js-dom-node-type.png)

**Node relationship:**

![js-dom-node-type](/img/js-node-relationship.png)

- Parent (eg: html)
- Children (eg: head)
- First child (eg: h1)
- Previous sibling (br -> h1)
- Next Sibling (h1 -> br)
- Last child (ul)

### Element Access Methods

![js-element-access-methods](/img/js-element-access-methods.png)

#### getElementByID(“ID_Name”)

The `getElementById()` method returns the element that has the ID attribute with the specified value.

In other words, if something presents uniquely in your document through ID then you can use this method to manipulate it.

:bulb: **TIP:** In browser `document` is the main object.

###### Reference

- https://www.w3schools.com/jsref/met_document_getelementbyid.asp
- https://www.javatpoint.com/document-getElementById()-method
- https://www.tutorialspoint.com/how-getelementbyid-works-in-javascript
- https://www.geeksforgeeks.org/html-dom-getelementbyid-method/

Example:

```html
<body>
  <p id="demo-id-one">Hello Sunil</p>
  <p id="demo-id-two">Bye Sunil</p>

  <script>
    //getElementByID()
    var result = document.getElementById('demo-id-one');
    document.write(result);
    console.log(result);
  </script>
</body>
```

```
output - [object HTMLParagraphElement] (on screen)

output - <p id="demo-id-one">Hello Sunil</p> (on console)
```

#### getElementsByTagName(“Tag_Name”)

`getElementsByTagName(“Tag_Name”)` method returns all the element of specified tag name.

- This method accepts a string indicating the type of elements that can be retrieved, a special value **“\*”** returns all elements in the documents.
- You can use the **length** property of the Node List object to determine the number of elements with the specified tag name, then you can loop through all elements and extract the info you want.

###### Reference

- https://www.javatpoint.com/document-getElementsByTagName()-method
- https://www.geeksforgeeks.org/html-dom-getelementsbytagname-method/
- https://www.w3schools.com/jsref/met_document_getelementsbytagname.asp

Example(return collection):

```html
<body>
  <div>
    <p>1st p inside div</p>
    <p>2nd p inside div</p>
  </div>

  <script>
    var result = document.getElementsByTagName('p');
    document.write(result);
    console.log(result);
  </script>
</body>
```

```
output - [object HTMLCollection] (on screen)

output - HTMLCollection(2) [p, p] (on console)

```

Example(return all):

```html
<body>
  <div>
    <p>1st p inside div</p>
    <p>2nd p inside div</p>
  </div>

  <script>
    var result = document.getElementsByTagName('*');
    document.write(result);
    console.log(result);
  </script>
</body>
```

```
output - [object HTMLCollection] (on screen)

output - HTMLCollection(10) [html, head, meta, meta, title, body, div, p, p, script, viewport: meta] (on console)

```

It returns every element whatever present on the webpage.

If you do not want to return entire document rather only want to know inside the body tag then try using:

```html
<body>
  <div>
    <p>1st p inside div</p>
    <p>2nd p inside div</p>
  </div>

  <script>
    var result = document.body.getElementsByTagName('*');
    document.write(result);
    console.log(result);
  </script>
</body>
```

```
output - [object HTMLCollection] (on screen)

output - HTMLCollection(4) [div, p, p, script] (on console)

```

If you do not want a collection of list but want a single value then you need to access it via index number.

**More Specific:**

```html
<body>
  <h1>We are learning DOM</h1>
  <h1>Subscribe</h1>
  <h2>Now</h2>
  <p id="geek">
    Hello
    <span>Sunil</span>
    <em>World</em>
    <span>YouTube</span>
  </p>
  <p id="find"><span>Bye</span>Sunil</p>
  <div>
    <p>1st p inside div</p>
    <p>2nd p inside div</p>
  </div>

  <script>
    //more specific :: Need only geek span
    var result = document.getElementById('geek').getElementsByTagName('span');
    console.log(result);
  </script>
</body>
```

```
output - HTMLCollection(2) [span, span] (on console)
```

**Using length property:**

```html
<body>
  <h1>We are learning DOM</h1>
  <h1>Subscribe</h1>
  <h2>Now</h2>
  <p id="geek">
    Hello
    <span>Sunil</span>
    <em>World</em>
    <span>YouTube</span>
  </p>
  <p id="find"><span>Bye</span>Sunil</p>
  <div>
    <p>1st p inside div</p>
    <p>2nd p inside div</p>
  </div>

  <script>
    //length
    var len = document.getElementsByTagName('p').length;
    console.log(len);
  </script>
</body>
```

```
output - 4 (on console)
```

**Looping:**

Gives you all paragraph.

```html
<body>
  <h1>We are learning DOM</h1>
  <h1>Subscribe</h1>
  <h2>Now</h2>
  <p id="geek">
    Hello
    <span>Sunil</span>
    <em>World</em>
    <span>YouTube</span>
  </p>
  <p id="find"><span>Bye</span>Sunil</p>
  <div>
    <p>1st p inside div</p>
    <p>2nd p inside div</p>
  </div>

  <script>
    //loop
    var len = document.getElementsByTagName('p').length;
    for (let i = 0; i < len; i++) {
      var result = document.getElementsByTagName('p')[i];
      console.log(result);
    }
  </script>
</body>
```

#### getElementsByClassName

The `getElementsByClassName()` method returns an object containing all the elements with the specified class names in the document as objects

Example:

```html
<body>
  <h1>We are learning DOM</h1>
  <h1>Subscribe</h1>
  <h2>Now</h2>
  <p class="geek">
    Hello
    <span>Sunil</span>
    <em>World</em>
    <span>YouTube</span>
  </p>
  <p class="myclass"><span>Bye</span>Sunil</p>
  <div>
    <p>1st p inside div</p>
    <p class="geek">2nd p inside div</p>
  </div>

  <script>
    //access geek element

    var result = document.getElementsByClassName('geek');
    console.log(result);
  </script>
</body>
```

```
output - HTMLCollection(2) [p.geek, p.geek] (on console)
```

If we need to access two classes then what ?

```html
<body>
  <h1>We are learning DOM</h1>
  <h1>Subscribe</h1>
  <h2>Now</h2>
  <p class="geek">
    Hello
    <span>Sunil</span>
    <em>World</em>
    <span>YouTube</span>
  </p>
  <p class="geek myclass"><span>Bye</span>Sunil</p>
  <div>
    <p>1st p inside div</p>
    <p class="geek">2nd p inside div</p>
  </div>

  <script>
    //access two class name
    var result = document.getElementsByClassName('geek myclass');
    console.log(result);
  </script>
</body>
```

```
output - HTMLCollection [p.geek.myclass] (on console)
```

**More Specific:**

```html
<body>
  <h1>We are learning JS</h1>
  <h1 class="geek myclass">Subscribe Geekyshows</h1>
  <h2>Now</h2>
  <p class="geek">
    Hello<span>Geekyshows</span> <em>World</em><span>Youtube</span>
  </p>

  <p class="myclass"><span>Bye</span>Geekyshows</p>
  <div id="show">
    <p>1st p inside div</p>
    <p class="geek">2nd p inside div</p>
  </div>
  <script>
    //more specific
    var getShow = document.getElementById('show');
    var result = getShow.getElementsByClassName('geek');
    console.log(result);
  </script>
</body>
```

```
output - HTMLCollection [p.geek] (on console)
```

**Using length property:**

```html
<body>
  <h1>We are learning JS</h1>
  <h1 class="geek myclass">Subscribe Geekyshows</h1>
  <h2>Now</h2>
  <p class="geek">
    Hello<span>Geekyshows</span> <em>World</em><span>Youtube</span>
  </p>

  <p class="myclass"><span>Bye</span>Geekyshows</p>
  <div id="show">
    <p>1st p inside div</p>
    <p class="geek">2nd p inside div</p>
  </div>
  <script>
    //length - find number of element of geek class
    var len = document.getElementsByClassName('geek').length;
    console.log(len);
  </script>
</body>
```

```
output - 3 (on console)
```

**Looping:**

```html
<body>
  <h1>We are learning JS</h1>
  <h1 class="geek myclass">Subscribe Geekyshows</h1>
  <h2>Now</h2>
  <p class="geek">
    Hello<span>Geekyshows</span> <em>World</em><span>Youtube</span>
  </p>

  <p class="myclass"><span>Bye</span>Geekyshows</p>
  <div id="show">
    <p>1st p inside div</p>
    <p class="geek">2nd p inside div</p>
  </div>
  <script>
    //for loop
    var data = document.getElementsByClassName('geek');
    var len = data.length;
    for (let i = 0; i < len; i++) {
      var result = document.getElementsByClassName('geek')[i];
      console.log(result);
    }
  </script>
</body>
```

#### querySelector(“CSS Selector”)

The method `querySelector()` returns the first Element match of the specified selector, or group of selectors. If no matches are found, null is returned.

**Example:**

**Element Selector:**

```html
querySelector('p') querySelector('p, h1')
```

**ID Selector:**

```html
querySelector('#show1') querySelector('#show, #show1')
```

**Class Selector:**

```html
querySelector('.geek') querySelector('p.myclass') querySelector('p >
span.myclass')
```

#### querySelectorAll(“CSS Selector”)

The querySelectorAll() method returns all elements in the document that matches a specified CSS selector, as a static NodeList object.

<hr>

<a name="com-res"></a>

##### Complementary Resources

When you struggle to understand a concept, I suggest you look for answers on the following resources:

- [MDN (Mozilla Developer Network)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
- [ES6 Features with examples)](http://es6-features.org/#Constants)
- [Reddit (JavaScript)](https://www.reddit.com/r/javascript/)
- [StackOverflow](https://stackoverflow.com/questions/tagged/javascript)
