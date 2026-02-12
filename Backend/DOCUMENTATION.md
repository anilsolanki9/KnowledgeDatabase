Frontend => Browser /Client Side
Backend => Server side

Backend Handles => APIs, Databases, Authentication, Business logics, Server-side validation
# Node.js

Using Node.js we can run JavaScript outside browser environment. 
- Node.js is a JavaScript Runtime Environment. It let us use JavaScript outside the browser, mainly on servers. 
- With Node.js Javascript can be used to
	- Create **Servers**
	- handle **API**s (HTTP Requests)
	- Conect to **Database**, and Handle Databases
	- **Read/Write** Files
	- **Real-time** apps (Chat, Live updates)
	- Perform Background tasks (Code execution at server)
	- Microservices
	- build CLI (Command Line Interface) tools. (Handling commands and aruments)
- `Note` :- DOM, Window, document, localStorage, `alert()` etc. are provided by browser environment and do not exist in node.js environment.

## What engine does Node.js use

Node.js uses `V8 Engine`, Created by **Google**, written in *C++*. V8 engine is also used in **Google Chrome**.
V8 engine uses JIT(Just-In-Time) compilation.

## Check if node.js is installed or not

```bash
node -v
```
## Run a javascript file (eg. app.js) using Node.js

```bash
node app.js
```

`Note` - Always check directory path before running javascript file. If Path is incorrect then file will not get executed.

## Browser JS v/s Node.js JS

| **Browser JS**                                                        | **Node.js**                                                              |
| --------------------------------------------------------------------- | ------------------------------------------------------------------------ |
| Run in Browser                                                        | Run on server                                                            |
| has DOM access                                                        | no DOM                                                                   |
| used for UI                                                           | used for Backend                                                         |
| Available APIs =>document, window, localStorage, alert( ), DOM etc.   | Available APIs => fs, http, os, path, process, Buffer                    |
| Can't access system Files                                             | Can read/write Files                                                     |
| Use cases => Form Validation, Animations, DOM updates, Event Handling | Use Cases => Build APIs, Database connect, Authentication, Server logics |
# npm (Node package manager) 

**Package** => Resuable code modules, saves development time, simplifies server creation, authentication, validation, etc. 
- Packages are avialble at https://www.npmjs.com/
- *Npmjs* websites have millions of open-source packages. 

## what is npm?

- **npm(node package manager)** comes automatically when we install *Node.js*
- Used to install package, manage dependencies, run script

## Initialize a Node.js Project

```bash
npm init -y
```

This initiializes the current directory as a Node.js application, It simpli means that in future we will create a Node.js application in this directory.
This command creates a `package.json` file. That stores default project configurations(name, version, description, main, scripts, keywords, author, license etc.). 
`-y` :- Yes to all defaults.

## Install Package

```bash
npm install expres
# or
npm i express
```

Installing a package simpli means bringing the code of package from npmjs website to our project.
## What happen when we install a package

Creates a folder `node_modules`, and two files `package,json`, `package-lock.json`

### node_modules 
- Stores the code of installed packages. 
- Very large folder. Never publish to Github.
### package.json
- Stores project info, info of all installed dependencies (Packages),
### package-lock.json
- stores all info of dependencies, dependencies of dependencies and so on. Basically stores a Dependency Tree. 
- Locks the exect versions of packages, so that whenever packages get installed the same version is installed that was used during development. 

`NOTE` :- As we never push node_modules folder to github or deployment, so when you clone any github repo, then always use `npm install` before doing anything. It ensures that all packages get installed. 
```bash
npm install
```

## Using package in Project

### module.exports  and require( )
To use the Installed package we have to bring package in our file by `require()`.

```js
const express = require("express");
```

Now we can use all functionalities of express package using `express` variable. 
This `rewuire()` is used for commonJS (old) Node versions. Before ES5 version.
To Import any function or variable etc from one file to other, so that we can `require()` it, we use `module.exports`
eg. app.js
```js
const fnc = () => {
  console.log("Hello");
};
module.exports = fnc;
```

