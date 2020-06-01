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
- [Variable Hoisting](#js-variable-hosting)
- [Rest & Spread Operator](#js-rest-spread)
- [Module - Import & Export](#js-module)
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
````

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

<hr>

<a name="com-res"></a>

##### Complementary Resources

When you struggle to understand a concept, I suggest you look for answers on the following resources:

- [MDN (Mozilla Developer Network)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
- [ES6 Features with examples)](http://es6-features.org/#Constants)
- [Reddit (JavaScript)](https://www.reddit.com/r/javascript/)
- [StackOverflow](https://stackoverflow.com/questions/tagged/javascript)
