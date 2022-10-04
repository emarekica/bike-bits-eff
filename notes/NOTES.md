# GLOSSARY

<br>

## Questions

<br>

- Kada pišemo CSS pravila, je li bolje pratiti abecedu ili kako se pojavljuju na stranici?

- Pojavljivanje u HTML-u.

- Kada imam veliki blok CSS-a koji se odnosi na dio stranice ("Blog post thumbnails", "About" sekcija), da ga odvojim u zasebni stylesheet ili da bude u main.css? 


- Yes.

- Trebali stavljati klasu na element, ako se ta klasa nikada neće koristiti u CSS-u niti JS-u?

- No.


<br><br>

- 

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

**B**

<br>

[::before](https://developer.mozilla.org/en-US/docs/Web/CSS/::before) / [::after](https://developer.mozilla.org/en-US/docs/Web/CSS/::after)
<br>

**::before, ::after**
<br>

- pseudo-element `::` (pseudo-classes have `:`)

- inline

- used to add cosmetic content to an element with the content property (replaces element with generated value) 
<br><br>


<br>

- **::before creates** pseudo-element that is first child of the selected element (before the element)

- **::after creates** pseudo-element that is last child of sel. element (after the element)


<br><br>

- objects inserted using `content` property are **replaced elements**

> replaced element is an element whose representation is outside the scope of CSS

> their content is not affected by the current CSS, position can be

<br>

- form controls, including other types of `input` elements, are explicitly listed as non-replaced elements (the spec describes their default platform-specific rendering with the term "Widgets") (except `img`)

- `content` property used to add **text, emoji, etc.** through CSS, not HTML

<br><br>

HTML: 
<br>

    <q>Some quotes</q>, he said, <q>are better than none.</q>

<br>

CSS:
<br>

    q::before {
      content: "«";
      color: blue;
    }

    q::after {
      content: "»";
      color: red;
    }
<br><br>

Output: "Some quotes", he said, "are better than none."


<br><br>

<br><hr /><br>

**F**

- [flex: Difference between ALIGN-ITENS and ALIGN-CONTENT](https://betterprogramming.pub/flexbox-align-items-and-align-content-a60b6f8451e3)

- [flex-grow ](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-grow)

- sets the flex grow factor of a flex item's main size (either width or height of the item which is dependent on the flex-direction value)

- specifies how much of the remaining space in the flex container should be assigned to the item (the flex grow factor)

<br><br>

`for`
<br>

    The value of the `for` attribute must be a single `id` for a labelable form-related element in the same document as the `label` element. So, any given label element can be associated with only one form control.

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

<br><br>

**P**
<br>

[:pseudo-class](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)
<br>

Keyword added to a selector that specifies a special state of the selected element(s).

`:enabled`, `:checked`, `:link`, `:visited` ...

<br><br>

[::pseudo-element](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)
<br>

Keyword added to a selector that lets you style a specific part of the selected element(s).

`::before`, `::after`, `::placeholder`, `::selection` ...

<br><br>

[:target](https://developer.mozilla.org/en-US/docs/Web/CSS/:target)
<br>

- pseudo-class

- represents a unique element (the _target element_) with an **id matching the URL's fragment** (denoted by the `#` sign) 
<br>

URL: _http://www.example.com/index.html#section2_
<br>

HTML: `<section id="section2">Example</section>`
<br>

Selecting the element with `:target` when the current URL:
<br>

CSS:
<br> 

    /* Selects an element with an ID matching the current URL's fragment */
    :target {
      border: 2px solid black;
    }

<br><br>

Another combo: 

HTML: 
<br>

    <a href="#p1">Link to paragraph 1</a>
    <p id="p1">TxT</p>

    <a href="#p2">Link to paragraph 2</a>
    <p id="p2">TxT</p>
<br>

CSS: `p:target {}`
<br><br>


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
