# TMG's Frontenders CSS and SCSS Styleguide {

## Table of Contents

1. [General Rules](#general-rules)
1. [Code Format](#code-format)
1. [SCSS](#scss)
1. [External Links](#external-links)

## General Rules

- Use tabs for indentation.

- For strings, use `"double quotes"`.

- Avoid the use of `!important` as much as _absolutely_ possible.

- Avoid trailing spaces          

- If the value of a property is `0`, do not specify units.

   ```css
   // good
   padding-top: 0;
   
   // bad
   padding-left: 0px;
   ```
   
- **Avoid** using IDs for CSS styling, unless there is a really good reason to.

- When using colors, always use a `$variable`. Either creating a new one if it's a new color, or reusing the existing ones. Use of the `darken()` and `lighten()` Sass functions is encouraged.

	```css
	// good
	$white: #fafafa;
	$header-background: $white;
	
	.tag-page-header {
		background-color: $header-background;
	}
	
	.tag-page-title {
		color: darken($white, 50%);
	}
	```
	
- When using `z-index`, use a `$variable` and put it on the global scss partial. Use a semantic variable name for it, so it can be reused.

**[⬆ back to top](#table-of-contents)**

## Code Format	

- Do not use `camelCasingNaming` for classes or IDs. Instead, go for `dashed-separated-naming`.
	
- When grouping selectors, use one line per selector.

- Add one space between the end of the selector and `{`

- Add one space after the `:` in properties.

- One line per declaration.

- End all declarations with `;`.

  ```css
  // good
  .main-header,
  .footer-text,
  .banner {
      color: $light-blue;
      line-height: 1.2em;
      text-shadow: 0 1px 1px rgba(0, 0, 0, .5);
  }
  
  // bad
  .main-header, .footer-text, .banner{
      text-shadow: 0 1px 1px rgba(0,0,0,.5); line-height: 1.2em;      
      color:$light-blue
  }
  ```

- Hex values for colors in lowercases. `#fafafa` instead of `#FAFAFA`.
- Hex values for colors in shorthand, if possible. `#bbb` instead of `#bbbbbb`.

**[⬆ back to top](#table-of-contents)**

## SCSS

- Do not use more than 3 nested selectors, if possible. If it seems that you need to, review your HTML structure:

	```css
	// bad
	#main {
		color: $main;
		.cc33 {
			border: 1px;
			.article {
				padding: 10px;
				.normal { /* one nested selecto too many! */
					background-color: $bg-main-color;
				}
			}
		}
	}
	```

- When nesting selectors, always put a line-break between the last declaration of the parent selector and the new/child nested selector:

	```css
	// bad
	#main {
		color: $main;
		font-size: 12px;
		.cc33 {
			border: 1px;
		}
	}
	
	// good
	#main {
		color: $main;
		font-size: 12px;
		
		.cc33 {
			border: 1px;
		}
	}
	```


**[⬆ back to top](#table-of-contents)**

## External Links
* [CSS Vocabulary](http://pumpula.net/p/apps/css-vocabulary/).

**[⬆ back to top](#table-of-contents)**


#}
