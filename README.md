# Glass Spider
A lightweight and flexible Drupal 8 base theme designed for GUI-based SASS compiling. 

## Mission
Glass Spider aims to be a solution that brings SASS-based theme development to a wide variety of skill levels. SASS setup is optimized for GUI compilers like Koala or Prepro. It's flexible – use Bootstrap or Breakpoint or anything you want (or don't) as long as it's SASS. 

I started this because I work with and teach developers and designers with a wide variety of skills and backgrounds who develop on different operating systems. When teaching SASS I often ended up spending hours teaching students how to set up a virtual machine in order to run command line compilers like Compass or Libsass. Students often ended up demoralized or frustrated because they were spending so much time honing their setup rather than actually working with SASS.

I had worked with Aurora as a Drupal base theme and learned to love how SASS driven it was. I also liked Omega for its strategy of bringing SASS to everyone. Unlike Omega this doesn't try to make PHP/Drupal responsible for compiling, leaving less code in this theme and more flexibility.

## Using SASS
SASS is simply a more powerful way to write CSS. Utilize cool libraries to handle your layouts like grid systems or media queries and enjoy the ability to write and use variables and functions. A compiler then turns your SASS into CSS. The CSS is what the website uses to display, SASS is just for development.

### SASS Basics
#### Importing
The most important SASS concept in this theme is one of importing. With importing we can divide all our files into different directories and have them made into one css files when compiled. In this theme the chain starts with style.scss, which then imports other .scss files and those files can import other files as well. For example in style.scss we have
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
#### Tested libraries
##### Breakpoint
To use pull out the [stylesheets directory](https://github.com/at-import/breakpoint/tree/2.x.x/stylesheets), rename it breakpoint

### Compilers
The purpose of the compiler is to turn your scss into css. The way they are ranked by difficulty is by:
* Easy: GUI-only
* Advanced: Requires some command line installations
In addition some compilers need different installation and configuration depending on the base OS and that is noted when relevant. 

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

### Other Plugins
To use popular plugins that are not-SASS based, utilize a compiler that supports them.

* [Compass](http://compass-style.org/)
  * [Koala](http://koala-app.com/)
* [Autoprefixer](https://github.com/postcss/autoprefixer)
  * [Prepros](https://prepros.io/)
