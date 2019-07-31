# Keyboards? Where we’re going, we don’t need keyboards.

* Don Wibier
* 7/19/2019 2:15pm
* donw@devexpress.com
* @donwibier

<!-- Summary: -->
Don Wibier showed us how to use several AI apis from Microsoft cognitive services, including vision api, speech api, language api, and search api. The github repo has all the examples to play around with them. The coolest thing was that it really is simple to wire up once you train the AI.

## Notes

What are the Cognitive Services APIs?
    : A set of powerful services based on M.L. and A.I.

Available APIs
* Vision API
* Speech API
* Language API
* Knowledge API
* Search API

### What can we do with it?
* Describe content of pictures and videos
* Recognize faces
* Capture and recognize audio

### Using these api's
* have to have azure account
* have to have services account
* result appears to be json
* each category gets a score back

## LUIS
Language Understanding. The api isn't concerned with areas  outside of your itent. So if the pizza ordering application is asked to book a flight it won't know what its going on.

[https://www.luis.ai](luis.ai) 

* Set up account
* set up intent
* give it utterances
* tag words in the utterances with parameters, using pre-built wherever possible
* then train the model
* test the model to inspect the results
* if it comes back with inaccurate results, you need to feed it more information
* then you can connect to that API and respond to it!

## Insights
* Can we upload our UX videos to the vision API to get emotion of the users based on timestamp?
* Can we try to train luis.ai on CME questions?

## Prereqs
* Visual Sutdio 2015/2017
* Account with MS
* Account with LUIS

## Resources
https://github.com/donwibier/DXCognitiveSession

## About
One of the cornerstones in Microsoft’s digital assistant Cortana are cognitive services. Instead of the
traditional Screen / Keyboard / Mouse combination for user interaction with your application, it offers
different ways of handling user input.

Think about vision, speech and language – the new way of communicating with your devices – but also
how to analyze and structure these kinds of user input.

This session will give you an introduction on the Cognitive Services Platform – show how it can help your
end-users – and with live coding examples you will experience how easy it is to start using this incredibly
cool API.

-----------------------
**tags**: cloud, intermediate
<!-- Footnotes -->
[^1]: Example footnote

<!-- Markdown Cheatsheet https://www.markdownguide.org/cheat-sheet/ -->
