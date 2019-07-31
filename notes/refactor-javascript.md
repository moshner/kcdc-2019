# Less. Better. Let's Refactor JavaScript

* Joe Morgan
* 7/19/2019 8:30 am
* @joesmorgan
* thejoemorgan.com

<!-- Summary: -->
All code bases get more complicated and messy over time, it's in their nature. Refactoring is a necessary thing to do. Not just by one person but by everyone, all the time. Joe Morgan explained the three steps of refactoring: Isolate, purify, and Combine. Then he went through specific examples in a pizza building application. 

## Notes
2nd Law of Themodynamics
: the total entropy of an isolated system cannot decrease over time

people argue that you can decrease the entropy

theory: 
peel pieces apart one at a time, what can we do to make it better.

### When are you ready to refactor
* avoid a situation where you get in too deep, making too many changes at once

### Pre-Steps
1. First rule: Do no harm.
1. Have a robust test suite, make it if you need to
    1. Unit tests
    1. Functional tests

### Steps
1. Isolate
1. Purify
1. Combine

### 1) Isolate
* What does it need to know?
* review the functions for complexity, how can you remove duplicates, etc.

### 2) Purify
* Taking all these parts that make sure it doesn't have reference to anything but it's immediate inputs and outputs
* It's easy to overlook the scope of your functions in javascript
* Changing state is something to be careful about
* You can move pure functions into their own files, up to you

### Isolate and Reuse
* Keep parameters flexible
* can use object destructuring
```
...(image && { image}) // short circuiting
```
Short Circuiting
: conditionally added properties to an object. if truthy set it.

Spread Operator as parameters
: allows you to fill in a lot of extra stuff into the 
```
function foo(
    thing1,
    thing2,
    ...thingN
) {etc.}
```

### 3) Combine
* be careful manipulating the display layer outside of the display layer
* sometimes you add complexity before you can remove complexity
* Remove nested if-thens
* Fail Early: Move the fail cases to the top to make it easier to skim
* Create a closure: for call once functions

## Layers
* Data
* Utilities
* Display

## Refactoring in Teams
* When? Constantly
* Who? Everyone should do it

## Insights
`limits.every()` is an interesting function for checking if everything is true

My confusion about functions having immediate inputs/outputs appears to be because I'm mixing the data layer and the display layers

"Individuals write **code,** teams create **software.**"

[Avoid Hasty Abstraction](https://kentcdodds.com/blog/aha-programming)

## About
You may have heard the phrase “red, green, refactor,” but in reality it’s more like “red, green, tech debt.” It’s easy to think you’ll go back and refactor your code when you have time, but by the time you get a chance, you’ll find a big plate of spaghetti. Teasing it apart can be difficult and scary (what about all the edge cases?). Admit it: when you find code that needs a refactor, you probably quietly close the file and move on to something else. In this talk, you’ll learn how to attack the spaghetti and turn it into clean, reusable code. You’ll learn techniques for refactoring code and isolating reusable chunks. You’ll also learn how to integrate continual refactoring into your process to ensure that code is clean without premature abstractions.

-----------------------
**tags**: javascript, intermediate
