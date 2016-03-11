# Glass Spider
A lightweight and flexible Drupal 8 base theme designed for GUI-based SASS compiling. 

## Mission
Glass Spider aims to be a solution that brings SASS-based theme development to a wide variety of skill levels. SASS setup is optimized for GUI compilers like Koala or Prepro. It's flexible – use Bootstrap or Breakpoint or anything you want (or don't) as long as it's SASS. Glass Spider also aims to utilize documentation-driven development. Too many tools, especially Drupal themes, lack great documentation, but Glass Spider will be built around a core of documentation at every step.

### Why?
I started this because I work with and teach developers and designers with a wide variety of skills and backgrounds who develop on different operating systems. When teaching SASS I often ended up spending hours teaching students how to set up a virtual machine in order to run command line compilers like Compass or Libsass. Students often ended up frustrated because they were spending so much time honing their setup rather than actually working with SASS.

I had worked with Aurora as a Drupal base theme and learned to love how SASS driven it was. I also liked Omega for its strategy of bringing SASS to everyone. Unlike Omega this doesn't try to make PHP/Drupal responsible for compiling, leaving less code in the base theme and more flexibility.

### Disadvantages
The package-manager free approach has some downsides, the main one being that most of the libraries are designed to be used with one. It also makes it harder to update them.

## Versions
### Drupal 8
The Drupal 8 base is built off of Classy.

### Drupal 7
The Drupal 7 base is built off of [Basic](https://www.drupal.org/project/basic), with some elements of Aurora. It is not meant to be used as a subtheme, but as a clone. Basic's documentation contains instructions for this:
> - Basic is meant to be YOUR theme. To change the name of the theme from 'basic' to another name like 'mytheme',
follow these steps (to do BEFORE enabling the theme) :
>    - rename the theme folder to 'mytheme'
>    - rename basic.info to mytheme.info
>    - Edit basic.info and change the name, description, project (can be deleted), replace all other instances of "basic" ie. [basic_tabs] would become [mytheme_tabs]
>    - In template.php change each iteration of 'basic' to 'mytheme'
>    - In theme-settings.php change each iteration of 'basic' to 'mytheme'


## Using SASS
SASS is simply a more powerful way to write CSS. Utilize cool libraries to handle your layouts like grid systems or media queries and enjoy the ability to write and use variables and functions. A compiler then turns your SASS into CSS. The CSS is what the website uses to display, SASS is just for development.

### SASS Basics
#### Importing
The most important SASS concept in this theme is one of importing. With importing we can divide all our files (called partials) into different directories and have them made into one css files when compiled. In this theme the chain starts with style.scss, which then imports other .scss files and those files can import other files as well. For example in style.scss we have
```scss
@import 'partials/global/base';
```
This references the _base.scss file in the partials/global directory. Yes the syntax doesn't include the underscore nor the extension of the file.
In that _base.scss we can import our variables like this
```scss
@import 'variables';
```
which references a file in the same directory as _base.scss with the name _variables.scss.

### Including libraries
In order to remain compiler agnostic this theme does not make use of popular package managers like Bundler. The libraries are included manually and should be put in their own directory in the libraries partial folder. For example Breakpoint would go into the breakpoint directory with the base Breakpoint _breakpoint.scss and in your libraries partial (_libraries.scss) you'll include it in with the statement
```sass
@import 'breakpoint/breakpoint';
```
#### Recommended Libraries
These libraries have been tested extensively with this theme and are lightweight and simple to include:
* Media query handling: [Breakpoint](http://breakpoint-sass.com/) 
* Grid: [Susy](http://susy.oddbird.net/) or [Singularity](https://github.com/at-import/Singularity)
* Mixins: [Bourbon](https://github.com/thoughtbot/bourbon)

#### Tested libraries
##### Bootstrap-sass
This is the SASS version of [Bootstrap](http://getbootstrap.com/), a popular framework for developing responsive projects. To use import the [assets/stylesheets directory](https://github.com/twbs/bootstrap-sass/tree/master/assets/stylesheets). You'll also need to [include](https://www.drupal.org/node/304255) Bootstrap's Javascript in your theme for full functionality. 

##### Bourbon
[Bourbon](https://github.com/thoughtbot/bourbon) is a mixin library. You first need to build Bourbon in Ruby or Node to have the correct SASS files. Once you've built it you can include it normally.

##### Breakpoint
[Breakpoint](http://breakpoint-sass.com/) is a simple way of handling media queries. To use import the [stylesheets directory](https://github.com/at-import/breakpoint/tree/2.x.x/stylesheets).

##### Foundation
It's technically possible to use [Foundation](http://foundation.zurb.com/) framework in this way, but it has a number of dependencies that must be installed and then the Foundation files must be modified to utilize them. In addition, the version of SASS your compiler uses must be 3.4. An alternative is using a compiler with built-in support like [Codekit](https://incident57.com/codekit/index.html).

##### Susy
[Susy](http://susy.oddbird.net/) is a responsive grid framework. Follow the instructions in the [Susy documentation](http://susydocs.oddbird.net/en/latest/install/#manual-start). 
There is a layout example in the docs/samples folder.

##### Singularity
[Singularity](https://github.com/at-import/Singularity) is another responsive grid framework. To use import the [stylesheets](https://github.com/at-import/Singularity/tree/1.x.x/stylesheets) directory. There is a layout example in the docs/samples folder.

### Compilers
The purpose of the compiler is to turn your scss into css. The way they are ranked by difficulty is by:
* Easy: GUI-only
* Advanced: Requires some command line installations
In addition some compilers need different installation and configuration depending on the base OS and that is noted when relevant. 

While this theme aims to be free of requirements to use a particular compiler, some language-specific files are included in order to make it easier to configure some compilers:
* Config.rb utilized by Koala

This theme has been tested in the following compilers:
#### PHPStorm Watcher

##### For Mac 
_Difficulty: Advanced_

To utilize PHPStorm's SASS Watcher, you need to make sure to [first install the depedencies](https://www.jetbrains.com/phpstorm/help/transpiling-sass-less-and-scss-to-css.html) and then configure the from:to in the arguments correctly
```
Recommended Settings:
Scope: file:themes/glass_spider/sass/style.scss
Program: Should be a path to your local SASS 
Arguments: --no-cache --update $FileName$:$FileParentDir$/css/style.css
Working Directory: $FileDir$
Output Paths To Refresh: $FileParentDir$/css/style.css;
```


#### Koala
##### For Windows
_Difficulty: Easy_

To use in Koala simply drag the sass folder into the Koala application and click compile.

### Style
Sample styles are done with Markdown formatted commenting for use in Markdown-based [Styleguide](https://github.com/davidhund/styleguide-generators) generators.


### Other Plugins
To use popular plugins that are not-SASS based, utilize a compiler that supports them.

* [Compass](http://compass-style.org/)
  * [Codekit](https://incident57.com/codekit/index.html) - contains Bower, a popular package manager, so install libraries through this if possible
  * [Koala](http://koala-app.com/)
* [Autoprefixer](https://github.com/postcss/autoprefixer)
  * [Prepros](https://prepros.io/)
