# Chapter 1 . Introduction to JavaScript

- JavaScript language is programming language of the Web. 
- Node.js has enabled javascript to run outside web browsers. 
- JavaScript is a High-Level, Interpreted, Object-oriented and functional programming language.
- JavaScript is Dynamically Typed language.
- Java != JavaScript

## JavaScript History
- JS was created at Netscape
- Then Javascript was standerdized by ECMA(European Computer Manufacturer's Association), after standerdization, Javascript was given a new name called "**ECMAScript**" also called "**ES**"
- Till ES5 there were many bugs in this language, after ES6 these all bugs were fixed, many new features (like *class*, *modules*) were introduced. 
- To maintain backward compatibility, it's not possible to remove legacy features/error/bugs. In ES5 and newer versions, programs can be choosen to work with `strict mode` in which a number of early language mistakes have been fixed.
- When we use ES6 or newer features of language like `class` or `module` etc then it implicitly invokes `strict mode`, and in those contexts the legacy buggy features aren't available.
---

- To perform certain things like input/output every language must have a platform or standard library. 
- Core Javascript provided Minimal API to work with numbers, text, arrays, sets, maps etc. But it does not includes input/output functionality. 
- Input/output, networking, storage, graphics etc are features provided by "Host Environment" in which javaScript is embedded or running.
- The original JavaScript host environment was web browser, this environment provides feature to take input from user's mouse/keyboard and by sending an HTTP request. It allows JavaScript code to display output to the user by changing HTML and CSS.
- In 2010 another Host environment for JavaScript was created, it was Node. Node allow us to run JavaScript outside browser. 
	- Node enable JavaScript to access entire Operating System, enabled read/write of files, send and recieve data over network, and make and server HTTP requests. 
	- Node is populer to create web servers.
	- node can be downloaded from https://nodejs.org 
	- 

## Run JavaScript in Web Browser

- Open Browser
- F12 or `Ctrl Shift I`
- Select Console tab
```js
console.log("Hello world!!");
```

Runing javascript code this way is very in-efficient, so let's run JS using node.js

## Run JavaScript using Node

create a file with `.js` extension (js denotes JavaScript), eg. `app.js`
- write any code in app.js file
```js
console.log("Hello World!!");
console.log(2 * 3);
```
- Go to the folder where app.js is present
- Open that folder in `Terminal`
```bash
$node app.js
> Hello World!!
> 6
```

If we want to run JavaScript automatically when we run a HTML file, 
- Create `index.html` file
- Add below line in it
```html
<script src="app.js"></script>
```

On the Console you will see this output
```bash
Hello World!!
6
```

```js
// Javascript comment

// variable => symbolic name for a value stored by the program in the RAM

// variabls can be declared with let, var, const keywords

let x; // declare a variable with name x, no value is assigned yet

x = 10; // x is initialized with value 10, means now variable x stores value 10

x; // Other then assignment operation, whenever we use variable name, it get replaced by its value

x = 1; // reassignment of variable x with value 1, now x stores value 1

// There are many types in JavaScript
// Number => can be integer or float. eg. 1, 12.34
// String => sequence of characters delimited by single quotes('') or double quotes("") or backticks(``). eg. "Hello", 'hello hyy', `i am string.`
// Boolean => Only has two values true/false
// Null => only has one value `null`, this is a special value that means `no value`
// Undefined => only has one value `undefined`, it's given by default to those variables which are declared but not initialized.

// Object => most imp data type of JavaScript. It's an collection of name-value pairs, or a string to value map.
// Objects are enclosed inside { }, property name and value are separated by colon( : ) and multiple properties are seperated by comma (,)
let obj = {
  pName: "val_1",
  p2Name: "val_2",
};

// we can access property value using dot . or square bracket [ ] notation
obj.pName; // val_1
obj["p2Name"]; // val_2

// we can create new property 
obj.p3Name = "val_3";

// to access properties conditionally we use Optional chaining => ?.

```
