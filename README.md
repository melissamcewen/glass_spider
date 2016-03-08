# Glass Spider
A lightweight and flexible Drupal 8 base theme designed for GUI-based SASS compiling. 

## Mission
Glass Spider aims to be a solution that brings SASS-based theme development to a wide variety of skill levels. SASS setup is optimized for GUI compilers like Koala or Prepro. It's flexible – use Bootstrap or Breakpoint or anything you want (or don't) as long as it's SASS. 

I started this because I work with and teach developers and designers with a wide variety of skills and backgrounds who develop on different operating systems. When teaching SASS I often ended up spending hours teaching students how to set up a virtual machine in order to run command line compilers like Compass or Libsass. Students often ended up demoralized or frustrated because they were spending so much time honing their setup rather than actually working with SASS.

I had worked with Aurora as a Drupal base theme and learned to love how SASS driven it was. I also liked Omega for its strategy of bringing SASS to everyone. Unlike Omega this doesn't try to make PHP/Drupal responsible for compiling, leaving less code in this theme and more flexibility.

## Using SASS


### Including libraries
In order to remain compiler agnostic this theme does not make use of popular package managers like Bundler. The libraries are included manually and should be put in their own directory in the libraries partial folder. 
#### Tested libraries
##### Breakpoint

### Compilers
The purpose of the compiler is to turn your scss into css. This theme has been tested in the following compilers:
#### PHPStorm Watcher
#### Koala
