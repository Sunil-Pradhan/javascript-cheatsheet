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
- [Operators](#js-operators)
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
var hello = 'world';
let bar = 'baz';
```

```javascript
// increment and decrement numbers
i++; // the equivalent of i = i + 1
i--; // the equivalent of i = i - 1;
```

<hr>

<a name="js-operators"></a>

## JavaScript Operators

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

Bitwise operators compare bit to bit.

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

![js-break-keyword](/img/js-break-keyword.png)

**`continue` - skip the loop:**

Example:

![js-continue-keyword](/img/js-continue-keyword.png)

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