server.js
```js
const fnc = require("./src/app");
```
In require() we pass the path string. The name of required component can be anything, fnc fnc1 fnc2 xyz or anything else
### Import / export

This is newer Modern JavaScript Standerd Module System.
To do export we use `export`  OR `export default`
`NOTE` - How we can use this export / Import feature ?? 
in the `package.json` add 

```json
{
  "type": "module"
}
```

Or either we can use `.mjs` extension for javascript files.

---
`export` 
- we can export many things from a file by name. 
- Normal `export` is called **named export**. 
- To import these named export things, we **must** have to import it with ***same name***.
- To **export** and  **import** we enclose variable name by `{ }` 
eg.  xyz.js
```js
export function add(a, b) {
  return a + b;
}

export const PI = 3.14;

// we must use {} at the export and import both locations for normal export
const fName = "Anil";
const lName = "Solanki";

export { fName, lName };
```

abc.js
```js
import {add, PI, fName, lName} from './xyz.js';

// we can rename the named exported variable, when we import it
import {add as sum} from "./xyz.js";
```

---
`export default` 
- **One file** can only export **one variable** using default export. 
- We dont have to use `{ }` around the variable name while importing. 
- When we use export default we can import the variable by **any name**. 

xyz.js
```js
export default function add(a, b) {
  return a + b;
}
```

abc.js
```js
import anyName from './xyz.js'
```

---
### Difference b/w ES Modules import/export & require( )

| **Feature**     | **`require( )`** | **`import` / `export`** |
| --------------- | ---------------- | ----------------------- |
| SYstem          | CommonJS         | ES Modules              |
| Standard  JS    | NO               | Yes                     |
| Loading         | Runtime          | Before execution        |
| Syntax          | Function call    | language keyword        |
| Tree-Shaking    | NO               | YES                     |
| Async Support   | NO               | YES (Dynamic import)    |
| Browser Support | No               | Yes                     |
Note -> Once we `require( )` an variable, it remain same even if we use a function that changes value of that variable. Because `require()` imports a copy of the value.
But if we use **import**/**export**  the value can change, because *ES modules* use **Live bindings**.

---
eg. xyz.js
```js
let count = 0;
function inc(){
	count++;
}

export {count, inc};
```

abc.js
```js
import {count, inc} from "./xyz.js";

console.log(count); // 0
inc();
console.log(count); // 1  // Updated
```
---
eg. xyz.js
```js
let count = 0;
function inc(){
	count++;
}

module.export = {count, inc};
```

abc.js
```js
const counter = require("./xyz.js");

console.log(counter.count); // 0
counter.inc();
console.log(counter.count); // 0  // Not updates
```

## Installing dev dependency

```bash
npm i nodemon --save-dev
# or
npm i nodemon -D
```

`dev dependency` => a package that we need only during **development** and **not in production**. 

in `package.json` these are listed in "devDependencies" property.

> [!NOTE]
> dependency => required to run the app
> devDependency => required to build, test, or develop the app.

See, we are curently noob, so we use 
```bash
npm install
```
as a command when we deploy. But this command installs both dependencies and devDependencies.

So in production, we use -
```bash
npm install --production
```
This ensures that only dependencies are installed and deDependencies are not installed.

We installs devDependencies because they helps us while we are developing the app, these are used by us (**Developers**) and not by the user.

Examples of dev-dependencies are
- nodemon (Auto restars the server on file changes)
- ESLint (Catch bugs early)
- Prettier (Clean Formatting)
- dotenv-cli (Load env during dev)
- Vite (Dev server & Bundler)
There are many such, use according to need. 

## npx vs npm

| **npm**               | **npx**                             |
| --------------------- | ----------------------------------- |
| node package manager  | node package execute                |
| Install packages      | Run a package without installing it |
| update/remove package | Execute CLI tools directly          |
| run scripts           |                                     |
| eg. npm i express     | eg. npx nodemon server.js           |
## Install package globally

```js
npm install -g packageName
```
This
- installs package globally on your system
- makes the CLI command available everywhere
But don't use it as it increases global polution. 




