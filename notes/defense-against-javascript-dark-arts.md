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

### 4) FOrmatting and Linting


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
"JavasScript 30" by Wes Bos: Free course to build your javascript skills

<!-- Footnotes -->
[^1]: Example footnote

<!-- Markdown Cheatsheet https://www.markdownguide.org/cheat-sheet/ -->