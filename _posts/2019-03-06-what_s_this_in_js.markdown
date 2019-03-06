---
layout: post
title:      "What’s ‘this’ in JS?"
date:       2019-03-06 10:28:22 -0500
permalink:  what_s_this_in_js
---



This article explores the concept of ‘this’ in JS and its scope and usage. 


## Concept of 'this' in JS  

Simply put, ‘this’ refers to an object in JS. The scope and value of this object depends on the context within which it is called. 

For eg., lets look at this piece of code:

```
let dog = {
	name: “Katie”,
	breed: “Golden Retriever”,
	speak: function () {
		return this;
	}
}
```
 
Inside of the speak function, ‘this’ refers to the dog object on which the function is called. Therefore, the function speak(), returns the dog object. If we called this.name, it would return Katie, which is the name property of the dog object.  

The context of ‘this’ changes when we assign dog.speak() to a new variable. For eg:

`let newDogFunction = dog.speak``

When we assign the dog.speak function to a new variable, we removed its original context which referred to the dog object. Therefore, when we call newDogFunction, ‘this’ now refers to the global object or what is known as ‘Window’, and not the dog object. 

## Arrow functions

Traditionally, functions in JavaScript were written as follows:

```
function oldJSFunction() = {
	Return “Hello old JS function”
}
```

ES6 introduced a new syntax for writing functions in JavaScript, called ‘arrow functions’. Simply put, arrow functions are a syntactically compact alternative to traditional functions. An example of an arrow function would be:

```
newFunction = () => {
	return “Hello new JS function”
}
```

The new ES6 syntax for functions introduced changes in our earlier understanding of the scope and context of ‘this’. Unlike traditional functions, arrow functions do not have their own ‘this’ object. Instead, they take the context of ‘this’ from the scope of where these functions are defined.

## Arrow functions and ‘this’

Going back to our newDogFunction, if we now defined it using arrow functions, we would be able to return the dog object. For example,

```
dog.fetchMethod = function () {
	const newDogFunction = () => {
		return this;
	}
	newDogFunction()
}
```

As we saw earlier, the arrow function adopts the context in which it was defined. Therefore, when we call dog.fetchMethod, this now has a context for “this”, which is the dog object.




