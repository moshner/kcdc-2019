# Building Quality JavaScript with Test-Driven Development

* Steven Hicks
* 7/17/2019 8am
* @pepopowitz
* steven.j.hicks@gmail.com
* [stevenhicks.me/tdd](https://stevenhicks.me/tdd)

<!-- Summary: -->
Steven Hicks presented a good workshop on how to get started with JEST and javascript tdd. There are a lot of reasources on the web but the biggest take away for me on this is that I need to **practice** it. Keep the tests small and start with a failing test. Then write the smallest amount of code to make the test pass. Then refactor the code to make it better. 

This means that I can write really crappy code to start var = "answer" and the refactor it to add in any dynamic stuff.

## Notes
Works at Artsy: Artsy is a NY based company that connects art collectors with galleries all over the world.

###  Jest
* ["Delightful JavaScript Testing"](http://facebook.github.io/jest)
* Easy to set up
* 0 configuration necessary
* Fast, not the fastest though
* Gives helpful error messages
* Interactive watch mode - only changes that are affected by recent changes, uses git to do that
* Writing tests
    * `__tests__` folder
    * *.spec.js
    * *.test.js
### Jest API
#### describe() is how you define a set of tests

```  // code block
describe('first-name-translator', () => {
    // tests go in here
})

``` 
#### it() or test() <-- Do the same thing

```  // code block
describe('first-name-translator', () => {
    it('translations)...
})
```
#### expect()

```
expect(a).toEqual(b);
expect(a).not.toEqual(b);
```

### Running Tests in Jest
(not talking about snapshots today)

### Module 1 Excercise

module-1/README.md

He had us work independently/together to go through the README file and follow the instructions.

[x] QUESTION: Would it be advisable to write tests for every iteration of the function?
 * Cover edge cases, happy pathy, and fail cases
 * It can be helpful to write two different/redudant tests that help you troubleshoot code

Tip: Commit small changes often


### Module 2: TDD

"A discipline in which any system change requires a failing test to be written first"

It's about tightening the feedback loop.

"Red/Green/Refactor" is ofter a term for this process.

Goals:
* Improve readability and maintainability
* Remove "code smells"
* Remove duplication

Leads to:
* Simpler designs
* Smaller units of code
...

Also may:
* Question your understanding of the requirements
* Document the requirements
* Guide code reviews
* Give you code confidence
* Reduce metal clutter

Steps to TDD
0. Accept that TDD is hard
1. Identify the test (one at a time or brainstorm all)
2. **Write the failing test** but also the interface to what you are testing
3. **Write as little code as possible to make the test pass.** fake it. once you are all green you have comfort
4. **Refactor the code** while making small changes. 

Tips:
* Stay "green" while refactoring as much as time
* Take smaller steps during the refactor
* Work in small iterations - tight feedback loop

Exercise: Module 2: fizz buzz with TDD

Suggestions: 
* Stay Green
* Handle validation first
* Design your interfaces as you write these tests
* Triangulate

### Module 3: Code Katas
* testing **can** become a habit

wow, that was hard because I am slow with javascript. 

tip: expect(() => function(val).toThrow) is the format for seeing throw messages, only. not normal return functions. Use this: 

```
let return = function(val)
expect(return).toEqual(val)
```

### Module 4: Real-life TDD | Mocking

When to use:
* The actual dependency has side-effects (e.g. deletions)
* The actual depenedncy is not deterministic (e.g. add 2+3 = 5 is deterministic; calling time is not deterministic)
* The actual dependecy is expenisve to test

#### jest.mock()
```
jest.mock('axios');
```

#### beforeEach() & afterEach()
good for making sure things are cleaned up at the end
```
beforeEach(() => {
    axios.get.mockReset();
})
```
```
axios.get.mockResolvedValue({
    data: [
        {
            name: 'first',
            hills: easy
        }
    ]
})
```
#### Assertions
[ ] look these up in his slides

#### combine all
pic 10:27am

```
import axios from 'axios'
 jest.mock('axios');

```

#### business logic
it's useful for business logic too

#### bug fixes
start by writing the bug into your a test case
then go fix it
pic 10:30

#### module 4ab / 4ac
module-4ab/README.md & ...ac/README.md

that sucked, again I don't know enough javascript

### Suggestions: 
* Introduce TDD in small doses
* Be pragmatic
* Test the interface not the data!
* Tests aren't permanent
* Make the change easy

## Good practices
* Treat test code like tested code
* Name things appropriately
* Test are cattle, not pets: delete them when they no longer serve them.
* Make things small
* Optimize tests for time of failure, not time of writing
    * keep in mind the target audience of them

## Insights
* TDD is easier when working on small things
* TDD is eaiser to implement when working on bugs, this is a good place to start.

## Actions
[ ] Create summary

[ ] Migrate notes to Evernote

## About
Learning Test-Driven Development (TDD) is frustrating. The first couple tests feel strange - you wonder why you're writing tests that fail on purpose. Before long, you find yourself behind schedule from spending so much time on tests. You abandon unit testing completely. You'll write them after....if you find the time.
 
 This workshop will ease the frustration of learning Test-Driven Development. We'll discuss the fundamentals of TDD and work together to solve problems in a test-driven manner. You'll build confidence in your ability to apply TDD in JavaScript with hands-on experience. 
 
 Topics and activities include:
 
 * Instruction and exercises that will familiarize you with Jest as a JavaScript test framework
 * An introduction to the fundamentals of TDD
 * An instructor-led demonstration of TDD in practice
 * A collaborative code kata to get a hands-on, practical introduction to TDD
 * A series of hands-on exercises writing test-driven JavaScript code
 * A discussion of best practices for keeping your JavaScript test-friendly
 
 We'll be using Jest to build quality into our JavaScript code from the start. No specific UI framework will be targeted in this workshop - we will focus on writing and testing pure JavaScript. The experience you gain will be applicable to any JavaScript-based app, regardless of your framework allegiance.
 
 Participants should be able to read and write JavaScript, as no time will be spent on language details. General familiarity with writing unit tests in any language is required. Familiarity with Test-Driven Development is helpful but not required, and no TDD experience is necessary. No experience with Jest is necessary.
 
 A laptop with the LTS version of NodeJS installed (currently 8.11.2) is required. The corresponding version of NPM (currently 5.6.0) is also required. Detailed setup instructions are at https://stevenhicks.me/tdd-setup.

-----------------------
**tags**: javascript, intermediate