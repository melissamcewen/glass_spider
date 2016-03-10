# Adding Bootstrap To Glass Spider - Step by Step

1. Download the [Bootstrap-Sass](https://github.com/twbs/bootstrap-sass) project, which is the SASS version of Bootstrap
2. In the project find the assets/stylesheets directory and move it into your Glass Spider theme under sass/libraries
3. Rename the stylesheets directory to 'bootstrap'
4. Edit your Glass Spider libraries.scss file to import it
```sass
@import 'bootstrap/bootstrap';
```
