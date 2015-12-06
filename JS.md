---
layout: page
title: JS
permalink: /js/
banner: banner_home.jpg
order: 3
---

### Stylization

Always use spaces within functions and around variables, checks, etc.

**Avoid**

```js
var menu=$('.nav');
$(this).on('click,'function(){});
```

**Prefer**

```js
var menu = $( '.nav' );
$( this ).on( 'click', function(){
	
});
```

### Organization

Most JavaScript written for themes will lie in `/js/scripts.js`. This allows us to keep all of our front-end theme-related functionality in a single file and instantiate certain libraries if necessary. Libraries should be included in the `/js/vendor/` folder and individually instantaited (HTTP/2) or concatenated into an individual file (HTTP1/1).

#### Inline JS

Avoid using inline JavaScript in PHP or template files as maintenance becomes significantly more difficult. Instead, use a JavaScript file to keep your 


#### Compilation

JavaScript files should be linted and minified upon compilation to identify any issues before they hit the staging or production environment.


### Performance

 - Cache selectors and elements
 - Don't run too much login in for loops
 - Call files only when needed - i.e. in a shortcode instead of throughout the entire site