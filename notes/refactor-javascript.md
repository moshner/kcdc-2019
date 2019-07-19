# Less. Better. Let's Refactor JavaScript

* Joe Morgan
* 7/19/2019 8:30 am
* @joesmorgan
* thejoemorgan.com

<!-- Summary: -->

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
* 

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

## Actions
[ ] Create summary

[ ] Migrate notes to Evernote

[ ] lookup article: "Avoid Hasty Abstraction"

## Resources

<!-- Footnotes -->
[^1]: Example footnote

<!-- Markdown Cheatsheet https://www.markdownguide.org/cheat-sheet/ -->