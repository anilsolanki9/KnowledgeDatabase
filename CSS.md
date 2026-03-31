HTML  →  Structure    "Yahan heading hai, yahan button"
CSS   →  Presentation "Heading red hogi, button rounded hoga"
JS    →  Behavior     "Button click pe kya hoga"

## CSS Syntax

```css
selector {
  property: value;
  property: value;
}
```

eg. 
```css
h1 {
  color: red;
  font-size: 32px;
  text-align: center;
}
```

```bash
h1              → SELECTOR "Kisko style karna hai" = (saare h1 tags ko)

{  }            → DECLARATION BLOCK "Kya style karna hai — andar likho"

color           → PROPERTY "Konsi cheez change karni hai"

red             → VALUE "Kya change karna hai"

color: red;     → DECLARATION , Property + Value = Declaration

;               → SEMICOLON , Har declaration ke baad ZAROORI hai
                  if Bhool gaye → CSS toot jaati hai
```

## Comments in CSS
```css
/* Ye ek comment hai — browser ignore karta hai */

h1 {
  color: red; /* Heading ka color */
}

/*
  Multiple lines
  ka comment bhi
  likh sakte ho
*/
```

# Ways to add CSS 

## 1 Inline CSS
```css
<h1 style="color: red; font-size: 32px;"> Namaste Duniya </h1>
```
Use when :
- Quick testing
- Override style for a specific element

## 2 Internal CSS
```html
<!DOCTYPE html>
<html>
  <head>
    <title>Meri Website</title>

    <!-- CSS yahan likhte hain -->
    <style>
      h1 {
        color: red;
        font-size: 32px;
      }

      p {
        color: blue;
        font-size: 16px;
      }
    </style>

  </head>
  <body>
    <h1>Namaste Duniya</h1>
    <p>Main paragraph hoon</p>
    <button>Click Karo</button>
  </body>
</html>
```

Use when :
- Single Page Project
- Quick Prototype

## 3 External CSS
- Create an `style.css` file and link it with HTML using `<link / >` tag.
style.css
```css
h1 {
  color: red;
  font-size: 32px;
}
```

index.html
```html
<!DOCTYPE html>
<html>
  <head>
    <title>Meri Website</title>
    <!-- CSS file ko link karo -->
    <link rel="stylesheet" href="./style.css">
  </head>
  <body>
    <h1>Namaste Duniya</h1>
    <p>Main paragraph hoon</p>
    <button>Click Karo</button>
  </body>
</html>
```

Best for :
- Multipage project
- Reusable style
### Teeno Ka Comparison 
```table
	            INLINE    INTERNAL    EXTERNAL
                ──────    ────────    ────────
Kahan likhein   Element   <style>     .css file
                pe tag    tag mein    mein

Reusability     ❌ None   ⚠️ 1 page   ✅ All pages

Maintenance     😱 Hard   😐 Medium   😊 Easy

Real projects   ❌ Avoid  ⚠️ Rarely   ✅ Always

Priority        1st       2nd         3rd
```

