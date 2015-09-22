## This was an in class assignment to add a controller and $scope variables to basic application.

When the assignment is completed, you will have a basic application with a single view and a single controller. This is part two of the assignment, please see [Part One]() before going forward.

In part two, we will add a controller and include a `$scope` variable in the `controller`; by adding the variable to the `$scope` it makes the variable accessible in the page.

### Step One: Modify `index.html` to include the Controller

To get the `index.html` page to recognize the controller, we will add an attribute to the html element `<body>`; the attribute in `ng-controller`. We add the `ng-controller` attribute and provide the name of the controller. In this example, we will call the controller `FirstController`

````HTML
<!DOCTYPE html>
<html  ng-app="firstApp">
<head>
    <meta charset="utf-8">
    <meta name="viewport" content="initial-scale=1, maximum-scale=1, 
                   user-scalable=no, width=device-width">
    <link href="http://code.ionicframework.com/1.0.0/css/ionic.min.css" rel="stylesheet">
    <script src="http://code.ionicframework.com/1.0.0/js/ionic.bundle.js">
    </script>
</head>
<body ng-controller="FirstController"> <!-- ADDED ATTRIBUTE HERE -->
</body>
</html>
````

### Step Two: Modify `app.js` to include the controller of the application. 

The `controller` contains the business logic, variable and data that pertains to the `$scope` of the element that the `controller` was assigned to.

Since the `angular.module` returns an object, we can add the controller to the module that is returned using this syntax.

````Javascript
// this will be the javascript file to hold
// all of the code for my first app
// create the angular module
angular.module('firstApp',['ionic'])
.controller('FirstController', function($scope) {
});
````
Notice the removal of the semi-colon at the end of the angular.module and the period added to the start of the `controller` definition.

The code above creates the angular JS module that the application's code will be included in; and then adds an angular `controller` named `FirstController` to the angularJS application `firstApp`.

### Step Three: Modify `app.js` to include a $scope variable in the newly created controller 

the `$scope` is provided to the controller for assigning objects and functions that can be accessible in the view, or `html` page associated with the specific `controller`. 

To add a variable do the following
````Javascript
$scope.myName = "Aaron Saunders"
````
Since remember that this is javascript and we can create javascript object using JSON format, we can also do the following to create a `$scope` variable `fullName` with a proper `first` and `last`.
````Javascript
$scope.fullName = {
   "first" : "Aaron",
   "last"  : "Saunders"
};
````
Now that we have created the `$scope` variables, let add them to in the view.

### Step Four: Modify `index.html` to show the value of the $scope variable

When including the `$scope` variables in the page, there is no need to include `$scope` just include the name of the variable enclosed in the angulars brackets `{{}}` which tell angular to evaluate the contents of the brackets. In the code below I added the lines to display the variable created in the controller

````HTML
<body ng-controller="FirstController"> <!-- ADDED ATTRIBUTE HERE -->
   <p>this should display Aaron Saunders -   {{ name }}</p>
   <p>
   this should display Aaron -   {{ fullName.first }} <br/>
   this should display Saunders -   {{ fullName.last }}
   </p>
</body>
````

Final Source of Working Application
===
`index.html`
````HTML
<!DOCTYPE html>
<html  ng-app="firstApp">
<head>
    <meta charset="utf-8">
    <meta name="viewport" content="initial-scale=1, maximum-scale=1, 
                   user-scalable=no, width=device-width">
    <link href="http://code.ionicframework.com/1.0.0/css/ionic.min.css" rel="stylesheet">
    <script src="http://code.ionicframework.com/1.0.0/js/ionic.bundle.js"></script>
    <!-- include the javascript app.js source file -->
    <script src="app.js"></script>
</head>
<body ng-controller="FirstController"> <!-- ADDED ATTRIBUTE HERE -->
   <p>this should display Aaron Saunders -   {{ name }}</p>
   <p>
   this should display Aaron -   {{ fullName.first }} <br/>
   this should display Saunders -   {{ fullName.last }}
   </p>
</body>
</html>
````

`app.js`
````Javascript
// this will be the javascript file to hold
// all of the code for my first app
// create the angular module
angular.module('firstApp',['ionic']);
````