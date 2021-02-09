<div align="center">
  <h1>VoiceTech - Day 9</h1>
  <p>Unit testing</p>
</div>

<h2 align="center">Google Assistant unit testing</h2>

## Unit test

For Dialogflow agent, we can write tests where each case expects a text query as an input and produces intent metadata as an output. This metadata should contain the name of the matched intent and a list of matched parameters.

The detectIntent endpoint of the Dialogflow API takes the text query as an input and produces a structured output that contains the name of the resolved intent and extracted parameters. It is useful for assessing the intent-matching performance of the agent. For a complete reference of other useful fields, see the QueryResult reference.

```
it('choose_fact', async function() {
  // The `dialogflow` variable is an abstraction around the API that creates
  // and sends payloads to Dialogflow.
  const resJson = await dialogflow.detectIntent(
    'Tell me about the history of Google');
  expect(resJson.queryResult).to.include.deep.keys('parameters');
  // Check that Dialogflow extracted required entities from the query.
  expect(resJson.queryResult.parameters).to.deep.equal({
    'category': 'history',
    // Put any other parameters you wish were extracted
  });
  expect(resJson.queryResult.intent.displayName).to.equal('choose_fact');
});
```

The detectIntent endpoint also triggers Dialogflow fulfillment, which may cause additional network calls. You can toggle fulfillment on or off for an individual intent in the Fulfillment section of that intent's page.