# Defense Against the JavaScript Dark Arts

* James Quick
* 7/18/2019 2:30pm
* @jamesqquick
* [Slides](https://bit.ly/js-dark-arts)
* [Learn Build Teach](https://www.learnbuildteach.com)

<!-- Summary: -->

## 1) Mastering Equality
### double equals 
looks for general equality.
 0 = "" //same
 null == undefined //same
coercion basically uses Falsy Values and flips those for truthy

### triple equals
compares strong equality by compareing both types and value without coercion

### Pass by Value
primitives are passed by value
primitieves = undefined, null, boolean, string, number

### Pass By Reference
same as value only if you compare two objects that are the same content but try to compare them they will not be equal.

e.g. if you copy the first object and compare back to the same they WON'T BE THE SAME!

### Deep clones
`p2 = { ...p1}` is a shallow clone and cannot make a copy of it. Lowdash is a default way to make a deep copy of an object. 

### Summary of #1
Use triple equals and make true copies of objects to avoid confusion.

## 2) ES6 Features
aka js2015

**You must know ES6** to be a successfuly JS developer

### Default Parameters
The problem:
```
const add = (num1, num2) => {
    return num1 + num2
}

console.log(add()) // is okay, you get NaN
```

Can be solved in ES5 by runing if conditions
```
const add = (num1,num2) => {
    num1 = num1 || 0;
    num2 = num2 || 0;
    return num1 + num2;
}

console.log...
```

ES6 Solution
```
const add (num1 = 0, num2 = 0)...
```

For objects
```
const addFromObject = ({ num1 = 0, num2 = 0} = {}) => {...}
```

You can declare a default value that is actually a function! So you can throw an error at that time.

### Template Literals
" vs `

` will keep formating and combine variable interpolation. 

```
console.log(`${person.first} ${person.last} lives in ${person.city}`)
```

### Spread Operators
Make shallow copies 

#### arrays
```
const arr2 = [...arr1]; //makes a copy without equality
```

#### objects
```
const object2 = {...object1}; //makes a copy without equality
```

### Deep Copies
```
JSON.parse(JSON.stringify(obj))
```
or...use Lowdash

### Other features of ES6
1. Arrow Functions
2. Promises
3. Enhanced Object Literals
4. ... and many more

## 3) Asynchronous JavaScript
* JavaScript is SINGLE THREADED language
    * You as a developer have to be intentional about 
    * "What the heck is the event loop anyway" - Good video by Philip Roberts

### Callbacks
Is async
```
setTimeout(() => {
    console.log("1 second");
}, 1000);
```

Adding click andlers is async too
```
button.addEventListener('click', (e)...)
```

### Callback Hell
```
setTimeout(() => {
    console.log("5");
    setTimeout(() => {
        console.log("4");
        setTimeout(() => {
            console.log("3");
            setTimeout(() => {
                console.log("2");
                setTimeout(() => {
                    console.log("1");
                }, 1000)
            }, 1000)
        }, 1000)
    }, 1000)
}, 1000)

//5...4...3...2..1
```
This is really easy to get yourself stuck into! This is very hard to read

### Promises
Are async
```
const axios = require('axios');

const url = "http://api.icndb.com/jokes/random?firstName=James&lastName=Quick"
axios.get(url)
    .then( res => {
        console.log(res.data.value.joke);
        //"Product Owners never ask James Quick for more features. They ask for mercy."
    })
    .catch( err => {
        console.log(err);
    });

```
### Promise Chaining
```
const todoURL = "https://jsonplaceholder.typicode.com/todos/1";
const userURL = "https://jsonplaceholder.typicode.com/users/"

axios.get(todoURL)
    .then((res) => {
        console.log(res.data); //userId = 1
        return axios.get(userURL + res.data.userId);
    })
    .then(res => {
        console.log(res.data) //user object
    })
    .catch(err => {
        console.log("ERROR! " + err);
    })
```
In this example we are running a promise after another promise completes. This way you don't have to have separate error catches.

### Async/Await
```
const getJokeAsync = async () => {
    const url = "http://api.icndb.com/jokes/random?firstName=James&lastName=Quick"
    const res = await axios.get(url);
    console.log(res.data.value.joke);
}

getJokeAsync();
```
ES8 js.

```
const getUserFromTodoAsync = async (todoId) => {
    const todoURL = "https://jsonplaceholder.typicode.com/todos/" + todoId;
    const userURL = "https://jsonplaceholder.typicode.com/users/"

    const res = await axios.get(todoUrl);
    const userRes = await axios.get(userURL + res.data.userId);
}
```
This is much more natural than the promise chaining

### Async/Await and Try/Catch
```
const getTodoAsync = async () => {
    const todoURL = "https://jsonplaceholder.typicode.com/todos/1";
    const userURL = "https://jsonplaceholder.typicode.com/users/"

    try {
        const res = await axios.get(todoUrl);
        const userRes = await axios.get(userURL + res.data.userId);
    } catch (ex) {
        console.log("ERROR!" + ex);
    }
}

getTodoAsync();

```

## 4) Formatting and Linting
It will statically keep you from doing something wrong. (Not dynamically).

### Benefits
* Consistent Code Formatting
* No const reassignment and no undeclared variables
* Better timing/performance with Asynchronous JS
* No console.log()

You can prevent pushing code if linting fails.

Instead of async in a for loop you can use `promise.all`

### Linting Setup
* Install eslint package to project
* Use `eslint --init` command
* follow prompts to create eslint configuration (creates .eslintrc file)
* Install eslint extension for VS Code
* Go into settings and check "Eslint: Auto Fix on Save"

## 5) TypeScript
TypeScript is a **typed superset** of JavaScript that **compiles to plain JavaScript.** 

### Benefits
* **Optional** static typings
* Converts to JavaScript
* Easily define object definitions with Interfaces
* Documentation and Intellisense

### Static Bindings
```
function ICanAdd( num1, num2) {
    return num1 + num2;
}

ICanAdd(1,2);
ICanAdd("James", "Quick");
ICanAdd({}, []);
```

```
function ICanAdd(num1: number, num2: number) {
    return num1 + num2;
}

ICanAdd(1, 2);
ICanAdd("James", "Quick"); //CANT DO THAT!
ICanAdd({}, []); //CANT DO THAT!
```

```
function ICanAdd(num1: number, num2: number):number {
    return num1 + num2;
}

const num:number = ICanAdd(1, 2);

```

```

function ICanAdd(num1: number, num2: number):number {
    return num1 + num2;
}

const num = ICanAdd(1, 2); //type of number is optional since function returns a number
```

```

function ICanAdd(num1: number, num2: number):number {
    return num1 + num2;
}

let num = ICanAdd(1, 2);
num = "James" //YOU CAN"T DO THIS: num is of type number
```

Try out the [TypeScript Playground](https://www.typescriptlang.org/play/index.html)

### Interfaces/Models
```
interface Person  {
    first: string,
    last: string,
    age:number,
    children: [],
    spouse:Person
}
```
This leads to knowing and getting intellisense help!

### Setup Typscript
* Install TypeScript via NPMx
* Use tsc command followed by TypeScript file
* Create TypeScript configuration file
* Install TSLint extension VS Code

## BONUS) Debugging
~~~console.log()~~~

VSCode has all the features 

## [Learn VS Code](https://www.udemy.com/learn-visual-studio-code/?couponCode=KCDC2019)
On UDemy
Coupon Code - KCDC2019

<!-- 
### Code Block
```  // code block
{
    "firstName": "John"
}
```  -->

## Insights
Can we declare default value errors 

Axios is making http requests

## Actions
[ ] Create summary

[ ] Migrate notes to Evernote

## Resources
* [JavaScript Double Equals vs Triple Equals](http://codeburst.io/javascript-double-equals-vs-triple-equals-61d4ce5a121a)
* [JavaScript Truthy](https://developer.mozilla.org/en-US/docs/Glossary/Truthy)
* 🎥 [JavaScript Objects](https://www.youtube.com/watch?v=VIKY1DqlRtI) - Getting Started
* 🎥 [JavaScript Arrays](https://www.youtube.com/watch?v=xh7njXASFjU&t=661s) - Getting Started
* 🎥 [JavaScript Promises](http://www.youtube.com/watch?v=gyC19H4ip1k) - Getting Started
* 🎥 [JavaScript Fetch API](https://www.youtube.com/watch?v=uBR2wAvGces&t=1s) - Getting Started
* [Explaining Value vs. Reference in JavaScript](https://codeburst.io/explaining-value-vs-reference-in-javascript-647a975e12a0)
* 📖 [JavaScript 30 by Wes Bos](https://javascript30.com/) - Free course to build your javascript skills
* [ESLint](https://eslint.org/)
* [TypeScript](https://www.typescriptlang.org/)
* 🎥 [Debugging JavaScript in Chrome and VS Code](https://www.youtube.com/watch?v=AX7uybwukkk)

## About
In the magical world of JavaScript, you have the power to do almost anything, but with great power comes great responsibility. Do you have the magical prowess to protect yourself from the darkest depths of JavaScript?
 
In this talk, we discuss 5 spells that you can use protect yourself from the most common JavaScript pitfalls. Some of these are as easy as a swish and flick of the old magic wand thanks to modern JavaScript tooling, but the rest comes from establishing best practices and a new mindset. After this talk, you will walk away head high and wand at the ready!

-----------------------
**tags**: javascript, intermediate