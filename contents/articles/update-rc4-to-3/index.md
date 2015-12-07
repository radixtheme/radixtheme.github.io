---
title: Update to Radix 7.x-3.1
author: Radix
date: 2015-12-07 10:00
template: article.jade
---
Radix 7.x-3.1 uses Gulp and no longer requires Compass gems. The update has to be done manually.

#### Step 1: Update Radix
1. Download [Radix 7.x-3.1](http://ftp.drupal.org/files/projects/radix-7.x-3.1.tar.gz).
2. Clear your site cache. `drush cc all`

#### Step 2: Remove unused files
Delete the following files from your subtheme: 
1. config.rb
2. Gemfile
3. Gemfile.lock
4. Guarfile

#### Step 3: Copy required files.
Copy the following files from the default kit to your subtheme.

1. `radix/kits/default/bower.json` to `/path/to/nameofyoursubtheme/bower.json`
2. `radix/kits/default/config.json` to `/path/to/nameofyoursubtheme/config.json`
3. `radix/kits/default/package.json` to `/path/to/nameofyoursubtheme/package.json`
4. `radix/kits/default/gulpfile.js` to `/path/to/nameofyoursubtheme/gulpfile.js`

#### Step 4: Update values.
Update the following values in bower.json, config.json and package.json: 

1. `{{Name}}` : name of your subtheme.
2. `{{Description}}` : description of your subtheme.
3. `{{machine_name}}` : the machine name of your subtheme.

#### Step 5: Fix SCSS files and directories
1. Move `/path/to/nameofyoursubtheme/assets/sass` to `/path/to/nameofyoursubtheme/scss`.
2. Delete `/path/to/nameofyoursubtheme/scss/screen.scss`
3. Copy `radix/kits/default/scss/default.style.scss` to `/path/to/nameofyoursubtheme/scss/nameofyoursubtheme.style.scss`
4. Copy `radix/kits/default/scss/radix` to `/path/to/nameofyoursubtheme/scss/radix`
5. Rename `/path/to/nameofyoursubtheme/scss/global` to `/path/to/nameofyoursubtheme/scss/base`
6. Rename `/path/to/nameofyoursubtheme/scss/partials` to `/path/to/nameofyoursubtheme/scss/components`
7. Rename `/path/to/nameofyoursubtheme/scss/base/_helper.scss` to `/path/to/nameofyoursubtheme/scss/base/_helpers.css`
8. Rename `/path/to/nameofyoursubtheme/scss/base/_mixin.scss` to `/path/to/nameofyoursubtheme/scss/base/_mixins.css`
9. Rename `/path/to/nameofyoursubtheme/scss/base/_variable.scss` to `/path/to/nameofyoursubtheme/scss/base/_variables.css`


#### Step 6: Fix JS files and directories
1. Move `/path/to/nameofyoursubtheme/assets/javascripts` to `/path/to/nameofyoursubtheme/js`
2. Rename `/path/to/nameofyoursubtheme/js/script.js` to `/path/to/nameofyoursubtheme/js/nameofyoursubtheme.script.js`

#### Step 7: Update info file
Edit nameofyoursubtheme.info and update the following lines:

1. `stylesheets[all][]     = assets/stylesheets/screen.css` to `stylesheets[all][]     = assets/css/nameofyoursubtheme.style.css`
2. `scripts[] = assets/javascripts/script.js` to `scripts[] = assets/js/nameofyoursubtheme.script.js`

#### Step 7: Install bower and npm modules.
Run `npm run setup`

#### Step 8: Run gulp
Run `gulp` to start watching for changes.
