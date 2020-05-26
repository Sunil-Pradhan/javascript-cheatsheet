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
