**Extension** => LIve Sass Compiler (Glenn Marks)
*Settings* 
- Compile On Watch => On
- Show Output Window On => None
- Watch On Launch => On

What is CSS ?
CSS Pre Processor that adds powerfull features like variable, nested rules, mixins, and functions to make CSS More manageable. 
It's a Superset of CSS, means all the CSS is valid in SCSS.


---

Create an file `style.scss`
Add normal CSS boilerplate

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html,
body {
  height: 100%;
  width: 100%;
}
```

The extension Live Sass Compiller creates two files -> `style.css`, `style.css.map`
The style.css file contains all the compiled code of style.scss file.

Browser only understands HTML, CSS, JS -> we can do anything with them (Just them)
So browser don't know about SCSS, so we have to convert SCSS into CSS. 

# Concepts of SCSS

## Variables in SCSS

```scss
$bgc: red;

body {
  height: 100%;
  background-color: $bgc; // red color is set
}
```

## Nesting in SCSS
We can nest CSS styling. Means we can write selectors inside other selectors. 
It makes easy to mimic HTML like structure. 
It makes code modular.

```scss
@media (max-width: 700px) {
  #wrapper {
    flex-wrap: wrap;
    
    .box {
      width: 45vw;
      height: 500px;
    }
    
    .box:hover {
      flex-grow: 1;
      transform: scale(1.02);
    }
  }
}
```

## Mixins

A Mixin is like a reusable styles for CSS rules. 
Helps to avoid coe repetition.
Can take aruments, to make the style rules dynamic. 
Mixin is just like functions.

```scss
// here flexCenter is the name of mixin
@mixin flexCenter() {
  display: flex;
  justify-content: center;
  align-items: center;
}

// Jaha bhi mixin ka code use krna hai, waha
@include flexCenter();
```

### Dynamic Mixin 

here btn-style is the name of mixin
bg-color is a variable, that have default value blue.
to create a we must write $ before it's name.

```scss

@mixin btn-style($bg-color: blue) {
  padding: 20px 30px;
  background-color: $bg-color; // dynamic property value
  color: white;
  border: none;
  border-radius: 7px;
  outline: none;
  cursor: pointer;
  font-size: 18px;
}

.blue-btn {
  @include btn-style(blue);
}

.red-btn {
  @include btn-style(red);
}
```

## Partials & Imports

- Partials - Small SCSS file starts with ( `_` ), we use it to split code, and make it moduler. eg. `_header.scss`, `_footer.scss`
- Imports : Use `@import` to bring partial files code into one maim file.
- Again it make code modular and easy to maintain. 
Note - For the files starting with `_` , the SASS compiler do not generate any .css file, or .css.map file either.

How to use -
- Create a  `.scss` file, whose name starts with `_` eg. `_button.scss`
```scss
@mixin btn-style($bg-color: blue, $text-color: white, $text-size: 18px) {
  padding: 15px 30px;
  background-color: $bg-color; // dynamic property value
  color: $text-color; // dynamic property value
  border: none;
  border-radius: 7px;
  outline: none;
  cursor: pointer;
  font-size: $text-size; // dynamic property value
}
```

Now import this partial file in main style file.
Always remember @import will be on top of any style, and this statement must be terminated with semicolon ( `;` )
style.scss
```scss
@import "btn";

// We can also use the partial file styles using @use
// TBH @use is more modern then old @import
@use "btn";

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html,
body {
  height: 100%;
  width: 100%;
  // overflow: hidden;
}

// Using mixin in this file
.blue-btn {
  @include btn-style(purple, red, 13px);
}

.red-btn {
  @include btn-style(yellow, orange, 20px);
}
```

## SCSS Built-In Functions

```scss
lighten($color, $amount); // takes a color argument
darken($color, $amount)
mix($color, $color, $weight)
```

## Extend Styles 

We can create Classes like structure, extends style block inside other

```scss
%btn-base {
  padding: 20px;
  background-color: #d44545;
}

.blue-btn {
  @extend %btn-base;
}
```

## Operators

There must be a space around operators, to make it work better. 
We can perform Math inside CSS, without using calc function. 

```scss
.blue-btn {
  width: 100px - 50px; // 50px
  height: 100px + 40px; // 140px
}
```



- what is SCSS
- syntax od SCSS
- power of $variable in SCSS
- @mixin and @import
- _file.scss
- nesting of selectors in scss
- vs code setup for scss > install sass compiler (glenn marks)
-  settings > search : live sass compiler
- show output window > none
- watch on launch (check)




