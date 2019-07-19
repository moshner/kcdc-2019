# The Life-Changing Magic of Tidying Your Dev Team

* Gabby Spurling
* 7/19/2019 9:45am
* @gabbythedev

<!-- Summary: -->
"Improving how you work is just as important as what you work on." Using Marie Kondo's method, Gabby Spurling explains how you can tidy up your work and development processes. The four principles covered here are: Single purpose, measure effectiveness, communicate concisely, and reassess over time. 

For your meetings, documentation, version control, and code you can use these principles to help your team work together and save people time.

## Tidying Principles
1. Single Purpose
    : Everything you do should have one focused purpose
2. Measure Effectiveness
    : Processes should be tested to ensure they are completing their intended purpose
3. Communicate Concisely
    : All processes should be easy to use for a future audience.
4. Reassess over Time
    : Processes should be reviewed to ensure they are still relevant and helpful

"Build a culture of craftsmanship."

## Time
* Your most valuable resource.
* If you tallied your activities do they match the things that you find the most important?

## Meetings
* est. 56 million meetings in the usa, every day
* average 1.25 hours
* 29% of meetings were not productive
* 20 million hours daily that could be used elsewhere
* Purpose: Provide a purpose before the meeting or an agenda that is shared
* "Work expands so as to fill the time available for it's completion" - Parkinson's Law
* Consider shortening meetings
* Distractions
    * multi-tasking is a myth
    * one person on a device signals that this isn't that important and distracts everyone else.
* Keep meetings to under 8 people
* Invite the right people

## Documentation
* It sucks but it's critical
* Pairing is a good way to work around this
* Think of questions that are important to ask and get the pairing person to document it.
* Pull in a third party to get to go through documentation after it is written
* The test: Can you go on vacation without being contacted?
    * e.g. measure contact rate for people who are out of the office.
* YOu can also end up with too much documentation

## Version Control
* Version control history can very quickly loose organization
* Think about the next person who has to read it when you commit

### Steps:
1. Focused Commit
    * Never use `git add .` - be specific!
    * instead use wildcards like `git add *authService.ts`
2. Commit Message
    * have the ticket number in the commit
    * one sentence line describing your change (paragraphs are too much)
    * if you need more than one sentence, have more commits
3. Branches accomplish one goal
    * avoid 'and alsos'
    * branches should be focused to one goal
4. Small Pull Requests
    * avoids blank-check approvals
    * will be hard to discuss changes
    * improves code approval speed
5. Provide context to pull requests
    * just add a couple of details
    * screenshots help
    * add a description
    * consider pull request templates for changes
        * Ticket, description, Checks
        * Checks: Works in IE11, Safari, Run unit tests, linted, etc.

## Code
* Drivers of Technical Debt:
    * Requirements change
    * Technology change
    * People change
* Costs for technical debt: time cost and human cost. Because people don't like messy code.
* "Perfect is the enemy of good" - Voltaire
* Keep it simple, avoid pre-optimization to avoid over complicating things.
* Have a team agreed strategy for dealing with tech debt.
    * deal with it in each ticket
    * assign someone to do it
    * clean up weeks
    * paid programming
    * code reviews
* Don't avoid it, it will just get worse

## I'm Ugly and I'm Proud
What if I have only one thing that works? Do I throw it away and buy a new one? No, change your relationship with it.

If you think about the processes and how they serve you and not how annoying they are, you will begin to bring in joy there.

## Actions
[x] Create summary

[ ] Migrate notes to Evernote

## About
In an industry overflowing with information, new and constant change, the power of simplicity is often overlooked. So much of our work depends on clean and focused code, but for maximum benefit, you should be applying the same approach to the processes surrounding your work. In doing so, you can create an environment where your team functions better and is filled with joy.

-----------------------
**tags**: process, intermediate
