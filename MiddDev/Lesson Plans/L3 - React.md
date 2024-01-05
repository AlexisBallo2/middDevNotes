Now that we understand the basics of JS, we can start to learn how to display information using our JS framework. For running our frontend, the framework uses "React." Today we will teach you how to begin thinking in React. 

# Thinking in React

### Components
React is special because of its use of "components" - or little bits of code we will reuse. A component may be a dropdown list that we use on multiple pages - rather than coding it 4 times, we can code it once and import it into the 4 different files. 

React is build around declaring a hierarchy for our designs. For example, consider the example below:
![[Pasted image 20240104201649.png]]
Here we have multiple components:
1. ORANGE - Container component. Houses our search and display components and determines where they should be displayed relative to each other. 
2. BLUE - Search component. Packages up the searching functionality and separates it from the code to display the searched items. 
3. GREEN - Display component. Only designed to show the items. 

### Try it yourself: 
In `app/reactIntro/page.js` you will find a `reactIntro` function which returns a div with "hello", and another component `C1`. As declared above, `C1` returns a similar div, but returns "testing". When we navigate to https://localhost:3000/reactIntro we see them composed and acting as 1 component. 

> Challenge:
> Make a new component titled `C2` (note that the component name MUST BEGIN WITH AN UPPERCASE LETTE)
### Props vs State


