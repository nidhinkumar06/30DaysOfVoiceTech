<div align="center">
  <h1>VoiceTech - Day 11</h1>
  <p>Unit testing</p>
</div>

<h2 align="center">Google Assistant unit testing - Functions</h2>

## Getters

1. `getLatestResponse()` - Get latest turn full response
2. `getSpeech(response?)` - Get response speech(concatenation of first and last speech)
3. `getText(response?)` - Get the response text(concatenation of first and last simple text)
4. `getScene(response?)`- Get the response speech
5. `getIntent(response?)`- Get the response intent
6. `getIsConversationEnded(response?)` - Returns whether the conveersation is ended in the response
7.  `getSessionParam(name, response?)` - Get the response value of a session storage parameter
8. `getUserParam(name, response?)` - Get the response value of a user storage parameter
9. `getHomeParam(name, response?)` - Get the response value ofa home storage parameter
10. `getCanvasURL(response?)` - Get the canvas URL
11. `getCanvasData(response?)` - Get the canvas data
12. `getContent(response?)` - Get the prompt content if exist
13. `getCard(response?)` - Gets the prompt card if exist
14. `getCollection(response?)` - Gets the prompt collection if exists
15. `getImage(response?)` - Gets the prompt image if exists
16. `getTable(response?)` - Gets the prompt table if exists
17. `getList(response?)` - Gets the prompt list if exists
18. `getMedia(response?)` - Gets the prompt media if exists

## Match Intents

1. `assertTopMatchedIntent(query, expectedIntent, place, queryLanguage)` - Asserts the expected intent in the top N matched intent to a given query, in the given language.
2. `assertMatchIntentsFromYamlFile(yamlFile, queriesLanguage?)` - Checks all the queries intent assertions in the yaml file.
3. `getMatchIntentsList(query, queryLanguage)` - Gets the matched intents names using the matchIntents API call.
4. `getMatchIntentsList(query, queryLanguage)` - Gets the intents for the checked query using the matchIntents API call.