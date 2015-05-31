---
layout: page
title: CSS
permalink: /css/
banner: banner_css.jpg
order: 1
---
  
CSS is arguably one of our most used languages at Old Town Media and the performance and technical debt of each site we build is largely dependent on how well it's written. Stylization and organization are very important aspects of this and are heavily discussed here. 

### Syntax

CSS Syntax is important for readability and for future maintainability. We have to be able to read and easily understand each others' code and adhering to these best practices will help both of those. 

* Write one selector per line
* Write one declaration per line
* Closing braces should be on a new line
* Adjacent and child selectors should have a line above them

**Avoid**

```css
.class-1, .class-2,
.class-3 {
width: 10px; height: 20px;
color: red; background-color: blue; }
.class-4{ width:100%; }
```

**Prefer:**

```css
.class-1,
.class-2,
.class-3 {
  width: 10px;
  height: 20px;
  color: red;
  background-color: blue;
}

.class-4{
	width: 100%;
}
```

* Include one space before the opening brace
* Include one space before the value
* Include one space after each comma-separated values

**Avoid**

```css
.class-1,.class-2{
  width:10px;
  box-shadow:0 1px 5px #000,1px 2px 5px #ccc;
}
```

**Prefer:**

```css
.class-1,
.class-2 {
  width: 10px;
  box-shadow: 0 1px 5px #000, 1px 2px 5px #ccc;
}
```

* Try to use lowercase for all values, except for font names
* Zero values don't need units
* End all declarations with a semi-colon, even the last one, to avoid error
* Use double quotes instead of single quotes

**Avoid**

```css
section {
  background-color: #FFFFFF;
  font-family: 'Times New Roman', serif;
  margin: 0px
}
```

**Prefer:**

```css
section {
  background-color: #fff;
  font-family: "Times New Roman", serif;
  margin: 0;
}
```

* If you only need to set one value, don't use the shorthand notation.
* However, If you need to set three or more values, do use the shorthand notation.

**Avoid**

```css
.header-background {
  background: blue;
  margin: 0 0 0 10px;
  font-family: "Arial Bold";
  font-size: 16px;
  line-height: 1;
  font-weight: 400;
}
```

**Prefer:**

```css
.header-background {
  background-color: blue;
  margin-left: 10px;
  font: 400 16px/1 "Arial Bold";
}
```

* Use indenting to signify child status

**Avoid**

```css
.header{
}

.contactinfo{
}

.phone{
}
```

**Prefer:**

```css
.header{
}

    .contactinfo{
	}

		.phone{
		}
```

#### Selector naming & specificity

Selectors should be named descriptively and classes should be used whenever possible. 

Styles should avoid being over specified. When you over-specify styles it becomes difficult to override them in the future and affects maintainability. [See here](https://css-tricks.com/specifics-on-css-specificity/) for more information on calculating specificity. 

Use classes, avoid IDs unless absolutely necessary, and don't over-qualify selectors by using elements adding-on to your classes.

**Avoid**

```css
html body div#pagewrap ul#summer-drinks li.favorite { }
```

**Prefer:** 

```css
.favorite { }
```

#### Commenting

Comments should be used liberally to describe each individual section of CSS with at least a title describing it. For more complex sections, a small explanation of the code is also encouraged.

```css
/**
 * Section title
 *
 * Description of section (if necessary)
 */
```

For single selectors or inline comments, use this syntax:

```scss
// Inline comment
```

#### Inline styles

Don't use inline styles. Not kidding.

### Sass

At Old Town Media we use the sass library to make writing css quicker and more efficient. We use local compilers to put concatenate files and run libraries such as autoprefixer upon compilation. This allows us to keep our stylesheets to one request while organizing the code in an easy-to-read and efficient way.
 
#### File Oranization
 
We follow a basic file structure at Old Town Media that makes our projects easier to work on.

```html
/styles
 -- main.scss
 -- ie8.scss
 -- print.css
 -- editor-styles.css
 -- login.css
 /sass
 	-- _normalize.scss
 	-- _responsive.scss
 	-- _forms.scss
```

---
RYAN - WHAT DO YOU WANT TO DO HERE
---

#### Breaking code into blocks

The main layout file should be organized in a top-down layout - starting with the header and ending with the footer. Other module-based stylesheets should be organized by module type or section. For example organizing a sheet by the custom post type or an eCommerce sheet starting with product listing, then individual product, then cart, etc.

#### Variables

Variables should all be defined in the main.scss file and should be named in a way that's recognizable to another developer/designer. All colors and font-families used more than once should be defined as variables to make organization easier.

**Avoid** 

```scss
	$luscious-nectar: #FFDAB9;
	$midnight: #191970;
```

**Prefer:** 

```scss
	$peach: #FFDAB9;
	$dark-blue: #191970;
```

#### Nesting

One of the best features of sass is that you can nest your selectors for easier readability. This is encouraged but should be used conservatively, lest we end up with a Woo nuclear-override selector. If you find yourself nesting more than 3 or 4 levels, re-evaluate the specificity required and your methodology.

There are times when more specificity is necessary, so use your best judgement.

#### Compiling

We cover general compilation more on the compiling page, but in general compiling should be done with a pre-processor on your workstation, triggering an autoprefixer and minifying the outputted css.

### Performance

While not as important as images, render-blocking elements, or javascript performance, CSS can still have a dramatic impact on a page load time and perceived performance.

---
MORE
---

#### Using images as background images instead of a new request

Whenever possible, images should be defined as background images - especially when they can be eliminated no the mobile side. If images are included in the css - they will only be loaded when the element is actually used instead of loaded at page load.

#### Network Requests

Stylesheets should all be compiled on the local side into one stylesheet. If you find yourself using a third-party library, it should be included using an @import statement in the appropriate section to be compiled.




### Mobile-first Responsive

We build our websites mobile first. Unless a design does not support it we use min-width media queries almost exclusively. Min-width queries allow us to be more flexible in building sites and results in using significantly less code with the same ending result. This also results in much faster mobile sites because the majority of the load is placed on larger screens, which generally have larger processors and faster Internet connections. 


#### Min-width media queries

Min-width media queries should be used almost exclusively and should all point in the same direction to avoid confusion. Min-width media queries follow the principle of progressive enhancement which puts the greater burden of styles and paints on desktops and larger devices. It also reduces the mount of code used and makes it easier to modify later.

#### Breakpoints

---
MORE
---

#### Media queries placement

Media queries should be placed in the _responsive.scss folder arranged from smallest min-width to the largest.


### IE8 and older browser support

We use an ie8-specific stylesheet trigger with an html IF comment targeting those browsers older than IE9. This method allows us much more flexibility and the potential to fix older IE quirks without muddying up our modern browser CSS.

```css
<!--[if lt IE 9]>
	<link rel="stylesheet" type="text/css" href="<?php echo get_template_directory_uri(); ?>/styles/ie8.css" />
<![endif]-->
```