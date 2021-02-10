<div align="center">
  <h1>VoiceTech - Day 10</h1>
  <p>Unit testing</p>
</div>

<h2 align="center">Google Assistant unit testing - Functions</h2>

## Send Functions

1. `sendQuery(queryText)` - Sends query to the action
2. `sendStop()` - Sends a 'stop' query to exit the action

What is `Assertion`?

An assertion is a boolean expression at a specific point in a program which will be true unless there is a bug in the program. A test assertion is defined as an expression, which encapsulates some testable logic specified about a target under test.

## Assertion

1. `assertSpeech(expected, assertParams?, response?)` - Asserts the expected text is contained in the response Speech (concatenation of the first_simple and last_simple Speech). Note: Through optional assertParams it is possible to require exact match, and/or allow regexp matching.
2. `assertText(expected, assertParams?, response?)` - Asserts the response Text (concatenation of the first_simple and last_simple Text)
3. `assertScene(expected, response?)` - Asserts the response Scene, i.e. the scene that is currently active in the conversation
4. `assertIntent(expected, response?)` - Asserts the response Intent, i.e. the intent that was matched by the query phrase
5. `assertConversationEnded(response?)` - Asserts the conversation ended in the response
6. `assertConversationNotEnded(response?)` - Asserts the conversation that did not ended in the response
7. `assertSessionParam(name, expected, response?)` - Asserts the response storage paramerter value
8. `assertUserParam(name, expected, response?)` - Asserts the response user storage parameter value
9. `assertHomeParam(name, expected, response?)` - Asserts the home storage parameter value
10. `assertCanvasURL(expected, response?)` - Asserts the canva storage url
11. `assertCanvasData(expected, requireExact?, response?)` - Asserts the canvas data
12. `assertCard(expected, requireExact?, response?)` - Asserts the card response
13. `assertImage(expected, requireExact?, response?)` - Asserts the image response
14. `assertCollection(expected, requireExact?, response?)` - Asserts the collection response
15. `assertTable(expected, requireExact?, response?)` - Asserts the table response
16. `assertList(expected, requireExact?, response?)` - Asserts the list response
17. `assertMedia(expected, requireExact?, response?)` - Asserts the media response


#### Reference Link

https://github.com/actions-on-google/assistant-conversation-testing-nodejs