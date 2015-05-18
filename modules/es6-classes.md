<!--
name: es6-classes
version : "0.1"
title : "ECMAScript 6 Classes"
description : "Understand how classes work in ES6"
homepage : "https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes"
freshnessDate : "2015-05-18"
license : "CC BY-SA 2.5"
-->

<!-- @section -->

## Overview

JavaScript classes are introduced in ECMAScript 6 and are syntactical sugar over JavaScript's existing prototype-based inheritance. The class syntax is **not** introducing a new object-oriented inheritance model to JavaScript. JS classes provide a much simpler and clearer syntax to create objects and dealing with inheritance.

<!-- @section -->

## Defining classes

Classes are in fact [functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions), and just like you can define [function expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function) and [function declarations](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function), the class syntax has the two opponents:

*   [class expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/class) and
*   [class declarations](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/class).

### Class declarations

One way to define a class is a _class declaration_. For that, you need a `class` keyword and a name of the class ("Polygon" here).

```js
class Polygon {
  constructor(height, width) {
    this.height = height;
    this.width = width;
  }
}
```

#### Hoisting

A difference between _function declarations_ and _class declarations_ is that _function declarations_ are hoisted and _class declarations_ are not. You first need to declare your class and then access it, otherwise code like the following will throw a ReferenceError:

```js
var p = new Polygon(); // ReferenceError

class Polygon {}
```

### Class expressions

A _class expression_ is another way to define a class and it can be named or unnamed. If named, the name of the class is local the class body only.


```js
// unnamed
var Polygon = class {
  constructor(height, width) {
    this.height = height;
    this.width = width;
  }
};

// named
var Polygon = class Polygon {
  constructor(height, width) {
    this.height = height;
    this.width = width;
  }
};
```

<!-- @section -->

## Class body and method definitions

The body of a class is the part that is in curly brackets `{}`. This is where you define class members, such as methods or constructors.

### Strict mode

The body of _class declarations_ and _class expressions_ is executed in [strict mode](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Strict_mode).

### Constructor

The [constructor](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes/constructor) method is a special method for creating and initializing an object created with a `class`. There can only be one special method with the name "constructor" in a class. A [SyntaxError](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/SyntaxError) will be thrown, if the class contains more than one occurrence of a `constructor` method.

A constructor can use the `super` keyword to call the constructor of a parent class.

### Prototype methods

See also [method definitions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Method_definitions).


### Static methods

The [static](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes/static) keyword defines a static method for a class. Static methods are called without instantiating their class nor are they callable when the class is instantiated. Static methods are often used to create utility functions for an application.


## Sub classing with `extends`

The `[extends](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes/extends)` keyword is used in _class declarations_ or _class expressions_ to create a class with a child of another class.


## Super class calls with `super`

The [super](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/super) keyword is used to call functions on an object's parent.
