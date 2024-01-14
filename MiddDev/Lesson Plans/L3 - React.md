Now that we understand the basics of JS, we can start to learn how to display information using our JS framework. For running our frontend, the framework uses "React." Today we will teach you how to begin thinking in React. 

# JSX

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
![[Pasted image 20240110160715.png|100]]
would be represented as:
[0,1,0    -1,-1,1,     1,0,0]

State allows us to manage variables and the "state" of the application at a point in time. The most common way we will manage state is with the `useState` hook provided to us by our nextjs framework. Consider the code block below

```js
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
```js
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
