# Adding Singularity To Glass Spider - Step by Step
1. Download and extract [Singularity](https://github.com/at-import/Singularity)
2. Move the Singularity directory ['stylesheets'](https://github.com/at-import/Singularity/tree/1.x.x/stylesheets) to your libraries partial folder in your Glass Spider theme
3. Rename the 'stylesheets' directory to 'singularity'
4. Edit your Glass Spider theme's 'libraries.scss' to import the 'singularity/_singularity.scss' file
```sass
@import 'singularity/singularitygs';
```

## Utilizing the sample layout
1. copy the Glass Spider sample layout partial sample 'singularity_sample_layout_drupal_7.scss' or 'singularity_sample_layout_drupal_8.scss' (depending on your Drupal version) into your Glass Spider theme's 'sass/partials/layouts' directory
2. include the sample in your layouts partial with the following import
```sass
@import 'singularity_sample_layout_drupal_7';
```
