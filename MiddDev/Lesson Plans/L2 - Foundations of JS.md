
Now that we have cloned our repository, we can begin to learn some JS. Don't worry about trying to understand everything yet - we will get there. For now - only ensure you understand the steps that we are explicitly teaching. 

# Setup

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

This code block assigns the integer value `10` to a variable `x`. There are many types of data structures that we can use in JS, such as integers, floats (decimals), strings, objects, arrays, etc. 

>Challenge:
>Create variables titled name, age, family which contain your name, your age, and a few members of your family. Log them to the console to confirm!



