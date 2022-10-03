# GLOSSARY

<br>

## Questions

<br>

- Kada pišemo CSS pravila, je li bolje pratiti abecedu ili kako se pojavljuju na stranici?

- Kada imam veliki blok CSS-a koji se odnosi na dio stranice ("Blog post thumbnails", "About" sekcija), da ga odvojim u zasebni stylesheet ili da bude u main.css? 

- Trebali stavljati klasu na element, ako se ta klasa nikada neće koristiti u CSS-u niti JS-u?

<br><hr /><br>

## CONTENT

<br>

1. [HTML](#1-html)

2. [CSS](#"2-css)

3. [JS](#3-js)

<br><hr /><br>

## 1. HTML

<br>

<br><hr /><br>

## 2. CSS

<br>

**F**

- [flex: Difference between ALIGN-ITENS and ALIGN-CONTENT](https://betterprogramming.pub/flexbox-align-items-and-align-content-a60b6f8451e3)

- [flex-grow ](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-grow)

- sets the flex grow factor of a flex item's main size (either width or height of the item which is dependent on the flex-direction value)

- specifies how much of the remaining space in the flex container should be assigned to the item (the flex grow factor)

<br><br>

- [format (in @font-face)](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face)
<br>

Available types: "woff", "woff2", "truetype", "opentype", "embedded-opentype","svg"

<br><br>

**N**

- [name (input)](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#name)

- string specifying a name for the input control

- submitted along with the control's value when the form data is submitted

- consider the name a required attribute (even though it's not). If an input has no name specified, or name is empty, the input's value is not submitted with the form! (Disabled controls, unchecked radio buttons, unchecked checkboxes, and reset buttons are also not sent)



<br><hr /><br>

## 3. JS

<br>

<br><hr /><br>

**U**

- USE STRICT

<br><hr /><br>

<br><br>

- [use strict](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Strict_mode)
  <br>

- opposite of _sloppy mode_
- different semantics from normal JS code semantics:
  <br>

      1. Eliminates some JS silent errors by changing them to throw errors.

      2. Fixes mistakes that make it difficult for JS engines to perform optimizations: strict mode code can sometimes be made to run faster than identical code that's not strict mode.

      3. Prohibits some syntax likely to be defined in future versions of ECMAScript.

<br>

- applies to entire scripts or to individual functions

- doesn't apply to block statements enclosed in `{}` braces
