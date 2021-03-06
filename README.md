# gulp-sass-bourbon-bower-jade
A boilerplate for front-end development using Gulp, SCSS with Bourbon, Bower &amp; Jade

Front-End Workflow
===================
![Toolbelt](https://github.com/Kzai/gulp-sass-bourbon-bower-jade/blob/master/toolbelt.jpg)


Provides the basis for a **Front-End** development workflow, complete with some basic **Gulp** watchers and tasks to speed things up, **Bower** for front-end dependency management and a few **node** modules for development dependencies. Also employs transpilers to work with **Bourbon** and **Jade** during development and outputs CSS (verbose and minified), HTML and third-party libraries to a dist directory, ready for handover. With this workflow, 99% of the work happens in the `src` directory. Gulp tasks compile to `dist` where minor tweaks can be done to get things as you'd like (script order etc). 

----------


<i class="icon-cog"></i> Setup Development Environment
-------------
**Development Dependencies**

`npm install`


**Front-end Dependencies**

`bower init` and complete bower.json with your project's details which will overwrite existing.

Workflow specifies that front-end dependencies are installed with Bower with `bower install --save [packageName]`.

After each Bower install, run `gulp bower` to pipe these required front-end dependencies to `./dist`.

For devDependencies like testing, `--save-dev`, obvs. 

Check `bower.json` for details.

> **Notes:**

> - Bower dependencies install to `./src/components` directory, as specified in `.bowerrc` file.
> - Bower packages install a lot of junk that may be useful in development but normally just the core files of the library (CSS, JS) are required for production. A Gulp task takes care of this and pipes core `.js` files (jQuery, for example) from your Bower dependencies in `./src/components` to the `./dist/assets/js/lib`. You can replicate the Gulp task to do this for any `.css` files that come with your Bower dependencies too, but you'll probably want to handle these using SCSS (and the associated Gulp transpilation task) to make sure your CSS is in the order you want.
> - ToDo: Create/edit a Gulp task that will insert links to Bower components in the index.jade file in specified order.
> - ToDo: Create/edit a Gulp task that will edit the paths to these dependencies in `./dist/assets/js/lib`.


###Gulp Tasks

Basic Gulp tasks have been created to serve as a starting point to automate your processes.
These include file watchers, compiling `.js` scripts, `.css`, compressing images etc.

