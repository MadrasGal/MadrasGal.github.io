---
layout: post
title:      "JavaScript Essentials - understanding ‘scope’, ‘hoisting’ and ‘context’ "
date:       2018-10-01 06:07:11 -0400
permalink:  javascript_essentials_-_understanding_scope_hoisting_and_context
---



# What is ‘Scope’?

Scope defines the availability of a declared variable or a method within a program. In other words, it helps us answer the question - is this particular variable or method still available to the program (even after the compiler has executed the line of code that declares the variable or method), or is there a need to redeclare/redefine the variable or method. 

In general --  

•	A variable or method having a ‘global scope’ is available everywhere in the program (and does not require to be redeclared or redefined).  

•	If a variable or method is declared inside a function or a block, its scope becomes ‘local’ i.e. its availability is limited to the function or block within which it is created.

•	Variables created without a const, let, or var always have a ‘global scope’.

# What is ‘Hoisting’?

Generally, we understand that globally scoped variables and functions should be defined at the top of the program, as the compiler reads the code from the top to the bottom. ‘Hoisting’ expands the scope of a variable or method that has been declared/defined later in the program and makes it available as if it were to have been declared or defined at the top of the program. 

The above does not apply when the keywords let or const are used.  Variables and constants declared with let or const are not hoisted.

It is important to remember that ‘hoisting’ only applies to variable declarations; and not to variable assignments. In other words, while the JavaScipt engine will hoist or hold the declared variable in memory and make it available to the program, its ‘value’ will not be hoisted.  

To further understand this concept, let’s look at the below piece of code. 

```
1.		function myFunc () {
2.	  console.log(hello);
3.	 
4.	  var hello = 'World!';
5.	}
6.	// => undefined
```


We see that the variable ‘hello’ has been defined on line 4 of the program and holds the value ‘World’. 

Applying the concept of hoisting, when the JavaScript engine runs line 2 of the code, the variable ‘hello’ is available to the program as if it were to have been declared at the top of the program. Therefore, the program does not throw up an error. However, the value of ‘hello’ will not be hoisted and therefore, it returns ‘undefined’.

# What is ‘Context’? 

Context is determined by how a function is invoked. JavaScript provides a keyword ‘this’ that refers to an object. However, the value of this object is to be determined ‘in context’ and can be quite confusing! 

In general -- 

•	Outside of any function, ‘this’ refers to the global object. In web browsers, ‘this’ is the window.

•	Inside an object method, ‘this’ refers to the object that received the method call

•	Inside a standalone function, even one inside a method, ‘this’ will default to the global object

•	Arrow functions don't define their own ‘this’ like standard functions do.



