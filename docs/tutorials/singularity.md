# Adding Singularity To Glass Spider - Step by Step
1. Download and extract [Singularity](https://github.com/at-import/Singularity)
2. Move the Singularity directory ['stylesheets'](https://github.com/at-import/Singularity/tree/1.x.x/stylesheets) to your libraries partial folder in your Glass Spider theme
3. Rename the 'stylesheets' directory to 'singularity'
4. Edit your Glass Spider theme's 'libraries.scss' to import the 'singularity/_singularity.scss' file
```sass
@import 'singularity/singularitygs';
```
