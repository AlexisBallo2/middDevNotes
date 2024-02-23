
# Setup
## 1: Make a new folder for your project

Using the file browser on your computer, create a new folder. Open that folder in vscode:
![[Pasted image 20240220182746.png]]
There should be no files in the folder

## 2: Create first HTML file

Create a new index.html file. and past in the following code:
```html
<!DOCTYPE html>
<html>
	<head>
	</head>
	
	<body>
		Hello world.
	</body>
</html>
```

This will be the basic outline that you will use for all plain html files. 

![[Pasted image 20240220183045.png]]


## 3: Install and start the "Live Server" extension

![[Pasted image 20240220182837.png]]

Then start the server by clicking "go live" in the bottom right of your screen
![[Pasted image 20240220183248.png]]


If not using vscode, you can run a new server in the directory by opening up a new terminal, navigating to the directory that you just created, and running "python3 -m http.server 8080"

Now a new tab should open with the words "Hello world"
![[Pasted image 20240220183330.png]]
# HTML basics

## The \<body></body\>

### Tags
Here you put all the content you want visible. We can think of this as a normal text editor, but with special "tags" that modify text differently. 

Ex if we replace "hello world" with <h1\></h1\>
![[Pasted image 20240223105414.png]]
Notice how the text is different
These are "semantic tags" and describe what is often enclosed in them.
Ex other semantic tags
- h1 (first subheading)
- h2 (second subheading)
- h3 (third subheading)
- p (paragraph)

## The \<head></head\>
Here you will declare file imports, file attributes, and other things. 

# CSS Basics

## Inline styles

We can directly add styles to an html page using inline css. To do this, we add the styles as an **attribute** to one of our html tags:
```html
<h2 style = "background-color:red;">
	Hello world.
</h1>
```

![[Pasted image 20240223110004.png]]

## Common styles
Common st

## Linking CSS to HTML
Create a new file "index.css" in the same directory as your html file. 
![[Pasted image 20240223105604.png]]

In your html file, add this line to the 'head' tag:
```html
<link rel="stylesheet" type="text/css" href="styles.css" /> 
```

Your head tag should look like this:
```html
<head>
	<link rel="stylesheet" type="text/css" href="styles.css" /> 
</head>
```

## 


