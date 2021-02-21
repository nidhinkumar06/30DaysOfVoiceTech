<div align="center">
  <h1>VoiceTech - Day 21</h1>
  <p>NodeJS for Alexa Development</p>
</div>

<h2 align="center">Asynchronous Function</h2>

Since the Lambda function which we write in Alexa is NodeJS we will look into the asynchronous function in javascript

### What is Asynchronous function?

Let's say you have gone to a theater waiting in a queue to buy ticket and when you are near to the counter you remember that you have forgot ur wallet soon u called ur friend who is in the theater to give some money.during that time you have reached the counter and you are telling the person in the counter to wait until ur friend comes in.

Does the person waits for u ?

No, he will ask the next person, similarly in JS when a function or a statement waits for some action to be done the next function or statement won't wait until the first function execute (That is becuase JS is async in nature)

To be more clear look the below example

```
function sample() {
  console.log(1);
  console.log(2);
  console.log(3);
}

sample()
```

When we call the function sample() it will execute with the following result `1 2 3` which is default in nature but if the second logs needs to wait for some reason like below

```
function sample() {
  console.log(1);
  setTimeout(function() { console.log(2) }, 1000)
  console.log(3);
}

sample()
```

The result for the above snippet will be `1 3 2` since we didn't give any instruction to JS to wait for the 2nd person.

Let's take another example

```
function printName() {
  let name = 'World';
  setTimeout(function() {
    name = 'Nidhin'
  }, 1000)
  return name;
}

printName()
```

When we run the above function it will return the result as `World`.Now u would think why it doesn't print `Nidhin`

The reason is we are returning the name when the function gets called and we didn't wait until the `setTimeout` is completed and that's the reason we are getting the result as `World`.

How can we get the name `Nidhin` instead of `World` for that we will make some tweak in the code like below

```
function printName(callback) {
  let name = 'World';
  setTimeout(function() {
    name = 'Nidhin'
    return(callback(null, name))
  }, 1000)
}

printName((err, data) => {
  console.log(data)
});
```

The above snippet will print the result `Nidhin` since we have used callback in your function which means it will wait until the timer is completed only after that it will print the result.This is one of the approach

### Why we need this?

If we are going to make an API call from Lambda then at that time we need to wait until the server responds back. So for that purpose we are inneed of these kind of approach


 