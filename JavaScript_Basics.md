> JavaScript is a programming language that adds interactivity to your website (e.g. games, responses when buttons are pressed or data entered in forms, dynamic styling, animation). This article helps you get started with this exciting language and gives you an idea of what is possible.

## What is JavaScript, really?

JavaScript is a full-fledged dynamic programming language that can be applied to an HTML document and used to create dynamic interactivity on websites. It was invented by Brendan Eich, co-founder of the Mozilla project, the Mozilla Foundation and the Mozilla Corporation.

You can do pretty much anything with JavaScript. You'll start small with simple features such as adjusting layouts, making things happen when buttons are clicked, carousels, and image galleries — but eventually as you get more experienced with the language you'll be able to create games, animated 2D and 3D graphics, full blown database-driven apps, and more.

JavaScript itself is a fairly compact language, but it is very flexible, and developers have written a lot of tools that sit on top of the core JavaScript language to provide you with access to a huge amount of extra functionality with very little effort. These include:

* Application Programming Interfaces (APIs) built into web browsers that allow you to do anything from dynamically create HTML and set CSS styles, to grab and manipulate a video stream from the user's web cam, or generate 3D graphics and audio samples.
* 3rd party APIs to allow developers to incorporate functionality in their sites from other properties, such as Twitter or Facebook.
* 3rd party frameworks and libraries you can apply to your HTML to allow you to rapidly build up sites and applications.

## A "hello world" example

The above section sounds really exciting, and so it should — JavaScript is one of the most exciting web technologies, and if when you start to get good at it your websites will enter a new dimension of power and creativity.

HOWEVER, JavaScript is a bit more complex to get comfortable with than HTML and CSS, and you'll have to start small, and keep working at it in tiny regular steps. To start off with, we'll show you how to add some really basic JavaScript to your page, to create a "hello world!" example  ([the standard in basic programming examples](http://en.wikipedia.org/wiki/%22Hello,_world!%22_program).)

> Important: If you haven't been following along with the rest of our course, [download this example code](https://github.com/mdn/beginner-html-site-styled/archive/gh-pages.zip) and use it as a starting point.

1. First, go to your test site and create a new file called `main.js`. Save it in your `scripts` folder.
2. Next, go to your `index.html` file and enter the following element on a new line just before the closing `</body>` tag:
```
<script src="scripts/main.js"></script>
```
3. This is basically doing the same job as the `<link>` element for CSS — it applies the JavaScript to the page, so it can have an effect on the HTML (and CSS, and anything else on the page).
4. Now add the following code to the `main.js` file:
```
var myHeading = document.querySelector('h1');
myHeading.innerHTML = 'Hello world!';
```
5. Now make sure the HTML and JavaScript files are saved, and load `index.html` in the browser. You should see something like the following:
<img alt="" src="https://mdn.mozillademos.org/files/9543/hello-world.png" style="width: 806px; height: 236px; display: block; margin: 0px auto;" />

> **Note**: The reason we've put the `<script>` element near the bottom of the HTML file is that HTML is loaded by the browser in the order it appears in the file. If the JavaScript is loaded first and it is supposed to affect the HTML below it, it might not work, as the JavaScript would be loaded before the HTML it is supposed to work on. Therefore, near the bottom of the page often the best strategy.

# What happened?

So your heading text has been changed to "Hello world!" using JavaScript. We did this by first using a function called `querySelector()` to grab a reference to our heading, and store it in a variable called `myHeading`. This is very similar to what we did in CSS using selectors — we want to do something to an element, so we need to first select it.

After that, we set the value of the `myHeading` variable's `innerHTML` property (which represents the content of the heading) to "Hello world!".
