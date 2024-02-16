Now that we understand the basics of JS, we can start to learn how to display information using our JS framework. For running our frontend, the framework uses "React." Today we will teach you how to begin thinking in React...

# 1 JSX

## 1.1 Structuring

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
## 1.2 Functions and Logic
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
# 2 Thinking in React

## 2.1 Components
React is special because of its use of "components" - or little bits of code we will reuse. A component may be a dropdown list that we use on multiple pages - rather than coding it 4 times, we can code it once and import it into the 4 different files. 

React is build around declaring a hierarchy for our designs. For example, consider the example below:
![[Pasted image 20240104201649.png]]
Here we have multiple components:
1. ORANGE - Container component. Houses our search and display components and determines where they should be displayed relative to each other. 
2. BLUE - Search component. Packages up the searching functionality and separates it from the code to display the searched items. 
3. GREEN - Display component. Only designed to show the items. 

We can break it even further down: 
![[Pasted image 20240105093618.png]]

## 2.2 Example: 

<div style = "background-color: #fff8a6; text-align:center; border-radius: 10px; padding: 10px 0 10px 0;">File: app/reactIntro1/page.js <br/> Server: <a href = "https://localhost:3000/reactIntro1">https://localhost:3000/reactIntro1</a></div>

The code in `app/reactIntro1/page.js` shows a `reactIntro` component that returns a div (notice that this is the default export, Next.js always renders only this one, all other functions must be called specially by the default export). Inside the div is the text "Hello" and another component `C1`. Component `C1` returns a div with the text "testing":
```jsx
function C1() {
	return (
		<div>
			Testing
		</div>
	)
}

export default function reactIntro() {

	return (
		<div>
			Hello
			<C1 />
		</div>
	)
}
```

This produces the expected behavior:
![[Pasted image 20240215223217.png|100]]
The server compiles the components into a single element. We can modify our code like so to produce this same output: 
```jsx
export default function reactIntro() {

	return (
		<div>
			Hello
			<div>
				Testing
			</div>
		</div>
	)
}

```

In this way, components are like VARIABLES, that we can type once and use in many places. 
## 2.3 Try it yourself: 

<div style = "background-color: #fff8a6; text-align:center; border-radius: 10px; padding: 10px 0 10px 0;">File: app/reactIntro2/page.js <br/> Server: <a href = "https://localhost:3000/reactIntro2">https://localhost:3000/reactIntro2</a></div>

<div style = "background-color: #d7ffc2; border-radius: 10px; padding: 10px 10px 10px 10px;">
<span style = "font-size:20px">Challenge</span><br/>
In `app/reactIntro2/page.js` you will find the "Board" component with a row of "Square" components. 
	<ul>
		<li>
			Add a new component that displays a "restart" button
		</li>
		<li>
			Complete the tic tac toe board
		</li>
	</ul>
</div>

## 2.3.1 Solution
The solution can be found here: [[ReactIntro2]]
# 3 State

Now that we have the basic board, we can start managing user input. 
Lets keep track of the board by using a simple 9 value array. 
For example an empty board would be represented as:
[0,0,0,   0,0,0,   0,0,0]
This state:
![[Pasted image 20240116112231.png|100]]

would be represented as:
[0,1,1    1,-1,0,     0,0,1]

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

<div style = "background-color: #fff8a6; text-align:center; border-radius: 10px; padding: 10px 0 10px 0;">File: app/reactIntro3/page.js <br/> Server: <a href = "https://localhost:3000/reactIntro3">https://localhost:3000/reactIntro3</a></div>


The issue here is that the board component has no idea wha the state of each square is, and the memory of the squares are all isolated from each other - therefore we have no way to tell when a player has completed a winning move. We can fix this by moving the state "up" and passing the state as props.  

## 3.1 Props vs State

Props allow us to pass information from one component to another. 
State is the current information stored only in that component. 

![[Pasted image 20240105094505.png]]

Lets move the "checked" state of the square to the board, and pass the state (the "checked" status) to each square as a prop. 

<div style = "background-color: #fff8a6; text-align:center; border-radius: 10px; padding: 10px 0 10px 0;">File: app/reactIntro4/page.js <br/> Server: <a href = "https://localhost:3000/reactIntro4">https://localhost:3000/reactIntro4</a></div>

In this file (`reactIntro4/page.js`) we lift the state to the board, and pass the props to the components.

The state is now controlled in the Board component: 
```jsx
const [checkState, setCheckState] = useState([0,0,0,0,0,0,0,0,0])
```
Therefore we can get the ith status by looking at checkState[i] 

