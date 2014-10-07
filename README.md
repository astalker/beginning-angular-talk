## ![Angular JS](AngularJS-large.png) 

### Beginning Angular JS and what we learned when using it


### Alasdair Stalker @alasdairstalker
### ![Airpoint](logo.gif) 

--
### So what is Angular JS

* A framework?
* A library?
* A plugin?

--
### Angular JS

* A Javascript toolset
* Extends HTML
* Allows you to create Single Page Applications

--
### Why would you need Angular JS?

* Javascript and HTML are flawed by themselves
* Demand for the Client to do the heavy lifting
* Testing Client side code is difficult
* Client side tools/libraries are disparate
* SPA's are complex

--
### What does Angular JS offer?

* Two way data bindings
* Dependency Injection
* Testability
* Modularity
* Promises

--
### Some tools

* Karma test runner for unit tests
* Protractor for End to End tests
* Batarang Chrome debugger plugin

--
### How do I get started?

* Download the JS file from angularjs.org
* Clone it from GitHub
* Bootstrap it using Yeoman
* Use a Mean stack e.g. mean.io

```
<div ng-app></div>
```

--
### Controllers

* Controllers provide the business logic for the view
* They can inherit from other controllers
* They define what the scope for a view is

--
  
### A controller is a function
```
function PhoneListCtrl($scope) {
  $scope.phones = [
    {"name": "Nexus S",
     "snippet": "Fast just got faster with Nexus S."},
    {"name": "Motorola XOOM™ with Wi-Fi",
     "snippet": "The Next, Next Generation tablet."},
    {"name": "MOTOROLA XOOM™",
     "snippet": "The Next, Next Generation tablet."}
  ];
}
```
--

### Add your controller to a Module

```
var myApp = angular.module('myApp', []);

myApp.controller('PhoneListCtrl', PhoneListCtrl);
```

Initialise your App by declaring your new module

```
<div ng-app="myApp"></div>
```

* Modules can list other modules as their dependencies

--
### Inline controller style

```
var myApp = angular.module('myApp', []);

myApp.controller('PhoneListCtrl', function($scope) {
  $scope.phones = [
    {'name': 'Nexus S',
     'snippet': 'Fast just got faster with Nexus S.'},
    {'name': 'Motorola XOOM™ with Wi-Fi',
     'snippet': 'The Next, Next Generation tablet.'},
    {'name': 'MOTOROLA XOOM™',
     'snippet': 'The Next, Next Generation tablet.'}
  ];
});
``` 
--
### Connecting a controller with a view

A controller can be linked to a view by using ng-controller

```
<div ng-controller="myController"></div>
```

--
### Connecting a controller with a view

Or by defining it in a route for your App (using ng-view)

```
<div ng-view></div>

angular.module('myApp').
  config(['$routeProvider', function($routeProvider) {
    $routeProvider
      .when('/my-page', {
        templateUrl : 'views/myPage.html',
        controller  : 'myController'
      })
})
```
--
### Scope

The Scope binds the Model and the View together

* It is the context of the model
* They can inherit
* Directives can create their own scope
* Whenever the scope changes the view is updated

--
### Views

A view is An HTML file or template presented to the user

* Where you declare what directives you want to use
* HTML combined with Angular expressions
* Automatic dirty checking in forms avoids model get and set
* Can often tell you exactly what is meant to be happening

--
### View - functions and variables

Calling a function on scope

```
<div ng-click="doSomething()"></div>
```

Displaying a variable in the view

```
<div ng-bind="myVariable"></div>
<div>{{myVariable}}</div>
```
--
### Views - objects

Displaying our list of phones

```
<ul>
  <li ng-repeat="phone in phones">
    {{phone.name}}
    <p>{{phone.snippet}}</p>
  </li>
</ul>
```
--
### Bindings make many tasks simpler

* A task that can be realised entirely in the view

```
<div ng-class="{toggleOn: toggle}">Item</div>

<a ng-click="toggle=!toggle">Toggle</a>
```

* Note, if a scope variable doesn't exist Angular will create it

--
### Directives

A piece of code that accomplishes a specific task
 
* Handles the behaviour of the UI 
* Helps to eliminate Javascript specific CSS
* Allows for effective reusable components
* Fully testable
* Perfect for validation

--
### What we learned using Angular JS

* Directives are great at describing the UI
* TDD is accessible on the client side 
* Acceptance testing with Protractor makes life better
* Module pattern and inheritance is effective
* Inherited scope is not easy
* Directives can take a bit of learning

--
### Resources

* angularjs.org
* ng-conf.org
* yearofmoo.com
* github.com/angular/angular.js
* ng-newsletter.com

--
### Questions


 
