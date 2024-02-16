```jsx
"use client"

// example component:
function Square() {
	return (
		<div className = "w-10 h-10 border-black border-2 "> 
		</div>
	)
}

function RestartButton() {
	return (
		<div>
			<button className = ""> Restart </button>
		</div>
	)
}

function Board() {
	return (
		<div>
			{/* first row */}
			<div className = "flex flex-row" >
				<Square />
				<Square />
				<Square />
			</div>
			{/* end of first row */}

			{/* second row */}
			<div className = "flex flex-row" >
				<Square />
				<Square />
				<Square />
			</div>
			{/* end of second row */}

			{/* third row */}
			<div className = "flex flex-row" >
				<Square />
				<Square />
				<Square />
			</div>
			{/* end of third row */}
			
		</div>
	)
}


export default function reactIntro() {

	return (
		<div>
			View the board below:
			<Board />
			{/* TODO - add your new component here */} 	
		</div>
	)
}

```