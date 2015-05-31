---
layout: page
title: PHP
permalink: /php/
banner: banner_php.jpg
order: 2
---


### Stylization

Always use full PHP syntax, never shorthand. Shorthand PHP can get mixed with other languages such as Underscores which can cause issues. In addition, certain servers will not register shorthand tags correctly.

**Avoid:**

```php
<?php
<?  ?>
<?= ?>
```

**Prefer:**

```php
<?php
<?php  ?>
```

Always add spaced around variables, operators, commas, etc. This will increase readability and maintainability.Do not put spaces around internal array references.

**Avoid:**

```php
<?php
function new_function($variable,$variable2){}
x==23
foo&&bar
array(1,2,3)
$baz.'-5'
$term.='X'
$array_item[ 'test' ] = '';
?>
```

**Prefer:**

```php
<?php
function new_function( $variable, $variable2 ){}
x == 23
foo && bar
array( 1, 2, 3 );
$baz . '-5'
$term .= 'X';
$array_item['test'] = '';
?>
```

Output and loops should be indented appropriately. Indent one tab for each individual level of html or looping hierarchy.

**Avoid:**

```php
<?php
if( !empty( $posts ) ){
foreach( $posts as $post ){
echo $stuff
}
}

$html .= "<ul>";
$html .= "<li>";
$html .= "<a href='http://google.com'>Google</a>";
$html .= "</li>";
$html .= "</ul>";
?>
```

**Prefer:**

```php
<?php
if( !empty( $posts ) ){
	foreach( $posts as $post ){
		echo $stuff
	}
}

$html .= "<ul>";
	$html .= "<li>";
		$html .= "<a href='http://google.com'>Google</a>";
	$html .= "</li>";
$html .= "</ul>";
?>
```

Always use braces on if statements. This helps isolate issues related to non-wrapped statements running double lines of code. 

**Avoid:**

```php
<?php
if ( is_true() ) $run_my_code;
?>
```

**Prefer:**

```php
<?php
if ( is_true() ){
	$run_my_code;
}
?>
```

Array values and series of variables should be indented to the equals sign 

**Avoid:**

```php
<?php
$array = array(
	'quantity' => 5,
	'orderby' => 'menu_order',
	'order' => 'ASC',
);

$variable1 = '';
$variable_of_a_long_name = '';
$medium = '';
?>
```

**Prefer:**

```php
<?php
$array = array(
	'quantity'	=> 5,
	'orderby'	=> 'menu_order',
	'order'		=> 'ASC',
);

$variable1			= '';
$long_name_variable = '';
$medium				= '';
?>
```

Please use lowercase and underscores for variable names. 

**Avoid:**

```php
<?php
$CleanTime = '';
?>
```

**Prefer:**

```php
<?php
$clean_time = '';
?>
```


### Documentation 

PHP functions should be documented according to [WordPress standards](https://make.wordpress.org/core/handbook/inline-documentation-standards/php-documentation-standards/#1-functions-and-class-methods) minus since and link.

From the WordPress documentation section:

>Summary: A brief, one sentence explanation of the purpose of the function spanning a maximum of two lines. Use a period at the end.
>Description: A supplement to the summary, providing a more detailed description. Use a period at the end.
>@ignore Used when an element is meant only for internal use and should be skipped from parsing.
>@access: Only use for standalone functions if private. If the function or class method is private, it is intended for internal use only, and there will be no documentation for it in the code reference.
>@see: Reference to a function, method, or class that is heavily-relied on. See the note above about inline @see tags for expected formatting.
>@global: List PHP globals that are used within the function or method, with an optional description of the global. If multiple globals are listed, they should be aligned by type, variable, and description, with each other as a group.
>@param: Note if the parameter is Optional before the description, and include a period at the end. For example: Optional. This value does something. Default empty.
>@return: Should contain all possible return types, and a description for each. Use a period at the end. Note: @return void should not be used outside of the default bundled themes.

```php
<?php
/**
 * Summary.
 *
 * Description.
 *
 * @access (for functions: only use if private)
 *
 * @see Function/method/class relied on
 * @global type $varname Description.
 * @global type $varname Description.
 *
 * @param type $var Description.
 * @param type $var Optional. Description.
 * @return type Description.
 */
?>
 ```
 
### Internationalization

All PHP-served strings should be internationalized using one of WordPress' internationalization functions.
  
### OOP & Classes
```php
  -- classes 
  -- _hooks()
```
  
### Functions

Functions should only ever do one thing and one thing well. This makes them repeatable, testable, and easier to maintain over time.

### WordPress
```php
  -- WordPress
    -- Reference 10up standards
  	-- mu-plugins
 ```

### Security

Maybe dump<br>
[8 Best Practices](http://www.sitepoint.com/8-practices-to-secure-your-web-app/)
 
### Testing & Debugging
```php
  	-- debugging
  	-- unit testing
  	-- acceptance testing
 ```
  	
## More Reading
[http://www.phptherightway.com/](http://www.phptherightway.com/)<br>
[https://phpbestpractices.org/](https://phpbestpractices.org/)<br>
[30 Best Practices for Beginners](http://code.tutsplus.com/tutorials/30-php-best-practices-for-beginners--net-6194)