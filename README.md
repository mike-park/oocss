## My changes from https://github.com/stubbornella/oocss.git:

Created a sass branch to allow complete oocss .css code to be imported into a rails 3.1 app using sass.
By renaming .css files to .css.scss and changing the @import statements, sass will process the @imports
server side and produce a single .css file as a result. With the previous file naming, all the @import
statements are processed client side, resulting in many http requests.

## To use in Rails 3.1

```
git clone git://github.com/mikepinde/oocss.git
cd oocss
git checkout sass
mkdir YOUR_RAILS_APP_NAME/app/assets/stylesheets/oocss
cp -pr . YOUR_RAILS_APP_NAME/app/assets/stylesheets/oocss
rm -rf YOUR_RAILS_APP_NAME/app/assets/stylesheets/oocss/.git
```

Add to YOUR_RAILS_APP_NAME/app/assets/stylesheets/application.css:

```
 *= require oocss/all
```

Original README.md below



## To Do

* Split module skins   

## Filestructure Conventions

_Example:_  

    \-yourplugin/ {plugin-root}  
    +-yourplugin.css {essential CSS}  
    +-yourplugin_debug.css {CSS for debugging} 
    +-yourplugin_doc.html {Examples and Explanation}  
    +-yourplugin_skins.css {all skins that only require pure css, others via @import}  
    +-\ skins/ {skins that need more than pure CSS, eg. images}  
      +-\ photo/ {skin-root}  
        +-photo_skin.css  
        +-img/  
      +-\ flow/ {skin-root}  
        +-flow_skin.css  
        +-img/  
