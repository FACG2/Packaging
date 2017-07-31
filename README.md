## What is a dependency ?

Dependencies are logical relationships between project activities.

The dependencies of tasks mean that you cannot proceed to another task if the first task is not finished yet.  In project management,  it is important for the team to deliver projects in a sequential manner. Understanding dependencies are crucial to creating a strong project schedule.

## There are four types of dependencies:

* End to start: Activity B can’t start until activity A is finished.
* Start to start: Activity B can only start if activity A has already started.
* End to end: Activity B can only finish if activity A has finished.
* Start to end: Activity B can’t finish until activity A starts.

`The Packaging section looks into the tools you'll use to manage external dependencies.`

## Package Dependencies:
You need to determine whether your package has dependencies on other packages and if any other packages depend on yours.


## NPM: What is a package manager? How does it help with dependencies?

* NPM basically is the package manager for node. It helps with installing various packages and resolving their various dependencies

* NPM is an online repository for the publishing of open-source Node.js projects.

* NPM makes is easy to reuse thousands of existing open source packages that solve a multitude of common problems.

* NPM is automated dependency and package management. This means that you can specify all of your project's dependencies inside your package.json file, then any time you (or anyone else) needs to get started with your project they can just run npm install and immediately have all of the dependencies installed.

## What is package.json, and what does npm init do?

A package.json file affords you a lot of great things:
1.  It serves as documentation for what packages your project depends on.
2. It allows you to specify the versions of a package that your project can use it.
3.  Its way easier to share with other developers.
To create a package.json run:
> npm init
This will initiate a command line that will conclude with the creation of a package.json in the directory you initiated the command.

## How do you use an installed package in your code?
 $ npm install express

 Now you can use this module in your js file as following :
  var express = require('express');

## The difference between dependencies:-

**Global dependencies:**
<br/>
 dependencies that are installed globally outside project folder,, it can be accessed from any project you create.<br />
  To download packages globally you can type this command:<br />
  `npm install -g <package-name>`

** Dependencies:**
<br />
   normal dependencies, or rather ones that you need when running your code I.e: express, angular.<br />
You can type this command to install dependencies locally : <br />
`  npm install <package-name> --save`

**Development Dependencies:**
<br />
   dependencies that you need at some point in the development workflow but not while running your code, I.e: tape, nodemon, etc.
   <br/>
you can type this command to install development dependencies locally:
<br />
  `npm install <package-name> --save-dev`


### When we use each?
- We install packages **globally** if our application doesn’t depends on them. <br />
- We install packages as a **dependencies** if our source code depends on them. <br/>
- We install packages as a **development dependencies** if we use them for development purposes.

It is normally a bad idea to install packages globally because your project depends on some packages that means you should document package names and version in package.json file to guarantee that no errors occurs with your project

## Package files:

### Where does NPM install packages?

npm can install packages in local or global mode. In local mode it installs the package in a node_modules folder in your parent working directory. This location is owned by the current user. Global packages are installed in {prefix}/lib/node_modules/ which is owned by root (where {prefix} is usually /usr/ or /usr/local). This means you would have to use sudo to install packages globally, which could cause permission errors when resolving third-party dependencies, as well as being a security concern.

### Why is it important to make sure that installed packages aren't included in your repositories?
Because of errors that will occur after that, as the packages included in repo will not be listed anymore, or due to availability.


### How do you prevent Git from including these files in your repository?
You have several options:
* Leave a dirty (or uncommitted) .gitignore file in your working dir (or apply it automatically using topgit or some other such patch tool).
* Put the excludes in your $GIT_DIR/info/exclude file, if this is specific to one tree.
* Run git config --global core.excludesfile ~/.gitignore and add patterns to your ~/.gitignore. This option applies if you want to ignore certain patterns across all trees. I use this for .pyc and .pyo files, for example.
