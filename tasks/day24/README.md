<div align="center">
  <h1>VoiceTech - Day 24</h1>
  <p>NodeJS for Alexa Development</p>
</div>

<h2 align="center">Async Await</h2>

Instead of using callbacks we can use promises or async await

An async function is a function declared with the async keyword, and the await keyword is permitted within them. The async and await keywords enable asynchronous, promise-based behavior to be written in a cleaner style, avoiding the need to explicitly configure promise chains.

Async functions can contain zero or more await expressions

The await keyword is only valid inside async functions within regular JavaScript code. 

The purpose of async/await is to simplify the syntax necessary to consume promise-based APIs. The behavior of async/await is similar to combining generators and promises.

aysnc await example

```
function resolveAfter2Seconds() {
  return new Promise(resolve => {
    setTimeout(() => {
      resolve('resolved');
    }, 2000);
  });
}

async function asyncCall() {
  console.log('calling');
  const result = await resolveAfter2Seconds();
  console.log(result);
  // expected output: "resolved"
}

asyncCall();

```