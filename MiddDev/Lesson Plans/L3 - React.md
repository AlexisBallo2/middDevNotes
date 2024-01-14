Now that we understand the basics of JS, we can start to learn how to display information using our JS framework. For running our frontend, the framework uses "React." Today we will teach you how to begin thinking in React...

# JSX

### Structuring
At it's core, JSX is a tool that React uses to maintain order in your app. JSX makes up the most "top level" code that we will be writing, it is the skeleton that holds all of the website elements together, telling the computer what goes where, specifies formats, and how each element should interact with one another.

For any element to be properly turned into website-ready code, it must be wrapped in a "tag". Tags are defined as the pairs of "<" ">" braces, with the actual rendered content being in between the pairs. 

Some basic examples are:
```html
<div> I am inside a div tag! </div>
<h1> I am inside a header tag! </h1>
<p> I am inside a paragraph tag! <p>

//Renders:
//I am inside a div tag!
//I am inside a header tag!
//I am inside a paragraph tag!
```
Already, you might realize that a website where we have all elements inside a single tag would be incredibly boring! This is where NESTING comes in, allowing us to place JSX elements inside of one another.
```html
<div>
	<h1> I am inside a header tag AND a div tag! </h1>
<div>
```
IMPORTANT: When nesting elements, there can only ever be ONE SINGLE all-encapsulating tag.
```html
<div>
	<h1> I am inside a header tag AND a div tag! </h1>
	<p> I am inside a paragraph tag AND a div tag! </p>
<div>
```
This will not run. We need a tag that contains both div elements:
```html
<div>
	<h1> I am inside a header tag AND a div tag! </h1>
	<p> I am inside a paragraph tag AND a div tag! </p>
<div>

<div>
	<h1> I am also inside a header tag AND a div tag! </h1>
	<p> I am also inside a paragraph tag AND a div tag! </p>
<div>
```

Lastly, for any JSX element that we want to render, it must be added to the "return" statement of our app. In React, this would be the return statement of our "app.js" file. Multi-line JSX elements need to be wrapped in parentheses to render, like so:

```html
return (
	<div>
		<h1> I am inside a header tag AND a div tag! </h1>
		<p> I am inside a paragraph tag AND a div tag! </p>
	<div>
)

```
### Functions and Logic
JSX allows us to add functionality into our website by allowing us to directly render the outcomes of desired functions or other code we've written using the "{}" braces. For example:
```html
const number = 5
return (
	<div>
		<h1> This is a number {number} </h1>
	<div>
)

//Renders to: "This is a number 5"
```

We can also call functions inside of here as well! Consider a function that adds 2 to any random number between 1-10:

```jsx
const randNum = Math.floor(Math.random() * 11)
const addTwo = (randNum) => {
	return randNum + 2
}

return(
	<div>
		<h1> 
			This is the result of adding 2 to {randNum}: {addTwo} 
		</h1>
	<div>
)

//If randNum = 7
//Renders "This is the result of adding 2 to 7: 9"
```
**Challenge:** In your "page.js" file, using an object that stores your first name, college year, and hometown, write and render a JSX expression that introduces yourself.

Now that we have functionality introduced, there's really no limit on how we can organize our website! This process of introducing OUR OWN code and functionality to JSX brings us into our next topic...
# Thinking in React

### Components
React is special because of its use of "components" - or little bits of code we will reuse. A component may be a dropdown list that we use on multiple pages - rather than coding it 4 times, we can code it once and import it into the 4 different files. 

React is build around declaring a hierarchy for our designs. For example, consider the example below:
![[Pasted image 20240104201649.png]]
Here we have multiple components:
1. ORANGE - Container component. Houses our search and display components and determines where they should be displayed relative to each other. 
2. BLUE - Search component. Packages up the searching functionality and separates it from the code to display the searched items. 
3. GREEN - Display component. Only designed to show the items. 

We can break it even further down: 
![[Pasted image 20240105093618.png]]
### Try it yourself: 
In `app/reactIntro2/page.js` you will find the "Board" component with a row of "Square" components. 
 - [ ] Add a new component that displays a "restart" button
 - [ ] Complete the tic tac toe board

### State

Now that we have the basic board, we can start managing user input. 
Lets keep track of the board by using a simple 9 value array. 
For example an empty board would be represented as:
[0,0,0,   0,0,0,   0,0,0]
This state:

would be represented as:
[0,1,0    -1,-1,1,     1,0,0]

State allows us to manage variables and the "state" of the application at a point in time. The most common way we will manage state is with the `useState` hook provided to us by our nextjs framework. Consider the code block below

```jsx
function Box() {
	const [isChecked, setIsChecked] = useState(false)
	if (isChecked) {
		return (
			<div>
				CHECKED
			</div>
		)
	} else {
		return (
			<div>
				NOT CHECKED
			</div>
		)
	}
}
```
Here, our "Box" component has a state variable named "isChecked". If it's true, we return a "checked", otherwise, we return a "not checked". 

To update our state we use the "setIsChecked()" function:
```jsx
function Box() {
	const [isChecked, setIsChecked] = useState(false)
	if (isChecked) {
		return (
			<div onClick = {() => setIsChecked(false)}>
				CHECKED
			</div>
		)
	} else {
		return (
			<div onClick = {() => setIsChecked(true)}>
				NOT CHECKED
			</div>
		)
	}
}
```
Now when we click on the element, we call a function which sets our "isChecked" variable to be true or false depending on our scenario.

Looking at `reactIntro4/page.js` we see is updated code, and that when we click on a square, its state updates. 

The issue here is that the board component has no idea if 

### Props vs State
Props allow us to pass information from one component to another. 
State is the current information stored only in that component. 

![[Pasted image 20240105094505.png]]
