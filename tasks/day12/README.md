<div align="center">
  <h1>VoiceTech - Day 12</h1>
  <p>Unit testing</p>
</div>

<h2 align="center">GoogleAssistant - Unit testing test suite</h2>

For the unit testing we are using mocha testing framework. In our project we will create a directory named `test` and then we will write the specs over there

For using mocha we need to install the mocha library in npm like below `npm i mocha `

Inside the test directory we will create a file and inside the file will create the base skelton of the test suite like below

```
import 'mocha';

import {ActionsOnGoogleTestManager} from '@assistant/conversation-testing';

const PROJECT_ID = '<ACTION_PROJECT_ID>';
const TRIGGER_PHRASE = 'Talk to <ACTION_DISPLAY_NAME>';

describe('Test Suite', function() {
  // Set the timeout for each test run to 60s.
  this.timeout(60000);
  let testManager;

  before('Before all setup', async function() {
    testManager = new ActionsOnGoogleTestManager({ projectId: PROJECT_ID });
    await testManager.writePreviewFromDraft();
    testManager.setSuiteLocale(DEFAULT_LOCALE);
    testManager.setSuiteSurface(DEFAULT_SURFACE);
  });

  afterEach(function() {
    testManager.cleanUpAfterTest();
  });
});
```

In the above snippet the describe is the test suite say for example if you are going to test the whole process which has the conversations.

The `before` method is used to set the values `before` running a spec and the `afterEach` block will be executed once a spec is runned successfully.

```
it('trigger only test', async function() {
    await testManager.sendQuery(TRIGGER_PHRASE);
    testManager.assertIntent('actions.intent.MAIN');
    testManager.assertScene('Welcome');
    testManager.assertSpeech('Welcome to Facts about Google!');
});
```

The `it` block will run the specs for each of the unit that we need to test as well as we can have multiple `it` blocksS