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
- [Variable Hoisting](#js-variable-hosting)
- [Rest & Spread Operator](#js-rest-spread)
- [Module - Import & Export](#js-module)
- [Destructuring - Array & Object](#js-destructuring)
- [Object Oriented Programming - OOP](#js-oop)
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

:bulb: **TIP:** The **Temporal Dead Zone(TDZ)** is never named explicitly in the ECMAScript specification, but the term is often used to describe why let and const bindings are not accessible before their declaration.

<br>

**Variable declaration:**

```javascript
// This is how you define a variable
// `x` will be `undefined`
var x;

// Declare a constant (the convention is to use CAPS for constants)
const PI = 3.14;

// Declare another two variables, using `var` and `let`
var firstName = 'Sunil';
let lastName = 'Pradhan';
```

**Re-declaring a JavaScript variable:**

If you re-declare a JavaScript variable, it will not lose its value.

```javascript
var x = 4;
var x;
console.log(x);

//Output - 4
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

:bulb: **TIP:** Memory allocation in Primitive data types happens in “Stack” whereas memory allocation in Reference data types happens in “Heap” (Dynamic memory).

<br>
<br>

The latest ECMAScript standard defines nine types:

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

The meaning of undefined is “value is not assigned”, that means if a variable is declared, but not assigned, then its value is undefined:

Example:

```javascript
var x;
console.log(typeof x);

//output - undefined
```

Without initialization we are trying to access it so that it throws us `undefined`.

**Condtion 1:** `undefined` when you declare a variable but not initialized a value and trying to access it then it will show you as `undefined`.

**Condtion 2:** Trying to access a variable which doesn’t even exist then it will show you an `undefined`.

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

:bulb: **TIP:** Difference between undefined and null in JavaScript

Undefined means the value has not been set, whereas null means the value has been set to empty.

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

### Typeof operator:

The typeof operator is used to get the data type of its operand. The operand can be either a literal or a data structure such as a variable, a function, or an object.

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
  // Statements to execute if
  // condition is true
}
```

Example:

![js-if-statement](/img/js-if-statement.png)

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

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

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

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

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

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

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### Switch statement

The switch statement chooses between multiple statements to execute based on possible values of a single expression. Each of these values in a switch statement is called a case.

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

:bulb: **TIP:** All the cases will be evaluated if you do not use a break statement.

Example: (Without default)

![js-switch-statement-without-default](/img/js-switch-statement-without-default.png)

Example: (With default)

![js-switch-statement-with-default](/img/js-switch-statement-with-default.png)

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

Example: In a week, if you have two days off then in that case you can use switch statements where you need to execute the same statement multiple times.

Example: (With multiple options)

![js-switch-statement-with-multiple-options](/img/js-switch-statement-with-multiple-options.png)

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### Conditional (Ternary) operator

Example: (By if statement)

![Conditional-ternary-operator-by-if-statement](/img/Conditional-ternary-operator-by-if-statement.png)

Example: (By ternary operator)

![js-conditional-ternary-operator-by-ternary-operator](/img/js-conditional-ternary-operator-by-ternary-operator.png)

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### Multiple conditional (Ternary) operators

Example: (By if statement)

![js-multiple-conditional-ternary-operator-by-if-statement](/img/js-multiple-conditional-ternary-operator-by-if-statement.png)

Example: (By ternary operator)

![js-multiple-conditional-ternary-operator-by-ternary-operator](/img/js-multiple-conditional-ternary-operator-by-ternary-operator.png)

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
- **do...while -** also loops through a block of code while a specified condition is true
- **for...in -** loops through the properties of an object
- **for...of -** loops through the values of an iterable object

#### for loop

The for loop is usually used where the loop will be repeated a fixed number of times.

**Type 1:**

Syntax:

```javascript
for (initialization condition; testing condition; increment/decrement)
{
    statement(s);
}
```

First for loop initialize a variable then enter into a test condition. If the condition is true then it will execute the block of statement After this step, it will reach at the end of the block `}` but before it goes to the second time looping, it increases one value with the help of an increment operator.

When the loop runs for a second time, it does not even look at the initialized variable because its job has been over.

When the test condition is false then it stops executing the statement.

Example:

![js-for-loop-type-one](/img/js-for-loop-type-one.png)

**Type 2:**

Example:

![js-for-loop-type-two](/img/js-for-loop-type-two.png)

Here you define a variable first but in for loop you are still keeping `;` at the initialize stage.

**Type 3:**

Example:

![js-for-loop-type-three](/img/js-for-loop-type-three.png)

**Type 4:**

Example:

![js-for-loop-type-four](/img/js-for-loop-type-four.png)

What it tells us. We have initialized a variable then we have our test condition within the if statement. It checks the condition upto equality 3 then it will break and exit from the loop.

#### Nested for loop

In nested for loop, you are using a for loop inside of another for loop.

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

![js-for-loop-nested](/img/js-for-loop-nested.png)

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

Default parameter values always come on last, otherwise it returns undefined. Once default value start then rest of parameters should be default value only.

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

Here we have passed two arguments so that after `a` and '`b`. It took the default value to show the result of '`c`, i.e 70.

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
function disp(a) {
  return function (b) {
    return a + b;
  };
}

var anoFun = disp(10);

console.log(anoFun(20));

//output - 30
```

**Pass in a function or Passing anonymous function as argument:**

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
- It is a design pattern which is also known as **Self-Executing Anonymous Function** and contains two major parts.
- The first is the anonymous function with lexical scope enclosed within the **Grouping Operator()**. This prevents accessing variables within the IIFE idiom as well as polluting the global scope.
- The second part is creating the **immediately executing function expression ()**, through which the JavaScript engine will directly interpret the function.

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

A callback function is a function which can be any function (Anonymous function, Arrow function) passed into another function as an argument, which is then invoked inside the outer function to complete some kind of action.

In other words, when you pass a function into another function as an argument then its called a **callback function**.

Call back function is of two types:

- Synchronous
- Asynchronous

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

**Example(Synchronous):**

It waits for each operation to complete, after that it executes the next operation.

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

It never waits for each operation to complete, rather it executes all operations in the first GO only.

```javascript
setTimeout(function show() {
  console.log('I am show function');
}, 5000);

console.log('End');

//output - End
//output - I am show function
```

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

#### Constructor as a Class in JavaScript

A specific category can be defined as class in JavaScript.

For example: Mobile is a category which can be considered as class in JavaScript. Inside the Mobile category many different brands can reside such as Nokia, Samsung, Apple and others.

We can define a class in JavaScript using a custom constructor.

Example:

```javascript
var Mobile = function (model_no, sprice) {
  this.model = model_no;
  this.color = 'white';
  this.price = 3000;
  this.sp = sprice;
  this.sellingprice = function () {
    return this.price + this.sp;
  };

  this.data = function () {
    console.log('Model no:' + this.model + ' Price: ' + this.sellingprice());
  };
};

var samsung = new Mobile('Galaxy', 2000);
samsung.data();

//output - Model no:Galaxy Price: 5000
```

Here `Mobile` is a class in JavaScript and then we create a object by using the `new` keyword.

Here `this` keyword points to the current object instance. That means;this.model is equal to samsung.model, here samsung is the current object instance.

When you creates any properties with the help of `this` keyword, then it would be public.

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### Private properties and method in JavaScript

Use `var` or `let` or `const` keyword to create private properties and methods.

Example:

```javascript
var Mobile = function (model_no, sprice) {
  this.model = model_no;
  this.color = 'white';
  var price = 3000; //private
  var show = function () {
    return 'Hello World';
  }; //private
};

var samsung = new Mobile('Galaxy', 2000);
console.log(samsung.model);
console.log(samsung.price);
console.log(samsung.show);

//output - Galaxy, undefined, undefined
```

<br/>
<div align="right">
    <b><a href="#javascript-cheatsheet">↥ back to top</a></b>
</div>
<br/>

#### Access private property from outside in JavaScript

If you want to access private property from outside then you need to use a public property or public methods.

Example:

```javascript
var Mobile = function (model_no, sprice) {
  this.model = model_no;
  this.color = 'white';
  var price = 3000;
  this.sp = sprice;
  this.SellingPrice = function () {
    return price;
  }; //now public
};

var samsung = new Mobile('Galaxy', 2000);
console.log(samsung.SellingPrice());

//output - 3000
```

The `SellingPrice` method can show you here the price of 3000 because it is now public with the help of this keyword. When we will call now it can show you the output.

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

The forEach loop calls a provided function once for each element in an array, in order.

Syntax:

```javascript
array.forEact(function (value, index, arr) {});
```

Where,

- value - It is the current value of array index and it's a variable so that you can name it anything like value, name or other.It is mandatory.
- index - Array's index number.Here also you can give any other name index, i or any other.It is not mandatory.
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

**Empty 2D Array: Using array literal**

**Method#1**

```javascript
var stu = [[], []];

for (let i = 0; i < 2; i++) {
  for (let j = 0; j < 3; j++) {
    console.log(i + ' || ' + j + ' ||');
  }
}

//output
//0 || 0 ||
//0 || 1 ||
//0 || 2 ||
//1 || 0 ||
//1 || 1 ||
//1 || 2 ||
```

This is not a good way to create an empty 2d array due, if you need to make 1000 empty arrays then you need to enter 1000 times `[] []`.

**Method#2**

```javascript
var stu = [];
var rows = 2;
var cols = 3;
for (var i = 0; i < rows; i++) {
  stu[i] = [];
}
for (var i = 0; i < rows; i++) {
  for (var j = 0; j < cols; j++) {
    console.log(stu[i][j] + ' ');
  }
}

//output -
//undefined
//undefined
//undefined
//undefined
//undefined
//undefined
```

This is how you can create empty arrays where later you can take input from the users too.

**Get input from user in 2D Array:**

```javascript
//define a 2d array
var rows = 3;
var cols = 2;
var stu = new Array(rows);
for (var i = 0; i < rows; i++) {
  stu[i] = new Array(cols);
}

//Input for array
for (var i = 0; i < rows; i++) {
  for (var j = 0; j < cols; j++) {
    stu[i][j] = prompt('Enter name: ');
  }
}

//Displaying value
for (var i = 0; i < rows; i++) {
  for (var j = 0; j < cols; j++) {
    document.write(i + ' ' + j + stu[i][j]);
  }
}
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

stu.fill('Manu', 1,3);

//fill Manu starting with index 1 to 3 but 3 not included
console.log(stu);

//output - [ 'Rahul', 'Manu', 'Manu', 'Raj', 'Raj' ]
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

So that's pretty much how you destructure works in JavaScript objects.

You have an object and then you use the curly braces and assign it to the object and each property name should match the variable name and then the value will get assigned to it.

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

<hr>

<a name="com-res"></a>

##### Complementary Resources

When you struggle to understand a concept, I suggest you look for answers on the following resources:

- [MDN (Mozilla Developer Network)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
- [ES6 Features with examples)](http://es6-features.org/#Constants)
- [Reddit (JavaScript)](https://www.reddit.com/r/javascript/)
- [StackOverflow](https://stackoverflow.com/questions/tagged/javascript)
