# Introduction to JavaScript

## I. Overview
If you are comfortable with HTML and CSS, you are already familiar with the basics of getting browser layout engines to display your web pages the way you want them to look.
To add even more control over the appearance of the page, as well as other capabilities, you will need to utilize the JavaScript programming language.

JavaScript was originally created by Brendan Eich of Netscape Communication in 1995, and was re-implemented as JScript in Microsoft Internet Explorer in 1996.
Standardization of the language began in 1996 when Netscape submitted the language to Ecma International (at the time, "European Computer Manufacturers Association").
The term JavaScript is actually trademarked by the Oracle Corporation, so the standardized name of the scripting language that runs in web browsers is ECMAScript.


## II. History of JavaScript
You can read the evolution of JavaScript & ECMAScript here:

- https://en.wikipedia.org/wiki/JavaScript
- https://en.wikipedia.org/wiki/ECMAScript

In this course we are mostly concerned about the version of JavaScript that was standardized in 2009 called ECMAScript 5 (aka ES5), and the latest version (ES6) which was finalized in 2015. 
Because ES6 has not been full adopted by all of the browser vendors, we will only be using a small subset of its features.

You can read peruse the full ES6 standard here - https://tc39.github.io/ecma262/ - but it's not very exciting reading.

A nice list of new ES6 language features is here - http://es6-features.org/ - and it will make more sense as you get comfortable with the JavaScript programming language.

There is a helpful ES6/Browser compatibility table here - https://kangax.github.io/compat-table/es6/

## III. Get started!

Let's go ahead and build a JavaScript "Hello World" application - it looks like this:

### hello-1.html

```
<!DOCTYPE html>
<html lang="en">
<head>
   <meta charset="utf-8" />
   <title>Hello-1</title>
   <script>
      console.log("Hello world!");
   </script>
</head>
<body>

</body>
</html>
```

Note that JavaScript directives are contained in a &lt;script> tag. 

Go ahead and save this web page in an HTML file named hello-1.html and load it into the Chrome web browser - which will be the browser we will use in all of our examples going forward. 

The line of code - `console.log("Hello world!");` - doesn't do anything in the web browser window, but will instead be visible in the JavaScript console. We can see this console by right-clicking in the browser window and choosing **Inspect**. After that, choose the **Console** tab.

![The JavaScript Console](_images/console-1.jpg)


## IV. The JavaScript console is interactive
This console also contains an interactive interpreter where you can run JavaScript commands. At the prompt, type `Date()` to create and see a new date from the `Date` object, and `Math.random()` to get a random number from the `Math` object.

![The JavaScript Console](_images/console-2.jpg)

## V. Declaring variables and constants
We use the `const` keyword to declare constant values (that do not change), and the `let` keyword to declare variables. Note the we do not specify any *type* information when we declare the variable, and the JavaScript interpreter will infer the data type of the variable based on what value we assign to it.

Note that `const` and `let` are both part of the ES6 standard (you are learning some ES6 already!) and are well-supported by the browsers.

### hello-2.html
```
<!DOCTYPE html>
<html lang="en">
<head>
   <meta charset="utf-8" />
   <title>Hello-2</title>
   <script>
     console.log("Hello world!");
     const answer = 42;
     // string concatenation
     console.log("The answer to everything is " + answer); 
	
     let x = 1;
     let y = 1;
     let sum = x + y;
     // string templating (ES6 only)
     console.log(`${x} + ${y} is ${sum}`); 
	</script>
</head>
<body>
</body>
</html>
```

![The JavaScript Console](_images/console-3.jpg)

- Note above when strings are added to numbers, we get back a concatenated string. 
- Also see the *String Templating* used above - that's a newer ES6 feature that is more powerful than simple string concatenation. 
Note the backtick `` ` `` symbol is used to denote the string, and `${}` encloses the variable names.


## VI. Viewing error messages

The console will display error meessages that will help you debug your code. Let's produce an error by attempting to change the value of the `answer` constant above.
Add this line of code - `answer = 43;` - right before the closing &lt;script> tag, and then reload the page. You should see an error:

![The JavaScript Console](_images/console-4.jpg)

## VII. JavaScript "Primitive" Data Types

The 5 common built-in "primitive" data types in JavaScript are: `Number`, `String`, `Boolean`, `Undefined` (a value has never been defined) and `Null` (the intentional absence of a value).

(ES6 has also added the `Symbol` type, which we probably won't need to use in this course.)

JavaScript is a *loosely typed* (aka *dynamic*) language. That means you don't have to declare the *type* of a variable ahead of time. The type will be determined automatically by the engine while the program is being run. 
That also means that the same variable can contain data of different types.

### hello-3.html
```
<!DOCTYPE html>
<html lang="en">
<head>
   <meta charset="utf-8" />
   <title>Hello-3</title>
   <script>
     // 5 fundamental JavaScript types
     let sum = 99; // Number
     let name = "Fred"; //String
     let isLoggedIn = false; // Boolean
     let userName = undefined;
     let data = null;

     // We can later change what type a variable contains
     sum = "Joe"; // sum now contains a String
     name = 50; // name now contains a Number

     console.log(sum); // "Joe"

</script>
</head>
<body>
</body>
</html>
```

## VIII. JavaScript "Built-in" Objects

JavaScript also contains a number of built-in objects that we can use. There is `Object`, which is a starting point for our own customized objects, as well as `Array`, `Date`, `Math`, and others. The "primitive" types above also can be treated like objects and have properties and methods that can be called on them.

### hello-4.html
```
<!DOCTYPE html>
<html lang="en">
<head>
   <meta charset="utf-8" />
   <title>Hello-4</title>
   <script>
     // Common JS Objects
     let colors = ["red","green","blue"]; // Array literal
     let person = {name:"Fred",age:20};   // Object literal
     let month = new Date().getMonth(); 
     let age = Math.round(20.999);

     console.log(colors[0]);
     console.log(person.name);
     console.log(month);
     console.log(age);

     // Treat "primitives" like objects
     let sum = 99.980809809;             // Number
     let name = "Fred";                  // String
     let isLoggedIn = false;             // Boolean
     let userName = undefined;
     let data = null;

     console.log(sum.toFixed(2));
     console.log(name.length);
     console.log(isLoggedIn.toString());

</script>
</head>
<body>
</body>
</html>
```
