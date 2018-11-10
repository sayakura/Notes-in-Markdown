# Main 
everthing here is scss style
### variables: 
```
$font-stack:    Helvetica, sans-serif;
$primary-color: #333;

body {
  font: 100% $font-stack;
  color: $primary-color;
}
```

### Nesting
```
nav {
  ul {
    margin: 0;
    padding: 0;
    list-style: none;
  }

  li { display: inline-block; }

  a {
    display: block;
    padding: 6px 12px;
    text-decoration: none;
    }
}
```

### Partials
You can create partial Sass files that contain little snippets of CSS that you can include in other Sass files. This is a great way to modularize your CSS and help keep things easier to maintain. A partial is simply a Sass file named with a leading underscore. You might name it something like ```_partial.scss```. The underscore lets Sass know that the file is only a partial file and that it should not be generated into a CSS file. Sass partials are used with the @import directive.

### Import
```
// _reset.scss

html,
body,
ul,
ol {
  margin:  0;
  padding: 0;
}
```
### Mixins
```
@mixin transform($property) {
  -webkit-transform: $property;
  -ms-transform: $property;
  transform: $property;
}

.box { @include transform(rotate(30deg)); }
```

### Extend/Inheritance
```
/* This CSS will print because %message-shared is extended. */
%message-shared {
  border: 1px solid #ccc;
  padding: 10px;
  color: #333;
}

// This CSS won't print because %equal-heights is never extended.
%equal-heights {
  display: flex;
  flex-wrap: wrap;
}

.message {
  @extend %message-shared;
}

.success {
  @extend %message-shared;
  border-color: green;
}

.error {
  @extend %message-shared;
  border-color: red;
}

.warning {
  @extend %message-shared;
  border-color: yellow;
}
```

### Operators
```
.container {
  width: 100%;
}

article[role="main"] {
  float: left;
  width: 600px / 960px * 100%;
}

aside[role="complementary"] {
  float: right;
  width: 300px / 960px * 100%;
}
```


## Features

```
// base.scss

@import 'reset';

body {
  font: 100% Helvetica, sans-serif;
  background-color: #efefef;
}
```rgba($color, 0.5)``` *-you can use variable that has a hex value in rgba*
```

## npm related
### configuration
in the package.json file, add  ```"compile:sass": "node-sass sass_folder/sass_file.scss css_folder/style.css -w"``` to ```"scripts"```  attribute, the -w flag gonna keep watching the change in the file
then run ```npm run compile:sass```

### live server
```npm install live-server -g```
```live server``` // this will launch your website in live

## Installing node-sass
> ```npm install node-sass --save-dev```
## Vocaburaries
    Mixins (@maxins)
        $font-stack:    Helvetica, sans-serif;
        $primary-color: #333;

    Functions (@function )
    include (@include )
    varibale ($name: value)

## Features
```rgba($color, 0.5)``` *-you can use variable that has a hex value in rgba*


## npm related
### configuration
in the package.json file, add  ```"compile:sass": "node-sass sass_folder/sass_file.scss css_folder/style.css -w"``` to ```"scripts"```  attribute, the -w flag gonna keep watching the change in the file
then run ```npm run compile:sass```

### live server
```npm install live-server -g```
```live server``` // this will launch your website in live

## Installing node-sass
> ```npm install node-sass --save-dev```
