+++
date = "2016-07-28"
draft = false
title = "Introduction to AngularJS"
categories = ["AngularJS"]
tags = ["Google", "HTML","MVC","jQuery"]
author = "Yuvraj Gupta"

+++
AngularJS is a toolset for building the framework most suited to your application development. It is fully extensible and works well with other libraries. 

HTML is great for declaring static documents, but it falters when we try to use it for declaring dynamic views in web-applications. AngularJS lets you extend HTML vocabulary for your application. The resulting environment is extraordinarily expressive, readable, and quick to develop.

Other frameworks deal with HTML’s shortcomings by either abstracting away HTML, CSS, and/or JavaScript or by providing an imperative way for manipulating the DOM. Neither of these address the root problem that HTML was not designed for dynamic views.

Key Introductory Points of AngularJS:-

* Developed and maintained by Google
* MVC Javascript Framework for Rich Web Application Development
* Hot new front-end JavaScript framework
* Rapidly develop powerful, responsive web apps
* Philosophy similar to jQUery
* Simplicity
* Enhance HTML, work with it not around it
* Testable, maintainable, extendable

**History of AngularJS**

Developed in 2009 by MiškoHevery and Adam Abrons for commercial purposes, but later Angular as an open-source library.

Hevery, who works at Google, continues to develop and maintain the library. Version 1.0 released in December 2012.

What about WebToolkit?

WebToolkit compiles Java down to JavaScript and was used by the Google extensively. With the rise of HTML5, CSS3, and JavaScript, Google is changing directions.

**Structure of AngularJS**

It follows the MVC Architecture i.e. Model, View and Controller.

**Model**
The data

**Controller**
The behavior
Modifying / updating the models

**View**
The interface
How the data is presented to the user

Model and Controller uses JavaScript where as View uses HTML to present the data.

**Models**

* Properties on the Controller’s $scope object
* Standard JavaScript values
* Can be used to separate the application into parts
* Application module can include the other modules by listing them as dependencies

**Controller**

* Function that takes at least one parameter: $scope
* Function is a constructor
* Ex: function MyCtrl($scope) { … }

**$scope**

* It is a JavaScript object
* Contains data (i.e. models) and methods (i.e. functions)
* Can add own properties
$scope.<my new property> = <value>;
* The $scope variable – Link your controllers and view

**Views**

* Make use of special ng attributes (directives) on the HTML elements
*  ng-app
	* Determines which part of the page will use AngularJS
	* If given a value it will load that application module
* ng-controller
	* Determines which Javascript Controller should be used for that part of the page.
* ng-model
	* Determines what model the value of an input field will be bound to
	* Used for two-way binding

**Dependency Injection**

* Pass the modules and services that you need as parameters
* In the previous case $scope is a service that will be injected
* Can be passed as an array of strings to the controller function as well
* Prevents errors when performing modification

**$http**

* Used to handle Ajax calls
* Wrappers around jQuery

**Features of AngularJS**

* Templating
* Databinding
* Routing
* Follows MVC Architecture
* Server-Side Communication
* Dependency Injection
* Extensibility ("Directives")
* Allows for testing
* Deep Linking (Map URL to route Definition)

**Why AngularJS**

* **Backed by Google- Actively maintained**

  * Angular is built and maintained by dedicated Google engineers.

  * AngularJS came about to standardize web application structure and provide a future template for how client-side apps should be developed.
Because AngularJS is built by Google, you can be sure that you are dealing with  efficient and reliable code that will scale with your project.

This means you not only have a large open community to learn from, but you also have skilled, highly-available engineers tasked to help you get your Angular questions answered.

* **Comprehensive feature set**

  * Angular a complete solution for rapid front-end development.
 
  * No other plugins or frameworks are necessary to build a data-driven web application.

* **REST Easy**

  * Restful actions are quickly becoming the standard for communicating from the server to the client.

  * In one line of JavaScript, you can quickly talk to the server and get the data you need to interact with your web pages.

* **Extends HTML**

  * Most websites built today are a giant series of \<div\> tags.

  * You need to create extensive and exhaustive CSS classes to express the intention of each object in the DOM.

  * With Angular, you can operate your HTML like XML, giving you endless possibilities for tags and attributes.

  * Angular accomplishes this via its HTML compiler and the use of directives to trigger behaviors based on newly created syntax you write.

* **Makes HTML your Template**

  * You can quickly grasp the bracket syntax of Angular's templating engine, because it's just HTML.

  * Angular traverses the DOM for these templates, which house the directives mentioned above.

  * The templates are then passed to the AngularJS compiler as DOM elements, which can be extended, executed or reused.

  * This is a key property which allows direct manipulation and extension of the DOM tree.

* **Enterprise-level Testing**

  * AngularJS requires no additional frameworks or plugins, including testing.

  * Easy in learning Angular's unit-testing API which guides you through executing your tests in as close to the actual state of your production application as possible.
