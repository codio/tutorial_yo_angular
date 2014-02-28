@annotation:tour installation
#Installing Yeoman
Let's start off by getting the panels set up in a nice way for the tutorial.

1. Create a new panel by selecting 'View->Panels->Split horizontal' from the menu
1. Open up a Terminal window to your Codio Box from the 'Tools->Terminal' menu
1. Note you can drag the Terminal tab into any other panel
1. Adjust the vertical splitter to suit your display

Let's get started with the real stuff by installing Yeoman. In your terminal window type

    npm install -g yo

Now site back and wait. If you were to do this on your laptop on a normal ADSL connection, it would be a LOT slower.

Once the Yeoman installation is complete, you can check the version that was installed

    yo --version && bower --version && grunt --version

Press the navigation button at the top of this panel to move to the next step.

@annotation:tour
#Installing Yeoman Generators
In a traditional web development workflow, you would need to spend a lot of time setting up boilerplate code for your webapp, downloading dependencies, and manually creating your web folder structure. Yeoman generators to the rescue! Generators do the hard work for you by scaffolding out your project. Let’s install a generator for creating AngularJS projects.

Yeoman comes with a handy interactive menu, to access this menu run:

    $ yo

![run yeoman](img/yo.png)

Use your keyboard’s up / down arrow keys to navigate the menu and hit enter when ‘Install a generator’ is highlighted.

Next we need to search for a generator to install. A search for `angular` will find many generators contributed by various members of the Yeoman open source community. In this instance we want to install the ‘generator-angular’ generator.

![angular generator](img/yo-angular.png)

With generator-angular selected, hit enter to start installing the generator. This will start to install the Node packages required for the generator.

Alternatively, if you already know the name of the generator you want to use, the generator can be installed using npm as follows:

    $ npm install -g generator-angular


@annotation:tour scaffold
#Use a Generator to scaffold your App

Once a generator has been installed it can be accessed via the Yeoman interactive menu:

    $ yo
    
![install angular](img/yo-install-angular.png)    
    
As you become more familiar with Yo, you might want to run generators directly without the use of the interactive menu:

    $ yo angular    
    
Some generators will also provide optional settings to customize your app with common developer libraries and speed up the initial setup of your development environment.

The AngularJS generator provides options to include use Sass (with Compass) and/or Twitter Bootstrap. Enter ‘n’ and ‘y’ respectively to these options.

![inputs](img/angular-inputs.png)

Next you are prompted to select what Angular modules you would like to include as well. Angular modules are self-contained JavaScript files with helpful functionality. For example, the ngResource module (angular-resource.js) provides interaction support with RESTful services.

You can deselect options using the spacebar. Let’s roll with the defaults. (So if you have been playing around with the spacebar, make sure that all the modules are marked as green.)

Okay, hit enter once your inputs look like you see above. Yeoman will automatically scaffold out your app, grab your dependencies, and pull in a few useful Grunt tasks for your workflow. After a short wait it will be ready.

@annotation:tour files
#Explore the File Tree
In the file tree on the left, take a look at what was actually scaffolded. We have:

- **app**: a parent directory for our web application
  - **index.html**: the base html file for our Angular app
  - **404.html**, **favicon.ico**, and **robots.txt:** commonly used web files so you don’t have to create them yourself
  - **bower_components**: a home for our JavaScript/web dependencies, installed by Bower
  - **scripts**: our own JS files
  - **app.js**: our main application code
  - **controllers**: our Angular controllers
  - **styles**: our CSS files
  - **views**: a place for our Angular templates
- **Gruntfile.js**, **package.json**, and **node_modules**: configuration and dependencies required by our Grunt tasks
- **test** and **karma.conf.js/karma-e2e.conf.js**: a scaffolded out test runner and the unit tests for the project, including boilerplate tests for our controllers.

@annotation:tour mods1
#Modify some files
To run properly in Codio, you'll want to open up `Gruntfile.js` and search for 'localhost' (somewhere around line 64) and change this

    // Change this to '0.0.0.0' to access the server from outside.
    hostname: 'localhost',
    livereload: 10467
        
to this

    // Change this to '0.0.0.0' to access the server from outside.
    hostname: '0.0.0.0',
    livereload: 4000    
    


@annotation:tour mods2
#Preview your App
Codio has the ability to save you lots of time by setting up cli and preview menus. Open up the Run menu at the top (see image below) and select 'Configure...'.

![run menu](img/run-menu.png)

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

![run updated](img/run-updated.png)

@annotation:tour preview
#Running the App
##Start Grunt
Right, we are now ready to get Grunt to serve up our content. From the Run menu, select 'Grunt Serve' (If it appears in the upper panel covering the tutorial, then drag it down to the lower panel). 

This does nothing more than save you the hassle of typing on the command line ...

    grunt serve

You should see your terminal window running `grunt serve`. 

##Preview
Now, from the Preview menu to the right, select 'Yeoman Demo'. Again, this is just a shortcut to ...

    http://{{domain}}:9000/




