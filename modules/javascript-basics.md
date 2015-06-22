<!--
{
"name" : "javascript-basics",
"version" : "0.0.1",
"title" : "JavaScript Basics",
"description" : "JavaScript is a programming language that adds interactivity to your website.",
"homepage" : "https://developer.mozilla.org/en-US/Learn/Getting_started_with_the_web/JavaScript_basics",
"author" : "Mozilla Developer Network",
"freshnessDate" : 2015-04-22,
"license" : "CC BY-SA"
}
-->

<!-- @section -->

# What is JavaScript, really?

JavaScript is a full-fledged dynamic programming language that can be applied to an HTML document and used to create dynamic interactivity on websites. It was invented by Brendan Eich, co-founder of the Mozilla project, the Mozilla Foundation and the Mozilla Corporation.

You can do pretty much anything with JavaScript. You'll start small with simple features such as adjusting layouts, making things happen when buttons are clicked, carousels, and image galleries — but eventually as you get more experienced with the language you'll be able to create games, animated 2D and 3D graphics, full blown database-driven apps, and more.

JavaScript itself is a fairly compact language, but it is very flexible, and developers have written a lot of tools that sit on top of the core JavaScript language to provide you with access to a huge amount of extra functionality with very little effort. These include:

* Application Programming Interfaces (APIs) built into web browsers that allow you to do anything from dynamically create HTML and set CSS styles, to grab and manipulate a video stream from the user's web cam, or generate 3D graphics and audio samples.
* 3rd party APIs to allow developers to incorporate functionality in their sites from other properties, such as Twitter or Facebook.
* 3rd party frameworks and libraries you can apply to your HTML to allow you to rapidly build up sites and applications.

<!-- @section -->

# A "hello world" example

The above section sounds really exciting, and so it should — JavaScript is one of the most exciting web technologies, and if when you start to get good at it your websites will enter a new dimension of power and creativity.

HOWEVER, JavaScript is a bit more complex to get comfortable with than HTML and CSS, and you'll have to start small, and keep working at it in tiny regular steps. To start off with, we'll show you how to add some really basic JavaScript to your page, to create a "hello world!" example (the standard in basic programming examples.)

> **Important**: If you haven't been following along with the rest of our course, [download this example code](https://github.com/mdn/beginner-html-site-styled/archive/gh-pages.zip) and use it as a starting point.

1. First, go to your test site and create a new file called main.js. Save it in your scripts folder.
2. Next, go to your index.html file and enter the following element on a new line just before the closing `</body>` tag: `<script src="scripts/main.js"></script>`
3. This is basically doing the same job as the <link> element for CSS — it applies the JavaScript to the page, so it can have an effect on the HTML (and CSS, and anything else on the page).
4. Now add the following code to the main.js file:

    ```javascript
    var myHeading = document.querySelector('h1');
    myHeading.innerHTML = 'Hello world!';
    ```

5. Now make sure the HTML and JavaScript files are saved, and load index.html in the browser. You should see something like the following:

