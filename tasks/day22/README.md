<div align="center">
  <h1>VoiceTech - Day 22</h1>
  <p>NodeJS for Alexa Development</p>
</div>

<h2 align="center">Javascript Variables</h2>

Javascript variables `var, let, const`

### var

variable which can be used like the below function

```
function getUser() {
    console.log(name);
    var name = 'Alexa';
    console.log(name);
}

getUser()
```

When the above function is run it will produce the output as follows

```
undefined
Alexa
```
The first log prints undefined since the var name is not defined. var has a global scope where as let has block scope that is

### Let

```
function getUser() {
    var arrived = true;

    if(arrived) {
       var name = 'Alexa';
       console.log(name); 
    }
    console.log(name);
}

getUser()
```

Which will print the name twice , but if the same variable is used with let then it is available only for that block
```
function getUser() {
    var arrived = true;

    if(arrived) {
       let name = 'Alexa';
       console.log(name); 
    }
    console.log(name);
}

getUser()
```

The above snippet will produce the result as `Alexa and undefined`

### Const

The value which cannot be changed once it is set is called as const a.k.a Constant

```
function getUser() {
    const name = 'Nidhin';
    name = 'Alexa';
    console.log(name);
}

getUser()
```
Which will throw an error like below

```
Uncaught TypeError: Assignment to constant variable.
    at getUser (<anonymous>:3:10)
    at <anonymous>:7:1
getUser @ VM743:3
(anonymous) @ VM743:7
```

But with a const we can create an object and assign values to it dynamically

```
function getUser() {
    const user = {
      name: 'Nidhin'
    };

    console.log(user.name);
    user.name = 'Kumar'
    console.log(user.name);
}

getUser()
```

which will print the output like `Nidhin and Kumar`