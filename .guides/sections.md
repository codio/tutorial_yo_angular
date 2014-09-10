---
title: IDE Panels
files: []
editable: false
layout: 2-panels-tree

---
It is a really good idea to quickly set up a couple of IDE panels so the tutorial is really easy to follow.

We have set up this Guide for 2 panels.

You should now see something like this

![panels ready](.guides/img/panels-created.png)

To hide the section titles, click on the 'Hamburger' icon and use the next (>>) button at the bottom to move to the next step. 
---
title: MEET YEOMAN
files: []
editable: false
layout: ""

---
![yeoman terminal](.guides/img/yeoman-term.png)

Yeoman is a man in a hat with tricks up his sleeve.

With just a command or two, Yeoman can write boilerplate code for your entire web application or individual pieces like Controllers and Models. Yeoman can fire up a preview web server and watch your files for edits in order to live reload changes and compile your Sass. Yeoman can also run your unit tests, minimize and concatenate your code, optimize images, plus more!

Yeoman comes with three tools for improving your productivity:

[yo](http://yeoman.io/) is a scaffolding tool that offers an ecosystem of framework-specific scaffolds, called generators, that can be used to perform some of the tedious tasks mentioned earlier.

[grunt](http://gruntjs.com/) is used to build, preview and test your project, thanks to help from tasks curated by the Yeoman team and [grunt-contrib](https://github.com/gruntjs/grunt-contrib).

[bower](http://bower.io/) is used for dependency management, so that you no longer have to manually download your front-end libraries.

You can install generators using the [npm](http://npmjs.org/) command and there are over [500 generators](http://yeoman.io/community-generators.html) now available, many of which have been written by the open-source community. Popular generators include [generator-angular](https://github.com/yeoman/generator-angular), [generator-backbone](https://github.com/yeoman/generator-backbone) and [generator-ember](https://github.com/yeoman/generator-ember).

##WHY USE YEOMAN?

With so many great tools available to front-end web developers these days it can sometimes be difficult to understand how they all fit together. Deciding on a workflow that you’re happy with is often a very personal endeavour, but getting started isn’t always easy. Yeoman aims to solve this problem by scaffolding workflows for creating modern webapps, while at the same time mixing in many of the best practices that have evolved within the industry.

##TODAY’S SAMPLE YEOMAN APP: A TODO APP USING ANGULARJS

For those unfamiliar with AngularJS, it is a JavaScript framework for developing dynamic web apps. Angular is what HTML would have been if it had been designed for web apps, instead of static documents. Angular aims to simplify application development by providing high-level features like data-binding and dependency injection (DI).

To dig deeper into the sweet spots of AngularJS, take a look at the detailed [documentation](http://docs.angularjs.org/guide).

The sample web app you'll build will be a Todo app. You will be able to add todos, delete todos, organize your todos using drag and drop, and save todos offline.

![sample app](.guides/img/sample-app.png)
---
title: Opening a Terminal window
files:
  - path: "#terminal"
    action: open
    panel: 0
    ref: ""
editable: false
layout: ""

---
A Terminal window has been opened for you but if you need to open one yourself at any time 

1. Click in the left code panel area
1. Open up a Terminal window to your Codio Box from the 'Tools->Terminal' menu. This should now appear in the left panel. If it's in the right panel, drag the terminal tab across to the left one.

Codio should now look like this:

![terminal panels](.guides/img/panels-term.png)

---
title: Installing Yeoman
files: []
editable: false
layout: ""

---
Now we're ready to get going with the tutorial proper.

Let's install Yeoman. In your terminal window type

`npm install -g yo`

Now sit back and wait. If you were to do this on your laptop on a normal ADSL connection, it would be a LOT slower.
---
title: Installing Yeoman Generators
files: []
editable: false
layout: ""

---
In a traditional web development workflow, you would need to spend a lot of time setting up boilerplate code for your webapp, downloading dependencies, and manually creating your web folder structure. Yeoman generators to the rescue! Generators do the hard work for you by scaffolding out your project. Let’s install a generator for creating AngularJS projects.

#Install an AngularJS generator

You can install Yeoman generators using the [npm](http://npmjs.org/) command and there are over [500 generators](http://yeoman.io/community-generators.html) now available, many of which have been written by the open-source community.

Install [generator-angular](https://www.npmjs.org/package/generator-angular) using this command:

	npm install --global generator-angular@0.9.2
    
This will start to install the Node packages required for the generator. Using `@0.9.2` will request a specific version of the generator.

---
title: Use a Generator to scaffold your App
files: []
editable: false
layout: ""

---
We've used the word "scaffold" a few times but you might not know what that means. Scaffolding, in the Yeoman sense of the word, means generating files for your web app based on your specific configuration requests. In this step, you'll see how Yeoman can generate files specifically for Angular apps — with options for using other external libraries like SASS and Twitter Bootstrap — with minimal effort.

Once a generator has been installed, you will automatically see the screen below (or it can be accessed via the Yeoman interactive menu: `$ yo`.
    
![install angular](.guides/img/yo-install-angular.png)    

###Comments
As you become more familiar with Yo, you might want to run generators directly without the use of the interactive menu:

    $ yo angular    
    
Some generators will also provide optional settings to customize your app with common developer libraries and speed up the initial setup of your development environment.

The AngularJS generator provides options to include use Sass (with Compass) and/or Bootstrap. Enter ‘n’ and ‘y’ respectively to these options.


###Keep calm and carry on
With 'Run the Angular generator' highlighted, press Enter.

![inputs](.guides/img/angular-inputs.png)

Next you are prompted to select what Angular modules you would like to include as well. Angular modules are self-contained JavaScript files with helpful functionality. For example, the ngResource module (angular-resource.js) provides interaction support with RESTful services.

You can deselect options using the spacebar. Let’s roll with the defaults. (So if you have been playing around with the spacebar, make sure that all the modules are marked as green.)

Okay, hit enter once your inputs look like you see above. Yeoman will automatically scaffold out your app, grab your dependencies, and pull in a few useful Grunt tasks for your workflow. After a short wait and a request for you to confirm bower reporting usage statistics it will be ready.

Don't worry if you see a log error like this followed by other errors

    npm ERR!                                                
    npm ERR! Additional logging details can be found in:
    npm ERR!     /home/codio/workspace/npm-debug.log 
    npm ERR! not ok code 0 

If you do see these errors, close the terminal window and re open to then run `bower install`.
---
title: Explore the File Tree
files:
  - path: "#tabs"
    action: close
    panel: 0
    ref: ""
editable: false
layout: ""

---
In the file tree on the left, take a look at what was actually scaffolded. We have:

- **app**: a parent directory for our web application
  - **index.html**: the base html file for our Angular app
  - **404.html**, **favicon.ico**, and **robots.txt:** commonly used web files so you don’t have to create them yourself
  - **fonts**: fonts used in the package
 - **images**: images used in the package
  - **scripts**: our own JS files
  - **scripts/app.js**: our main Angular application code
  - **scripts/controllers**: our Angular controllers
  - **styles**: our CSS files
  - **views**: a place for our Angular templates
- **bower_components**: a home for our JavaScript/web dependencies, installed by Bower
- **Gruntfile.js**, **package.json**, and **node_modules**: configuration and dependencies required by our Grunt tasks
- **test**: a scaffolded out test runner and the unit tests for the project, including boilerplate tests for our controllers.

---
title: Modify Gruntfile.js
files:
  - path: Gruntfile.js
    action: open
    panel: 0
    ref: ""
    lineCount: 0
editable: true
layout: ""

---
To run properly in Codio, you'll want to open up `Gruntfile.js` in the root of your App and search for `localhost` (somewhere around line 70) and change this

    // Change this to '0.0.0.0' to access the server from outside.
    hostname: 'localhost',
    livereload: 35729
        
to this

    // Change this to '0.0.0.0' to access the server from outside.
    hostname: '0.0.0.0',
    livereload: 4000    

Codio leaves all Ports between 1024 and 9999 at your disposal, so we need to modify the livereload port.

Also search for `<%= yeoman.app %>/{,*/}*.html',` (around line 58) to change this:

    files: [
          '<%= yeoman.app %>/{,*/}*.html',
          '.tmp/styles/{,*/}*.css',
          '<%= yeoman.app %>/images/{,*/}*.{png,jpg,jpeg,gif,webp,svg}'
        ]

to this

    files: [
          '<%= yeoman.app %>/{,*/}*.html',
          '<%= yeoman.app %>/scripts/{,*/}*.js',
          '.tmp/styles/{,*/}*.css',
          '<%= yeoman.app %>/images/{,*/}*.{png,jpg,jpeg,gif,webp,svg}'
        ]
        
Also (around line 16) remove the following from the wiredep section:

		options: {
   		cwd: '<%%= yeoman.app %>'
			},
		}


	

---
title: Setting up the Codio menus
files:
  - path: Gruntfile.js
    action: close
    panel: 0
    ref: ""
editable: false
layout: ""

---
Codio has the ability to save you lots of time by configuring the 'Run' menu (cli commands) and the 'Preview' menu. 

Click on 'Configure...' as shown in the Run menu below.

![run menu](.guides/img/run-menu.png)

Now, copy and paste the following code into the code tab to save you the hassle ...

    {
    // Configure your Run and Preview buttons here.

    // Run button configuration
      "commands": {
        "Grunt Serve": "grunt serve",
        "Grunt Test": "grunt test",
        "Grunt Build": "grunt",
        "Grunt Serve:Dist": "grunt serve:dist"
      },

    // Preview button configuration
      "preview": {
        "Yeoman Demo": "http://{{domain}}:9000/"
      }
    }

You will now see that the Run and Preview menus have been updated and look like this ...

![run updated](.guides/img/run-updated.png)
---
title: "Running & Previewing the App"
files:
  - path: .codio
    action: close
    panel: 0
    ref: ""
editable: false
layout: ""

---
##Start Grunt
Right, we are now ready to get Grunt to serve up our content. From the Run menu, select 'Grunt Serve' (If it appears in the upper panel covering the tutorial, then drag it down to the lower panel). 

![menus done](.guides/img/menus-done.png)

This does nothing more than save you the hassle of typing on the command line ...

    grunt serve

You should see your terminal window running `grunt serve`. If there are any issues running Grunt, just run `npm install` from the terminal to make sure all packages got correctly installed.

When Grunt is ready you will see 
`Waiting...` in the terminal

##Preview
Now, from the Preview menu to the right, select 'Yeoman Demo'. Again, this is just a shortcut to ...

    http://{{domain}}:9000/

You should now see the following screen appear in a new browser tab.

![allo allo](.guides/img/allo.png)

---
title: Live Reload
files:
  - path: app/views/main.html
    action: open
    panel: 0
    ref: ""
    lineCount: 0
editable: true
layout: ""

---
With both `grunt serve` still running in the background and the Preview tab still open, open up the file `app/views/main.html` and change some text somewhere. You will notice that the browser tab auto reloads the content.
---
title: Create a new Template to show a ToDo list
files:
  - path: "app/scripts/controllers/main.js, app/views/main.html"
    action: open
    panel: 0
    ref: ""
    lineCount: 0
editable: true
layout: ""

---
###app/views/main.html
First, let's modify our view (views/main.html) to output our todos items as text input fields. Copy and paste the following code into the `app/views/main.html` file (replace everything).

    <div class="container">
      <h2>My todos</h2>
      <p class="form-group" ng-repeat="todo in todos">
        <input type="text" ng-model="todo" class="form-control">
      </p>
    </div>

###app/scripts/controllers/main.js
Now, let's modify the controller script by replacing everything with ...

    'use strict';

    angular.module('workspaceApp')
      .controller('MainCtrl', function ($scope) {
        $scope.todos = ['Item 1', 'Item 2', 'Item 3'];
      });

The [ng-repeat](http://docs.angularjs.org/api/ng.directive:ngRepeat) attribute on the paragraph tag is an [Angular directive](http://docs.angularjs.org/guide/directive) that instantiates a template once per item from a collection. In our case, imagine that the paragraph element and its content is turned into a virtual rubber stamp by adding the ng-repeat attribute. For each item in the todos array, Angular will stamp out a new instance of the `<p><input></p>` HTML.

The [ng-model](http://docs.angularjs.org/api/ng.directive:ngModel) attribute is another Angular directive that works with input, select, textarea and custom controls to create a two-way data binding. In our example, it populates a text input field with the value from the current todo item in the ng-repeat loop.

Your browser should now show something like this

![preview](.guides/img/preview-1.png)
---
title: Adding a ToDo
files:
  - path: app/views/main.html
    panel: 0
    ref: ""
    lineCount: 0
editable: true
layout: ""

---
Let’s implement a way to add new todo items to the list of existing todos within the application.

Modify `app/views/main.html` by adding a form element in between the `<h2>` and `<p>` elements from the previous section. Your views/main.html should now look like this:

    <div class="container">
      <h2>My todos</h2>

      <!-- Todos input -->
      <form role="form" ng-submit="addTodo()">
        <div class="row">
          <div class="input-group">
            <input type="text" ng-model="todo" placeholder="What needs to be done?" class="form-control">
            <span class="input-group-btn">
              <input type="submit" class="btn btn-primary" value="Add">
            </span>
          </div>
        </div>
      </form>
      <p></p>

      <!-- Todos list -->
      <p class="form-group" ng-repeat="todo in todos">
        <input type="text" ng-model="todo" class="form-control">
      </p>
    </div>

This adds a form with a submit button to the top of the page. It utilises another Angular directive, [ng-submit](http://docs.angularjs.org/api/ng.directive:ngSubmit) which we’ll get to next. Return to your browser and the UI should now look similar to this:

![preview](.guides/img/preview-2.png)
---
title: Making the Add button work
files:
  - path: app/scripts/controllers/main.js
    panel: 0
    ref: ""
    lineCount: 0
editable: true
layout: ""

---
If you click the Add button currently, nothing will happen - let’s change that.

`ng-submit` binds an angular expression to the onsubmit event of the form. If no action attribute is applied to the form, it also prevents the default browser behaviour. In our example we’ve added an angular expression of `addTodo()`.

The following `addTodo` function pushes new todo items onto the existing todo items array and then clears the text input field. Let's add the following code inside the existing code

    $scope.addTodo = function () {
      $scope.todos.push($scope.todo);
      $scope.todo = '';
    };

So, your `app/scripts/controllers/main.js` should now look like this  ...

    'use strict';

    angular.module('workspaceApp')
      .controller('MainCtrl', function ($scope) {
        $scope.todos = ['Item 1', 'Item 2', 'Item 3'];
        $scope.addTodo = function () {
          $scope.todos.push($scope.todo);
          $scope.todo = '';
        };
      });

View the app in the browser again. Type some text in the input field for a new todo item and hit the Add button. It will be immediately reflected in your todos list. Here you can see I have added 2 new todos.

**Note**: if you enter in more than one blank todo item, or a todo item with the same name, your todo app will unexpectedly stop working. :( As a fun exercise on your own time, enhance the addTodo function with error checking.

![preview](.guides/img/preview-3.png)
---
title: Adding a Remove Button
files:
  - path: app/views/main.html
    action: open
    panel: 0
    ref: ""
    lineCount: 0
editable: true
layout: ""

---
Let’s now add the ability to remove a todo item. We’ll need to add a new remove button alongside each todo item.

Going back to our view template (app/views/main.html), add a button to the existing `ng-repeat` directive. And to make sure our input field and remove button line up nicely, change the class on the paragraph tag from "form-group" to “input-group”.

Replace the stuff below `<!-- Todos list -->` with this code

    <!-- Todos list -->
    <p class="input-group" ng-repeat="todo in todos">
      <input type="text" ng-model="todo" class="form-control">
      <span class="input-group-btn">
        <button class="btn btn-danger" ng-click="removeTodo($index)" aria-label="Remove">X</button>
      </span>
    </p>

then run your app again, and you should get this ...

![remove](.guides/img/remove-buttons.png)

We introduced a new Angular directive above, [ng-click](http://docs.angularjs.org/api/ng.directive:ngClick). ng-click allows you to specify custom behaviours when an element is clicked. In this instance, we call `removeTodo()` and pass `$index` to the function.

The value of `$index` will be the array index of the current todo item within the ng-repeat directive. For example, the first item will have an array index of 0 and `removeTodo` will be passed the value of 0. Similarly, the last item of a todo list with 5 items will have an array index of 4 and `removeTodo` will be passed a value of 4.

---
title: Making the remove buttons work
files:
  - path: app/scripts/controllers/main.js
    action: open
    panel: 0
    ref: ""
    lineCount: 0
editable: true
layout: ""

---
Let’s now add some logic for removing todo items to our controller. The following `removeTodo` function removes one todo item from the items array using the JavaScript `splice` method at the given `$index` value:

    $scope.removeTodo = function (index) {
      $scope.todos.splice(index, 1);
    };

The complete controller (app/scripts/controllers/main.js) with the new `removeTodo` function is below:

    'use strict';

    angular.module('workspaceApp')
      .controller('MainCtrl', function ($scope) {
        $scope.todos = ['Item 1', 'Item 2', 'Item 3'];
        $scope.addTodo = function () {
          $scope.todos.push($scope.todo);
          $scope.todo = '';
        };
        $scope.removeTodo = function (index) {
          $scope.todos.splice(index, 1);
        };
      });

Now you can use the 'x' buttons to remove items.

One thing you might notice is that although we’re able to add and remove items, we don’t have a way to persist them. Any time we refresh the page our todo items are reset back to the defaults in our todos array hardcoding in `main.js`. 

Don’t worry, we’ll fix this later after we learn more about installing packages with Bower.
---
title: Using Bower to install packages
files:
  - path: "#tabs"
    action: close
    panel: 0
    ref: ""
  - path: "#terminal"
    action: open
    panel: 0
    ref: ""
editable: false
layout: ""

---
Let’s add some order to our list and make it sortable. For this we’re going to use Bower to install the [AngularUI Sortable](https://github.com/angular-ui/ui-sortable) module, a directive component for AngularJS.

We can check what packages we have already installed with:

    $ bower list
    
You should see that you already have packages for angular-cookies, angular-resources, angular-route, plus others. 

#Search for packages

To verify that there are AngularUI packages available, use Bower to search for "angular-ui-sortable":

    $ bower search angular-ui-sortable
    
There is one result for "angular-ui-sortable" so let’s install it along with [jQuery UI](http://jqueryui.com/) as we already have jQuery installed. To save you from searching, the package name for jQuery UI is "jquery-ui".

#Install Packages

Use Bower to install both "angular-ui-sortable" and "jquery-ui":

    $ bower install --save angular-ui-sortable
    $ bower install --save jquery-ui
    
The `--save` option updates the **bower.json** file with dependencies on angular-ui-sortable and jquery-ui. This will save you from having to manually add it to *bower.json* yourself.

If you have multiple packages that you want to install, you can do it in one line:

    $ bower install --save angular-ui-sortable jquery-ui
    
#Confirm Installation

Take a look at your **bower_components** directory just to check that everything is there as expected. You should see folders for "jquery-ui" and "angular-ui-sortable" alongside the previously installed angular packages. If you do not see these new folders immediately, refresh the file tree using the refresh button at the bottom right of the tree
---
title: Make Todos Sortable
files: []
editable: false
layout: ""

---
References to these newly installed dependencies must be added to our **app/index.html** file. You could manually add the AngularUI Sortable module and jQueryUI script files yourself but Yeoman will automate this for you!

Run `grunt serve` again.

You'll see that the script section at the bottom of **app/index.html** has automatically updated to include `jquery-ui/ui/jquery-ui.js` and `angular-ui-sortable/sortable.js`:

    <!-- build:js scripts/vendor.js -->
    <!-- bower:js -->
    <script src="bower_components/jquery/dist/jquery.js"></script>
    <script src="bower_components/angular/angular.js"></script>
    <script src="bower_components/json3/lib/json3.js"></script>
    <script src="bower_components/bootstrap/dist/js/bootstrap.js"></script>
    <script src="bower_components/angular-resource/angular-resource.js"></script>
    <script src="bower_components/angular-cookies/angular-cookies.js"></script>
    <script src="bower_components/angular-sanitize/angular-sanitize.js"></script>
    <script src="bower_components/angular-animate/angular-animate.js"></script>
    <script src="bower_components/angular-touch/angular-touch.js"></script>
    <script src="bower_components/angular-route/angular-route.js"></script>
    <script src="bower_components/jquery-ui/ui/jquery-ui.js"></script>
    <script src="bower_components/angular-ui-sortable/sortable.js"></script>
    <!-- endbower -->
    <!-- endbuild -->
---
title: Using Sortable Module
files:
  - path: "app/views/main.html, app/scripts/app.js"
    action: open
    panel: 0
    ref: ""
    lineCount: 0
  - path: app/index.html
    action: close
    panel: 0
    ref: ""
editable: true
layout: ""

---
**app/scripts/app.js**

IMPORTANT: don't modify `main.js` by mistake. I made this mistake a couple of times setting this all up!

In order to use the Sortable module, we must load it into our application by updating our Angular module definitions in `app/scripts/app.js`. Currently it looks like this:

    'use strict';

    /**
     * @ngdoc overview
     * @name workspaceApp
     * @description
     * # workspaceApp
     *
     * Main module of the application.
     */
    angular
      .module('workspaceApp', [
        'ngAnimate',
        'ngCookies',
        'ngResource',
        'ngRoute',
        'ngSanitize',
        'ngTouch'
      ])
      .config(function ($routeProvider) {
        $routeProvider
          .when('/', {
            templateUrl: 'views/main.html',
            controller: 'MainCtrl'
          })
          .when('/about', {
            templateUrl: 'views/about.html',
            controller: 'AboutCtrl'
          })
          .otherwise({
            redirectTo: '/'
          });
      });


Add the ui.sortable dependency to the array list in the second paramater. Our complete todo module should now look like this:

    'use strict';
	/**
     * @ngdoc overview
     * @name workspaceApp
     * @description
     * # workspaceApp
     *
     * Main module of the application.
     */
    angular.module('workspaceApp', [
        'ngAnimate',
        'ngCookies',
        'ngResource',
        'ngRoute',
        'ngSanitize',
        'ngTouch',
        'ui.sortable'
    ])
      .config(function ($routeProvider) {
        $routeProvider
          .when('/', {
            templateUrl: 'views/main.html',
            controller: 'MainCtrl'
          })
          .otherwise({
            redirectTo: '/'
          });
      });
      
**app/views/main.html**      

Finally, we need to add the `ui-sortable` directive as a `div` wrapper around our `ng-repeat` in `app/views/main.html`:

    <!-- Todos list -->
    <div ui-sortable ng-model="todos">
      <p class="input-group" ng-repeat="todo in todos">
      
Let's also add some inline css in order to show a move cursor so it’s clear that we can move todo items:

    <p class="input-group" ng-repeat="todo in todos" style="padding:5px 10px; cursor: move;">

The full todo list markup looks like this now:

    <!-- Todos list -->
    <div ui-sortable ng-model="todos">
      <p class="input-group" ng-repeat="todo in todos" style="padding:5px 10px; cursor: move;">
        <input type="text" ng-model="todo" class="form-control">
        <span class="input-group-btn">
          <button class="btn btn-danger" ng-click="removeTodo($index)" aria-label="Remove">X</button>
        </span>
      </p>
    </div>
    
Back in the browser, we can now re-order our list by dragging the entries up and down from:

![order1](.guides/img/order1.png) 

to:

![order2](.guides/img/order2.png)
---
title: Testing with Karma and Jasmine
files:
  - path: "#tabs"
    action: close
    panel: 0
    ref: ""
editable: true
layout: ""

---
For those unfamiliar with [Karma](http://karma-runner.github.io/), it is a JavaScript test runner that is test framework agnostic. The Angular generator has two included test frameworks: [ngScenario](https://code.angularjs.org/1.2.16/docs/guide/e2e-testing) and [Jasmine](http://jasmine.github.io/). When we ran `yo angular` earlier in this codelab, the generator scaffolded a **test** directory in the root folder, created a `karma.conf.js` file, and pulled in the Node modules for Karma. We’ll be editing a Jasmine script to describe our tests soon but let’s see how we can run tests first.

`grunt serve` has been terminated for you by the closing of the terminal window.

There is already a grunt task scaffolded out in our `Gruntfile.js` for running tests. It can be executed in one of two ways

1. From the Run menu, select 'Grunt Test' from the drop down list
2. From the cli, run `grunt test`

When you run `grunt test`, you will see some warnings in the Yeoman console. Don’t worry, that’s to be expected right now.

Our tests are currently failing as we haven’t updated the boilerplate test which still references `awesomeThings`. We also need to update the Karma configuration to load the the new Bower components into the browser. Open **`test/karma.conf.js`** and replace the "files" array with:

    files: [
      'bower_components/angular/angular.js',
      'bower_components/angular-mocks/angular-mocks.js',
      'bower_components/angular-animate/angular-animate.js',
      'bower_components/angular-cookies/angular-cookies.js',
      'bower_components/angular-resource/angular-resource.js',
      'bower_components/angular-route/angular-route.js',
      'bower_components/angular-sanitize/angular-sanitize.js',
      'bower_components/angular-touch/angular-touch.js',
      'bower_components/jquery/dist/jquery.js',
      'bower_components/jquery-ui/ui/jquery-ui.js',
      'bower_components/angular-ui-sortable/sortable.js',
      'app/scripts/**/*.js',
      'test/spec/**/*.js'
    ],

---
title: Modify test main.js
files:
  - path: "app/scripts/controllers/main.js, test/spec/controllers/main.js"
    action: open
    panel: 0
    ref: ""
    lineCount: 0
  - path: test/karma.conf.js
    action: close
    panel: 0
    ref: ""
editable: true
layout: ""

---
Next, modify the unit test for your `main.js`. You’ll find the tests scaffolding out in the `test` folder, so open up `test/spec/controllers/main.js`.

Delete the following:

    it('should attach a list of awesomeThings to the scope', function () {
      expect(scope.awesomeThings.length).toBe(3);
    });

And replace that text with the following:

    it('should have no items to start', function () {
      expect(scope.todos.length).toBe(0);
    });

#Open scripts/controllers/main.js.
Remove the 3 items we added earlier from the $scope.todos declaration:

`$scope.todos = [];`

The complete controller (app/scripts/controllers/main.js) should now look like

    'use strict';

    angular.module('workspaceApp')
      .controller('MainCtrl', function ($scope) {
        $scope.todos = [];
        $scope.addTodo = function () {
          $scope.todos.push($scope.todo);
          $scope.todo = '';
        };
        $scope.removeTodo = function (index) {
          $scope.todos.splice(index, 1);
        };
      });

Re-running our tests with grunt test should see our tests passing. Don't worry about the warnings. 

You should see something like this ...

![test run](.guides/img/test-run.png)

Fantastic!

Writing unit tests make it easier to catch bugs as your app gets bigger and when more developers join your team. The scaffolding feature of Yeoman makes writing unit tests easier so no excuse for not writing your own tests! ;)
---
title: Get Ready for Production
files:
  - path: "app/scripts/controllers/main.js, test/spec/controllers/main.js"
    action: close
    panel: 0
    ref: ""
editable: false
layout: ""

---
![yeoman sitting](.guides/img/yeoman-sitting.png)

Ready to show your beautiful todo app to the world? Let’s try to create a production version of our application. We’ll want to lint our code, run our tests, concatenate and minify our scripts and styles to save on those network requests, optimize images if we were using any, compile the output of any preprocessors we’re using and in general make our application really lean. Phew!

Amazingly we can achieve all of this just by running Grunt in one of 2 ways

- from  the Run menu dropdown, select 'Grunt Build'
- from the command line, `grunt`

This command will go through the Grunt tasks and configuration Yeoman has set up for you and create a version of your app we can ship. Give it a minute and you should be presented with a completed build and a report of how long the build took to complete and where time was spent:

Your lean, production-ready application is now available in a dist folder in the root of your project. These are the files that you can put on your server using FTP or any other deployment methods

#Build and preview the production-ready app

Want to preview your production app locally? That’s just another simple grunt command:

- from  the Run menu dropdown, select 'Grunt Serve:Dist'
- from the command line, `grunt serve:dist`

It will build your project and launch a local web server. Yo Hero!
---
title: Make Todos persistent with Local Storage
files:
  - path: "#terminal"
    action: open
    panel: 0
    ref: ""
editable: false
layout: ""

---
Let’s revisit the issue of items not persisting when the browser refreshes.

To easily achieve this, we can use another Angular module called [angular-local-storage](http://gregpike.net/demos/angular-local-storage/demo.html) that will allow us to quickly implement [Local Storage](http://diveintohtml5.info/storage.html). Bower comes to the rescue. Run the following command in the terminal:

    $ bower install --save angular-local-storage

and you'll see something like this ...

![bower install output](.guides/img/bower-install.png)

---
title: Modifying app/index.html for Local Storage
files:
  - path: "#tabs"
    action: close
    panel: 0
    ref: ""
editable: true
layout: ""

---
There are now 4 tutorial steps you'll run through to get persistant storage up and running, so don't start previewing just yet!

Modify `app/index.html` to include the new Angular module by adding the following after the other Angular script tags:

    <script src="bower_components/angular-local-storage/angular-local-storage.js"></script>
    
Re-run `grunt serve` to get some automated magic in your `index.html`.

Open your `index.html` and the scripts should now look like this:

    <!-- build:js scripts/vendor.js -->
    <!-- bower:js -->
    <script src="bower_components/jquery/dist/jquery.js"></script>
    <script src="bower_components/angular/angular.js"></script>
    <script src="bower_components/json3/lib/json3.js"></script>
    <script src="bower_components/bootstrap/dist/js/bootstrap.js"></script>
    <script src="bower_components/angular-resource/angular-resource.js"></script>
    <script src="bower_components/angular-cookies/angular-cookies.js"></script>
    <script src="bower_components/angular-sanitize/angular-sanitize.js"></script>
    <script src="bower_components/angular-animate/angular-animate.js"></script>
    <script src="bower_components/angular-touch/angular-touch.js"></script>
    <script src="bower_components/angular-route/angular-route.js"></script>
    <script src="bower_components/jquery-ui/ui/jquery-ui.js"></script>
    <script src="bower_components/angular-ui-sortable/sortable.js"></script>
    <script src="bower_components/angular-local-storage/angular-local-storage.js"></script>
    <!-- endbower -->
    <!-- endbuild -->
---
title: Modifying app/scripts/app.js for Local Storage
files:
  - path: app/scripts/app.js
    action: open
    panel: 0
    ref: ""
    lineCount: 0
  - path: app/index.html
    action: close
    panel: 0
    ref: ""
editable: true
layout: ""

---
**IMPORTANT**: don't modify `main.js` by mistake. I made this mistake a couple of times setting this all up!

Edit the todo module (app/scripts/app.js) to include the `localStorage` adapter:

    angular.module('workspaceApp', [
        'ngAnimate',
        'ngCookies',
        'ngResource',
        'ngRoute',
        'ngSanitize',
        'ngTouch',
        'ui.sortable',
        'LocalStorageModule'
    ])

While you’re in `app.js`, also configure `localStorageServiceProvider` to use ‘todo’ as a `localStorage` name prefix so your app doesn’t accidently read todos from another app using the same variable names:

    .config(['localStorageServiceProvider', function(localStorageServiceProvider){
      localStorageServiceProvider.setPrefix('ls');
    }])

Our todo module (app/scripts/app.js) should now look like this:

    'use strict';

    /**
     * @ngdoc overview
     * @name workspaceApp
     * @description
     * # workspaceApp
     *
     * Main module of the application.
     */
    angular
      .module('workspaceApp', [
        'ngAnimate',
        'ngCookies',
        'ngResource',
        'ngRoute',
        'ngSanitize',
        'ngTouch',
        'ui.sortable',
        'LocalStorageModule'
        
   		])
      .config(['localStorageServiceProvider', function(localStorageServiceProvider){
        localStorageServiceProvider.setPrefix('ls');
      }])
      .config(function ($routeProvider) {
        $routeProvider
          .when('/', {
            templateUrl: 'views/main.html',
            controller: 'MainCtrl'
          })
          .otherwise({
            redirectTo: '/'
          });
      });
---
title: Modifying app/scripts/controllers/main.js for Local Storage
files:
  - path: app/scripts/controllers/main.js
    action: open
    panel: 0
    ref: ""
    lineCount: 0
  - path: app/scripts/app.js
    action: close
    panel: 0
    ref: ""
editable: true
layout: ""

---
You will also need to update your controller (scripts/controllers/main.js) to declare a dependency on the `localStorage` service. Add `localStorageService` as the second parameter in the callback function.

    'use strict';

    angular.module('workspaceApp')
      .controller('MainCtrl', function ($scope, localStorageService) {
        // (code hidden here to save space)
      });

So now, rather than reading our todos from a static array, we’ll be reading it from Local Storage and then storing it in `$scope.todos` instead.

We’ll also use the angular [$watch](http://docs.angularjs.org/api/ng.$rootScope.Scope#methods_$watch) listener to watch for changes in the value of `$scope.todos`. If someone adds or removes a todo, it will then keep our `localStorage` todos datastore in sync.

Therefore, we need to remove the current `$scope.todos` declaration:

    $scope.todos = ['Item 1', 'Item 2', 'Item 3'];

And replace it with this:

    var todosInStore = localStorageService.get('todos');

    $scope.todos = todosInStore && todosInStore.split('\n') || [];

    $scope.$watch('todos', function () {
      localStorageService.add('todos', $scope.todos.join('\n'));
    }, true);

We now have a controller that is as follows:

    'use strict';

    angular.module('workspaceApp')
      .controller('MainCtrl', function ($scope, localStorageService) {

        var todosInStore = localStorageService.get('todos');

        $scope.todos = todosInStore && todosInStore.split('\n') || [];

        $scope.$watch('todos', function () {
          localStorageService.add('todos', $scope.todos.join('\n'));
        }, true);

        $scope.addTodo = function () {
          $scope.todos.push($scope.todo);
          $scope.todo = '';
        };

        $scope.removeTodo = function (index) {
          $scope.todos.splice(index, 1);
        };

      });

If you look at your app in the browser now you’ll see that there are no items in the todo list. The app is initialising the todos array from `localStorage` and we haven’t given it any todo items yet.

Go ahead and refresh the browser and start adding some items. Then refresh the browser and you'll see everything persisting nicely.
---
title: Checking in Dev Tools
files:
  - path: "#tabs"
    action: close
    panel: 0
    ref: ""
editable: false
layout: ""

---
We can confirm whether our data is being persisted to `localStorage` by checking the Resources panel in Chrome DevTools and selecting "Local Storage" from the lefthand side:

![dev tools](.guides/img/dev-tools.png)

Pat yourself on the back! You just used Yeoman to build a snazzy todo app in no time. Can you imagine doing front-end web development in any other way now?

So to recap, in this section we:

- Scaffolded the boilerplate for an application using `yo`
- Installed dependencies to improve the functionality in our app with `bower`
- Used `grunt serve` to build and preview an interim version of our app. All our edits resulted in a live reload of the page giving us a nice real-time view of what we authored.