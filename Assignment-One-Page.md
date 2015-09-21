# This was an in class assignment to create a basic ionic framework application.

When the assignment is completed, you will have a basic application with a single view and a single controller.

### Step One: Create `index.html` and add the following code

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
<body>
</body>
</html>
````

This includes the default `css` for ionic framework and the `ionic.bundle.js` is a bundle of all of the files you need to build a basic Ionic Framework application using the angularJS framework. 

REMEMEBER: there is no need to include angularjs in your application

### Step Two: Create `app.js` and add the following code

````Javascript
// this will be the javascript file to hold
// all of the code for my first app
// create the angular module
angular.module('firstApp',['ionic']);
````
The code above creates the angular JS module that the application's code will be included in. Notice the name `firstApp`, that is the name of the module that must be included in the `index.html` file with the `ng-app` attribute.. Quick refresher

````HTML
<html ng-app="firstApp" >
````

Now that the `app.js` file is created, we need to include the `app.js` file in the `index.html` file. This is accomplished by using the HTML script tag. Make the following edits to your `index.html` file, add this code right below the existing `script` tag that is in the `index.html` `<head>` tag.

````HTML
<!-- include the javascript app.js source file -->
<script src="app.js"></script>
````

### Final Source of working application

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
<body>
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