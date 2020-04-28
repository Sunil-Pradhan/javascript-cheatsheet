 <p align="center">
  <img width="256" height="256" src="/img/JavaScript_logo_large.png">
</p>

<h1 align="center">JavaScript Cheatsheet</h1>

This document is a cheatsheet for JavaScript you will frequently encounter in modern projects and most contemporary sample code.


## Table of Contents

* [JavaScript Comments](#js-commet)
* [Data types](#js-datatypes)
* [Variables](#js-variables)
* [Complementary Resources](#com-res)



<a name="js-commet"></a>
## Comments

Single line comments start with `//`. For multi-line commands, you use `/* ... */`.

```javascript
// This is a single line comment

/*
 And this is
 a multi-line
 comment
 */
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


    demo      | Scope    | Reassignable     | Temporal Dead Zone
------------ | ------------------------------------------------
**const**    | Block    | No               | Yes
------------ | ------------------------------------------------
**let**      | Block    | Yes              | Yes
------------ | ------------------------------------------------
**var**      | Function | Yes              | No


First Header | Second Header
------------ | -------------
Content from cell 1 | Content from cell 2
Content in the first column | Content in the second column


<hr>

<a name="com-res"></a>
##### Complementary Resources

When you struggle to understand a concept, I suggest you look for answers on the following resources:


* [MDN (Mozilla Developer Network)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
* [ES6 Features with examples)](http://es6-features.org/#Constants)
* [Reddit (JavaScript))](https://www.reddit.com/r/javascript/)
* [StackOverflow)](https://stackoverflow.com/questions/tagged/javascript)