![Hello World](https://mdn.mozillademos.org/files/9543/hello-world.png)

> **Note**: The reason we've put the `<script>` element near the bottom of the HTML file is that HTML is loaded by the browser in the order it appears in the file. If the JavaScript is loaded first and it is supposed to affect the HTML below it, it might not work, as the JavaScript would be loaded before the HTML it is supposed to  work on. Therefore, near the bottom of the page often the best strategy.

<!-- @task, "text" : "Edit you `main.js` file to change the heading.  Paste the content of your `main.js` here.", "hasDeliverable": true -->

## What happened?

So your heading text has been changed to "Hello world!" using JavaScript. We did this by first using a function called `querySelector()` to grab a reference to our heading, and store it in a variable called `myHeading`. This is very similar to what we did in CSS using selectors — we want to do something to an element, so we need to first select it.

After that, we set the value of the `myHeading` variable's' `innerHTML` property (which represents the content of the heading) to "Hello world!".

<!-- @multipleChoice -->

Why is it good to put the script-tag near the bottom of the HTML file?

- [ ] It is easier to find
- [ ] It makes JS load faster
- [X] It ensures the proper processing of the page

<!-- @end -->

<!-- @section -->

# Language basics crash course

Let's explain just some of the basic features of the JavaScript language, to give you some more understanding of how it all works. Better yet, these features are common to all programming languages. If you can understand these fundamentals, you should be able to make a start programming just about anything!

> **Important**: In this article, try entering the example code lines into your browser console to see what happens. For more details on browser consoles, see our [page on browser developer tools](https://developer.mozilla.org/en-US/Learn/Discover_browser_developer_tools).

<!-- @REMOVETHISlink, "url" : "https://developer.mozilla.org/en-US/Learn/Discover_browser_developer_tools", "task" : "After reading this page, inspect the CSS of the Outlearn webpage." -->

## Variables

Variables are containers that you can store values in. You start by declaring a variable with the var keyword, followed by any name you want to call it:

```javascript
var myVariable;
```

> **Note**: All lines in JS must end with a semi-colon, to indicate that this is where the line ends. If you don't include these, you can get unexpected results.  
>
> **Note**: JavaScript is case sensitive — myVariable is a different variable to myvariable. If you are getting problems in your code, check the casing!

After declaring a variable, you can give it a value:

```javascript
myVariable = 'Bob';
```

You can retrieve the value by just calling the variable by name:

```javascript
myVariable;
```

You can do both these operations on the same line if you wish:

```javascript
var myVariable = 'Bob';
```

After giving a variable a value, you can later choose to change it:

```javascript
var myVariable = 'Bob';
myVariable = 'Steve';
```

Note that variables have different data types:

| Variable | Description  | Example |
|---------|---------------|-------------|
| String  | A string of text. To signify that the variable is a string, you should enclose it in quote marks.                            | var myVariable = 'Bob';  |
| Number  | A number. Numbers don't have quotes around them.                                                                             | var myVariable = 10;  |
| Boolean | A True/False value. true/false are special keywords in JS, and don't need quotes.  | var myVariable = true;   |
| Array   | A structure that allows you to store multiple values in one single reference.     | var myVariable = [1, 'Bob', 'Steve', 10]; Call each member of the array like this: myVariable[0], myVariable[1], etc. |
| Object  | Basically, anything. Everything in JavaScript is an object, and can be stored in a variable. Keep this in mind as you learn. |  |

So why do we need variables? Well, variables are needed to do anything interesting in programming. If values couldn't change, then you wouldn't be able to do anything dynamic, like personalize a greeting message to the user visiting your site, or change the image displayed in an image gallery, etc.

## Comments

You can put comments into JavaScript code, just like you can in CSS. In JavaScript, single line comments look like this:

```javascript
// This is a comment
```

But you can also use CSS_style multi line comments:

```javascript
/*
 This is a multi line
 comment
*/
```

## Operators

An operator is basically a mathematical symbol that can act on two values (or variables) and produce a result. In the below table you can see some of the most simple operators, along with some examples to try out in the browser console.

| Operator | Description  | Symbol | Example |
| -------- | --------  | -------- | -------- |
| add/concatenation          | Used to add two numbers together, or glue two strings together.                                                                              | +     | 6 + 9; "Hello " + "world!";                                                                                                                                                                                                                                   |
| subtract, multiple, divide | These do what you'd expect them to do in basic math.                                                                                         | -,* , / | 9 - 3;8 * 2; // multiply in JS is an asterisk9 / 3;                                                                                                                                                                                                           |
| assignment operator        | You've seen this already: it assigns a value to a variable.                                                                                  | =     | var myVariable = 'Bob';                                                                                                                                                                                                                                       |
| Identity operator          | Does a test to see if two values are equal to one another, and returns atrue/false (boolean) result.                                         | ===   | var myVariable = 3;myVariable === 4;                                                                                                                                                                                                                          |
| Negation, not equal        | Often used alongside the Equality operator, the negation operator is the JS equivalent of a logical NOT — it turns a true into a false, etc. | !,!== | The basic expression istrue, but the comparison returns falsebecause we've negated it:var myVariable = 3;!myVariable === 3;Here we are testing "ismyVariableNOT equal to 3". This returnsfalse, because it IS equal to 3.var myVariable = 3;myVariable !== 3; |

There are a lot more to explore, but this will do for now. See [Expressions and operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators) for a complete list.

> **Note**: Mixing data types can lead to some strange results when performing calculations, so be careful that you are referring to your variables correctly, and getting the results you expected. For example enter "35" + "25" into your console. Why do you not get the result you expected? Because the quote marks turn the numbers into strings — you've ended up with the strings concatenated together, and not numbers added. If you enter 35 + 25, you'll get the correct result.

## Conditionals

Conditionals are code structures that allow you to test whether an expression returns true or not, and then run different code depending on the result. The most common form of conditional is called if ... else. So for example:

```javascript
var iceCream = 'chocolate';
if (iceCream === 'chocolate') {
  alert('Yay, I love chocolate ice cream!');
} else {
  alert('Awwww, but chocolate is my favorite...');
}
```

The expression inside the if ( ... ) is the test — this uses the identity operator (as described above) to compare the variable iceCream with the string chocolate to see if the two are equal. If this comparison returns true, run the first block of code. If not, skip that code and run the second block of code after the else statement.

## Functions

Functions are a way of encapsulating functionality that you want to reuse, so you can call that function with a single function name, and not have to write the entire code out again and again each time you use it. You have already seen some functions above, for example:

```javascript
var myVariable = document.querySelector('h1');
```

```javascript
alert('hello!');
```

These functions are built into the browser for you to use whenever you like.

If you see something that looks like a variable name, but has brackets — () — after it, it is probably a function. Functions often take arguments — bits of data they need to do their job. These are put inside the brackets, and separated by commas if there is more than one.

For example, the alert() function makes a pop-up box appear inside the browser window, but we need to give it a string as an argument to tell it what message it is supposed to write in the pop-up box.

The good news is that you can define your own functions — in this next example we write a simple function that takes two numbers as arguments and multiples them together:

```javascript
function multiply(num1,num2) {
  var result = num1 * num2;
  return result;
}
```

Try running the above function in the console, then try using your new function a few times, e.g.:

```javascript
multiply(4,7);
multiply(20,20);
multiply(0.5,3);
```
> **Note**: The return statement tells the browser to return the result variable out of the function so it is available to use. This is necessary because variables defined inside functions are only available inside those functions. This is called variable scoping (read [more on variable scoping here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Values,_variables,_and_literals#Variable_scope).)

Create a new function `divide()` that takes as input two numbers `num1` and `num2` and returns `num1/num2`.

<!-- @task, "text" : "Create a function divide().", "hasDeliverable" : true -->

## Events

To create real interactivity on a website, you have to use events — these are code structures that listen out for things happening to the browser, and then allow you to run code in response to those things happening. The most obvious example is the click event, which is fired by the browser when the mouse clicks on something. To demonstrate this, try entering the following into your console, then clicking on the current web page:

```javascript
document.querySelector('html').onclick = function() {
    alert('Ouch! Stop poking me!');
}
```

There are many ways to attach an event to an element; here we are selecting the HTML element and making its onclick handler property equal to an anonymous function (a function without a name) that contains the code we want to run when the click event occurs.

Note that

```javascript
document.querySelector('html').onclick = function() {};
```

is equivalent to

```javascript
var myHTML = document.querySelector('html');
myHTML.onclick = function() {};
```
It's just a shorter way to write it.

<!-- @section -->

# Supercharging our example website

Now we've reviewed a few basics of JavaScript, let's add a couple of cool basic features to our example site to give you some first steps into what is possible.

## Adding an image changer

In this section we'll add another image to our site, and add some simple JavaScript to change between the two when the image is clicked on.

- First of all, find another image that you'd like to feature on your site. Make sure it is the same size as your first image, or as close as possible.
- Save the image in your `images` folder.
- Go to your `main.js` file, and enter the following JavaScript (if your hello world JavaScript is still there, delete it):
    ```javascript
    var myImage = document.querySelector('img');
    myImage.onclick = function() {
        var mySrc = myImage.getAttribute('src');
        if(mySrc === 'images/firefox-icon.png') {
          myImage.setAttribute ('src','images/firefox2.png');
        } else {
          myImage.setAttribute ('src','images/firefox-icon.png');
        }
    }
    ```
- Save all files and load index.html in the browser. Now when you click the image, it should change to the other one!

So here, we are storing a reference to our image element in the myImage variable. Next, we make this variable's onclick event handler property equal to an anonymous function. Now, every time this image element is clicked:

1. We retrieve the value of the image's src attribute.
2. We use a conditional to check whether the src value is equal to the path to the original image:
  1. If it is, we change the src value to the path to the 2nd image, forcing the other image to be loaded inside the `<image>` element.
  2. If it isn't (meaning it must already have changed), we change the src value back to the original image path, to flip it back to what it was originally.

## Adding a personalized welcome message

Next we will add another bit of code, to change the page's title to include a personalized welcome message when the user first navigates to the site. This welcome message will persist when the user leaves the site and then comes back. We will also include an option to change the user and therefore the welcome message anytime it is required.

1. In index.html, add the following line just before the `<script>` element:
  ```html
  <button>Change user</button>
  ```
2. In `main.js`, add the following code at the bottom of the file, exactly as written — this grabs references to the new button we added and the heading, and stores them in variables:
  ```javascript
  var myButton = document.querySelector('button');
  var myHeading = document.querySelector('h1');
  ```
3. Now add the following function to set the personalized greeting — this won't do anything yet, but we'll use it later on:
  ```javascript
  function setUserName() {
    var myName = prompt('Please enter your name.');
    localStorage.setItem('name', myName);
    myHeading.innerHTML = 'Mozilla is cool, ' + myName;
  }
  ```
  This function contains a `prompt()` function, which brings up a dialog box a bit like `alert()` does; the difference is that `prompt()` asks the user to enter some data, and stores that data in a variable when the dialog OK button is pressed. In this case, we are asking the user to enter their name. Next, we call on an API called localStorage, which allows us to store data in the browser, and retrieve it later on. We use localStorage's `setItem()` function to create and store a data item called 'name', and set its value to the myName variable that contains the name the user entered. Finally, we set the innerHTML of the heading to a string, plus the user's name.

4. Next, add this if ... else block — we could call this the initialization code, as it sets up the app when it first loads:
  ```javascript
  if(!localStorage.getItem('name')) {
    setUserName();
  } else {
    var storedName = localStorage.getItem('name');
    myHeading.innerHTML = 'Mozilla is cool, ' + storedName;
  }
  ```
  This block first uses the negation operator (logical NOT) to check whether the name data item exists — if it doesn't exist, the `setUserName()` function is run to create it. If it already exists (i.e. the user set it when they previously visited the site), we retrieve the stored name using `getItem()` and set the innerHTML of the heading to a string, plus the user's name, the same as we did inside `setUserName()`.

5. Finally, put the below onclick event handler on the button, so that when clicked the `setUserName()` function is run. This allows the user to set a new name whenever they want by pressing the button:
  ```javascript
  myButton.onclick = function() {
    setUserName();
  }
  ```


<!-- @multipleChoice -->

In step 4. above, the if-else construction ensures that:

- [X] The item `name` is not used before it is defined
- [ ] The item `name` will not be stored locally
- [ ] The item `name` cannot be changed later

<!-- @end (multipleChoice) -->

Now when you first visit the site, it'll ask you for your user name then give you a personalized message. You can then change the name any time you like by pressing the button. As an added bonus, because the name is stored inside localStorage, it persists after the site is closed down, so the personalized message will still be there when you open the site up again!

<!-- @section -->

# Conclusion

If you have followed all the instructions in this article, you should end up with a page that looks something like this (you can also [view our version here](http://mdn.github.io/beginner-html-site-scripted/)):

![Hello World Completed](https://mdn.mozillademos.org/files/9539/website-screen-scripted.png)

If you get stuck, you can always compare your work with our [finished example code on Github](https://github.com/mdn/beginner-html-site-scripted/blob/gh-pages/scripts/main.js).

Here, we have only really scratched the surface of JavaScript. If you have enjoyed learning about it and want to go deeper with your studies, go to our [JavaScript Guide](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide).
