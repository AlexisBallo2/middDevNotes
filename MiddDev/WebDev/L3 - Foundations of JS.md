
Now that we have cloned our repository, we can begin to learn some JS. Don't worry about trying to understand everything yet - we will get there. For now - only ensure you understand the steps that we are explicitly teaching. 

Link to repository: https://github.com/MiddDev2-0/middDev-TicTacToe

# Setup
nfrorhwqoels.
JS needs an "engine" to run - something that actually runs the JS code. Historically websites were just html/css/js files, and your browser executed the js files. Nowadays, websites are much more complicated, and frameworks allow us to create much more advanced websites with much less code. The framework we will be using is also written in JS - and therefore we need to run this framework locally. We can do this by using "node" to run our server. 

Node is a JS engine that allows us to run JS without a browser. First lets install the dependencies. Navigate the the directory and type 
```shell
npm i
```
you can ignore the packages that this installs. 

Next run the application:
```shell
npm run dev
```
this will start a local version of the website, and will allow you to access the website at https://localhost:3000/


# Diving in

<div style = "background-color: #fff8a6; text-align:center; border-radius: 10px; padding: 10px 0 10px 0;">File: app/intro/page.js <br/> Server: <a href = "https://localhost:3000/intro">https://localhost:3000/intro</a></div>

Now we can get started actually working in JS. Navigate to the file `app/intro/page.js`. Like we said before - you can ignore a majority of the files. Only focus were we are currently writing code.

In this file you should see:
```js
// here we will learn the basics of JavaScript
let x = 10
console.log(x)

```
You may ignore all code before and after this section. 

Now navigate to https://localhost:3000/intro. Open the developer console **add details for how**
Somewhere in the console you should see:

![[Pasted image 20240104194003.png]]
note that it does this twice. We can ignore this for now. Only pay attention to what is in between the running and finished identifiers. 

## Data types
This code block assigns the integer value `10` to a variable `x`. There are many types of data structures that we can use in JS, such as integers, floats (decimals), strings, arrays, etc. 

```js
// string
let petType = "dog"

// integer
let price = 10

// array
let names = ["joe", "mama"]
//
```

We can also use objects to package multiple variables into a single variable. Consider the example object below:
```js
let jacket = {
	price: 10,
	currency: "usd",
	color: "red",
	stores: ['1st street', '3rd ave']
}
```
In this object we have an integer for price, a string for currency and color, and array of strings for the stores the product is carried in. 

>Challenge:
>Create an object titled name, age, family which contain your name, your age, and a few members of your family. Log them to the console to confirm!

# Functions

```js
function functionName(param1, param2) {
	// all function code goes here

	// can return a specific "thing" or ignore return value if we dont have anything we want to return
	return True
}
```
# Functions as variables

We can declare functions as a variable:

```js
let myFunction = (param1, param2) = > {
	console.log(param1, "and", param2)
}
myFunction("joe", "miles")
```


This allows us to pass functions to functions:
```js
function dummyFunct(callback) {
	console.log("executing callback")
	callback("hello", "goodbye)
	console.log("finished callback")
}
let myFunction = (param1, param2) = > {
	console.log(param1, "and", param2)
}
dummyFunct(myFunction)
```
will return:
```
executing callback
hello and goodbye
finished callback
```

within "dummyFunct" we treat the parameter as a function, and since we have passed a function "myFunction" to dummyFunct, we are able to execute it. Note that since JS is not typed, we are able to pass regular variables to dummyFunct (ex passing an integer or string), so we must be careful we are passing a function!!


# Looping

Pretty similar to other languages:

while loop:
```js
haveFriends = true
while(haveFriends) {
	// while the boolean 'haveFriends' is true, code within the while loop will iterate
	
}
```

for loop:
```js
for(let i = 0; i<10; i++) {
	// code in here will run with every iteration 
}
```

we often use for looping to get individual elements in an array:
```js
let animals = ['cow','dog','sheep']
for(let i = 0; i<animals.length; i++) {
	console.log(animals[i])
}
```
returns:
```
cow
dog
sheep
```

we can be more efficient in our looping with the "forEach" syntax:
```js
let animals = ['cow','dog','sheep']
let printAnimal = (animal) => {
	console.log(animal)
}
// passing functions as variables!
animals.forEach(printAnimal)

// we often do it in one line:
animals.forEach((animal) => {
	console.log(animal)
})
```
returns:
```
cow
dog
sheep
cow
dog
sheep
```