The Square component only takes the integer for the "isChecked" value, so we can receive that prop and render accordingly:
```jsx
function Square({isChecked, setSquare}) {

	if (isChecked) {
		return (
			<div onClick = {() => setSquare()} className = "w-10 h-10 border-black border-2 "> 
				X
			</div>
		)
	} else {
		return (
			<div onClick = {() => setSquare()} className = "w-10 h-10 border-black border-2 "> 
			</div>
		)
	}
}
```

We will also add a function to handle modifying a square:
```jsx
const updateState = (i) => {
	let tempBoardState = [...checkState]
	if(tempBoardState[i] === 0){
		tempBoardState[i] = 1
	} else {
		tempBoardState[i] = 0
	}
	setCheckState(tempBoardState)
}
```

<div style = "background-color: #d7ffc2; border-radius: 10px; padding: 10px 10px 10px 10px;">
<span style = "font-size:20px">Challenge</span><br/>
In app/reactIntro4/page.js the Square component is modified to take 2 props: an "isChecked" variable and a "setSquare" function. When the square is clicked, the "setSquare" function is executed. You are also given an "updateState" function in the board component and a new "checkState" and "setCheckState" state array. 
	<ul>
		<li>
			Modify the rest of the calls of the Square component to receive the "isChecked" and "updateState" props. Example call on line 55 
		</li>
	</ul>
</div>

### 3.1.1 Solution
The solution can be found here: [[ReactIntro4]]
We will modify all calls of the Square component to look like so:
```jsx
<Square isChecked = {checkState[0]} setSquare = {() => {updateState(0)}} />
```


## 3.2 Adding complexity

<div style = "background-color: #fff8a6; text-align:center; border-radius: 10px; padding: 10px 0 10px 0;">File: app/reactIntro5/page.js <br/> Server: <a href = "https://localhost:3000/reactIntro5">https://localhost:3000/reactIntro5</a></div>

Now that all squares are pulling from the Board state, and we are able to update the board state when we click on a Square, lets add the idea of turns. 

<div style = "background-color: #d7ffc2; border-radius: 10px; padding: 10px 10px 10px 10px;">
<span style = "font-size:20px">Challenge</span><br/>
In app/reactIntro5/page.js we want to not just have a square be "on" or "off", but to have it be "X", "O", or "off". To achieve this we need a different value to be shown based on the value of "isChecked", and a "turn" state so we know what the new value in the array will be. 
	<ul>
		<li>
			Add a "turn" state to the Board component. -1 = "X", 1 = "O"
		</li>
		<li>
			Whenever we update the state of the board, flip the turn state
		</li>
		<li>
			In the Square component, render an "X" when isChecked == -1, an "O" when isChecked == 1, and nothing when isChecked == 0
		</li>
	</ul>
</div>

### 3.2.1 Solution

The full solution can be found here: [[ReactIntro5]]

In the Board component we will use a simple useState hook:
```jsx
const [turn, setTurn] = useState(-1)
```

In our function to update the board state, we modify the function to set the value to the current turn value:
```jsx
const updateState = (i) => {
	let tempBoardState = [...checkState]
	if(tempBoardState[i] === 0){
		tempBoardState[i] = turn
	} else {
		tempBoardState[i] = 0
	}
	setCheckState(tempBoardState)
	setTurn(-1 * turn)
}
```

We also modify our Square component to render different things depending on the value of isChecked:
```jsx
const updateState = (i) => {
	let tempBoardState = [...checkState]
	if(tempBoardState[i] === 0){
		tempBoardState[i] = turn
	} else {
		tempBoardState[i] = 0
	}
	setCheckState(tempBoardState)
	setTurn(-1 * turn)
}
```
# 4 useEffect

The useEffect hook allows us to write code that runs only when we specifically tell it to. 
The basic structure is:
```jsx
useEffect(()=> {
	// do something
},[paramsList])
```
We see it is a function as a variable followed by an array. 

The code will run EVERYTIME something in the array changes. For example if we have 

```jsx
useEffect(()=> {
	console.log(number)
},[number])
```
Then every time we increment number, it will be console logged. Be careful not to change the "number" variable within the useEffect block, as it will cause an infinite loop. 


<div style = "background-color: #fff8a6; text-align:center; border-radius: 10px; padding: 10px 0 10px 0;">File: app/reactIntro6/page.js <br/> Server: <a href = "https://localhost:3000/reactIntro6">https://localhost:3000/reactIntro6</a></div>

in `reactIntro6/page.js` we see this code: 

```jsx
function Square({number, isChecked, setSquare}) {
	useEffect(() => {
		console.log("reRendered!", number )
	}, [isChecked])
	...
	
```

Here, every time "isChecked" changes, we will console log the square number!

We will later use this to only check the board state for winning combinations after a move is made. 