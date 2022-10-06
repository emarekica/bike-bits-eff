# GLOSSARY

<br>

## Questions

<br>

<br><hr /><br>

## CONTENT

<br>

1. [HTML](#1-html)

2. [CSS](#"2-css)

3. [JS](#3-js)

<br><hr /><br>

[MIME type](https://developer.mozilla.org/en-US/docs/Glossary/MIME_type)
<br>

- media/content type

- string sent along with a file indicating the type of the file describing the content format

- serves the same purpose as filename extensions traditionally do on Windows

<br><br>

## 1. HTML

<br>

**A**
<br>

[anchor](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a)

<br>

- creates a hyperlink to anything URL can address

- content within each `a` should indicate the link's destination

- ig `href` attribute present, pressing the `enter` key while focused on the `a` element will activate it
  <br>

``

<p>You can reach Michael at:</p>

    <ul>
      <li><a href="https://example.com">Website</a></li>
      <li><a href="mailto:m.bluth@example.com">Email</a></li>
      <li><a href="tel:+123456789">Phone</a></li>
    </ul>

``
<br>

<p>You can reach Michael at:</p>

<ul>
  <li><a href="https://example.com">Website</a></li>
  <li><a href="mailto:m.bluth@example.com">Email</a></li>
  <li><a href="tel:+123456789">Phone</a></li>
</ul>

<br><br>

Two ways of connecting `a` to another element (`name` deprecated):
<br>

    <h2 id="gallery title">Gallery title</hr2>
    <a href="#gallery-title"></a>

    <h2 id="mirko">Mirko</h2>
    <a name="#mirko"></a>

<br><hr /><br>

**C**

<br>

[charset](https://developer.mozilla.org/en-US/docs/Glossary/character_encoding)
<br>

- character encoding

- defines a mapping between bytes and text (a sequence of bytes allows for different textual interpretations)

- by specifying a particular encoding (such as UTF-8), we specify how the sequence of bytes is to be interpreted

- ensures you can use characters from all human languages
  <br>

      <meta charset="utf-8" />

<br><br>

**I**
<br>

[Input type="checkbox"](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/checkbox)
<br>

- elements of this type rendered by default as boxes that are checked (ticked) when activated

- select single or multiple values for submission in a form (or not)

- `value` (string) given to the data submitted with the checkbox's `name`

- `a`, `button`, `input` and `textarea` all have the `:focus` state by default

<br><br>

**L**
<br>

[label](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/label)
<br>

- caption for connected element

- connect with the element's `id` with attribute `for` with same value
  <br>

`input`: `id`
`label`: `for`

<br>

    <input type="checkbox" name="cheese" id="cheese">
    <label for="cheese">Do you like cheese?</label>

<br><br>

Or nest the `input` directly inside the `label`, in which case the for and id attributes are not needed because the association is implicit.
<br>

    <label>
      Do you like peas?
      <input type="checkbox" name="peas" />
    </label>

<br><br>

### `label` + `input`

<br>

- label txt **visually & programmatically** associated with corresponding txt input

- click/touch/tap on `label` passes the focus to associated `input` > increased hit area for focusing the input

<br><hr /><br>

## 2. CSS

<br>

**A**
<br>

[animatable CSS properties](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties)

<br>

Not all properties are animatable.
<br>

When doing animation with transition, write the animation property under primary selector.

Write what & how it should be animated when state is changed.
<br>

    .btn:link {
      transition: all 0.2s;
    }

    .btn:hover {
      transform: translateY(-3px);

      /* offset-x | offset-y | blur-radius | color */
      box-shadow: 0 1rem 2rem rgba(0, 0, 0, 0.2);
    }

<br> <br>

<br><hr /><br>

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

[box-sizing: border-box and content-box](https://developer.mozilla.org/en-US/docs/Web/CSS/box-sizing)
<br>

Useful to put it on layout elements.

`box-sizing: border-box` makes dealing with the sizes of elements much easier. It tells the browser to account for any border and padding in the values you specify for an element's width and height. **If you set an element's width to 100 pixels, that 100 pixels will include any border or padding you added, and the content box will shrink to absorb that extra width**.
<br>

On the other hand, when using `position: relative` or `position: absolute`, use of `box-sizing: content-box` because it allows the **positioning values to be relative to the content, and independent of changes to border and padding sizes**, which is sometimes desirable.

<br><hr /><br>

**F**

[flex: Difference between ALIGN-ITEMS and ALIGN-CONTENT](https://betterprogramming.pub/flexbox-align-items-and-align-content-a60b6f8451e3)
<br><br>

`align-content` manages the space between the lines when items wrap.
<br>

`align-items` aligns the items relative to each other when sizes of items are different. When the size of the items are the same and there is only one line, they behave similarly.

<br><br>

[flex-grow ](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-grow)

- sets the flex grow factor of a flex item's main size (either width or height of the item which is dependent on the flex-direction value)

- specifies how much of the remaining space in the flex container should be assigned to the item (the flex grow factor)

<br><br>

`for`
<br>

The value of the `for` attribute must be a single `id` for a labelable form-related element in the same document as the `label` element. So, any given label element can be associated with only one form control.

<br><br>

[format (in @font-face)](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face)
<br>

Available types: "woff", "woff2", "truetype", "opentype", "embedded-opentype","svg"

<br><br>

**M**
<br>

[meta](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta#attr-http-equiv)
<br>

    <meta http-equiv="X-UA-Compatible" content="IE=edge" />

<br><br>

`http-equiv` defines a pragma directive. The attribute is named http-equiv(alent) because all the allowed values are names of particular HTTP headers:

`x-ua-compatible` If specified, the content attribute must have the value `IE=edge`. User agents are required to ignore this pragma.

`X-UA-Compatible` is a document mode meta tag that allows web authors to choose what version of Internet Explorer the page should be rendered as. It is used by Internet Explorer 8 to specify whether a page should be rendered as IE 7 (compatibility view) or IE 8 (standards view).

<br><br>

**N**

[name (input)](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#name)

- string specifying a name for the input control

- submitted along with the control's value when the form data is submitted

- consider the name a required attribute (even though it's not). If an input has no name specified, or name is empty, the input's value is not submitted with the form! (Disabled controls, unchecked radio buttons, unchecked checkboxes, and reset buttons are also not sent)

<br><br>

**P**
<br>

**PRE- vs POST-PROCESSPRS**

- _pre-processors_ parse and compile CSS extention language into plain CSS
- has own stzlesheet language

- use them for color schemes, font-face mixins, layout mixins etc.

- don't use them for cross-browser fixes like vendor prefixes and polyfills
  <br><br>

- _post-processors_ parse and process CSS and add vendor prefixes

- applies automation/repetition

- for cross-browser fixes, images, fonts, linters ... [see list](https://github.com/postcss/postcss#tools)

<br>

<br>

<br><br>

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

**V**
<br>

[viewport](https://developer.mozilla.org/en-US/docs/Web/HTML/Viewport_meta_tag)

    <meta name="viewport" content="width=device-width, initial-scale=1.0">

<br>

Area of the window in which web content can be seen.

This is often not the same size as the rendered page, in which case the browser provides scrollbars for the user to scroll around and access all the content.
<br><br>

`width`
<br>

**Controls the size of the viewport**. It can be set to a specific number of **pixels** like width=600 or to the special value **device-width**, which is 100vw, or 100% of the viewport width.
<br>

`initial-scale`
<br>
Controls the zoom level when the page is first loaded. Minimum: 0.1. Maximum: 10. Default:1

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
