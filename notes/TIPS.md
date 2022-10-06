# TIPS n TRICKS

<br>

## CONTENT

<br>

1. [HTML](#1-html)

2. [CSS](#"2-css)

3. [JS](#3-js)

<br><hr /><br>

## 1. HTML

<br>

### CONNECTING ANCHOR TO OTHER ELEMENTS

<br>

Two ways of connecting `a` to another element (`name` is deprecated):
<br>

    <h2 id="gallery title">Gallery title</hr2>
    <a href="#gallery-title"></a>

    <h2 id="mirko">Mirko</h2>
    <a name="#mirko"></a>

<br><hr /><br>

### HEADING WITH 2 LINES

<br>

HTML:
<br>

    <div class="text-box">
        <h1 class="heading-primary">
        <span class="heading-primary-main">Outdoors</span>
        <span class="heading-primary-sub">is where life happens</span>
        </h1>
    </div>

<br><br>

CSS:

    .heading-primary {
        display: block;
    }

    .text-box {
        position: absolute;
        top: 45%;
        left: 50%;
        transform: translate(-50%, -50%);
    }

<br><br>

`top: 50%`, `left: 50%` means it is 50% width of the parent element

`transform: translate(50%, 50%)` are in the relation of the element itself, not the parent element

<br><hr /><br>

## 2. CSS

<br>

### ADD "x" WITH CSS

<br>

- `::after` class + `content` property

- element is not visible, when clicking on link, opens a little modal with "x" that can close it

<br><br>

HTML:
<br>

    <li><a href="#example1">Open example #1</a></li>

    <div class="lightbox" id="example1">
    <figure>
        <a href="#" class="close"></a>
        <figcaption>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec felis enim,
        placerat id eleifend eu, semper vel sem.
        </figcaption>
    </figure>
    </div>

<br><br>

CSS:
<br>

    /* Unopened lightbox */
    .lightbox {
    display: none;
    }

    /* Opened lightbox */
    .lightbox:target {
    position: absolute;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    }

    /* Lightbox content */
    .lightbox figcaption {
    width: 25rem;
    position: relative;
    padding: 1.5em;
    background-color: lightpink;
    }

    /* Close button */
    .lightbox .close {
    position: relative;
    display: block;
    }

    .lightbox .close::after {
    right: -1rem;
    top: -1rem;
    width: 2rem;
    height: 2rem;
    position: absolute;
    display: flex;
    z-index: 1;
    align-items: center;
    justify-content: center;
    background-color: black;
    border-radius: 50%;
    color: white;
    content: "×";
    cursor: pointer;
    }

    /* Lightbox overlay */
    .lightbox .close::before {
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    position: fixed;
    background-color: rgba(0, 0, 0, 0.7);
    content: "";
    cursor: default;
    }

<br><br>

### `:focus`, `:hover`, `:` WHEN TO USE WHICH

<br>

`:hover`
<br>

Also called the “pointer hover pseudo-class”, applies when a pointing device interacts with an element without necessarily activating it.

A typical example of this is when a **mouse** hovers over an element.

For **keyboard**, the `:hover` pseudo-class is never triggered. The keyboard is not considered a “pointer” device and so can’t apply to this pointer hover pseudo-class.
<br><br>

`:focus`
<br>

Applies when an element is in a state that is ready to be interacted with, i.e. it has the focus of the input device. When this applies differs quite greatly between the different input devices.

When using a **mouse** or similar pointing device, the `:focus` pseudo-class will apply once the user has begun activating the element and, importantly, it will continue to stay in focus until the user activates another element by clicking.

Focusing on an element with **keyboard** is very similar to hovering over it for mouse users. I like to think of the :focus pseudo-class as a hover state for keyboard devices, because it signals a similar intention for interaction.

<br><br>

`:active`
<br>

Applies _during the period in which the element is being activated_. For example, if using a **mouse**, it would be the time between when the mouse button is clicked and when it is released.

<br><br>

Most of the times when an element is being clicked with a mouse, all three conditions are valid - the mouse if over the element, the element is in focus, and the element is being activated.
<br>

        button:hover:focus:active {
        background-color: #ffdb3a;
        }

<br>

Since all three events are applied during a typical click event, the cascade takes over and the last-defined style wins.
<br>

The best way to order your pseudo-class styles are `:hover` then `:focus` then `:active`.
<br>

        button:hover {
        background-color: green;
        }

        button:focus {
        background-color: blue;
        }

        button:active {
        background-color: red;
        }

<br>

This will not apply on mobile (iOS) Safari.

<br><br>

[Article](https://bitsofco.de/when-do-the-hover-focus-and-active-pseudo-classes-apply/)

<br><hr /><br>

### JUMPING ELEMENTS WHEN HIDE/SHOW TOGGLE

<br>

Instead of `display:none` & `display: inline/inline-block/block`, use `opacity:0` & `opacity: 1`.

<br><hr /><br>

### TRANSITION & ANIMATABLE PROPERTIES

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

<br><br>

**Example with switcher button**
<br>

    parent: `position:relative`

    child: `position: absolute`

<br>

`left: 0;` = `0%` or start of the element

`right: 0;` = `100%` or end of the element

Moving the child on click horizontally ) with `calc()` or `transform: translateX()` or `transform: translateX( calc() )`, where the child element starts from the `0%` of its parent and ends at `100%` of its parent.

Calculate it with the `calc()` by substracting the child's width from 100% of the parent.

_(other element's properties are left out)_

<br><br>

```
.switcher {
  position: relative;
}

.enabled--round {
  position: absolute;
  left: 0;

  transition: all 0.5s ease;
}

<!-- animation -->
<!-- span > span refers to .enabled--round because it is span inside of a span -->

input:checked + span > span {
  padding: 0.2rem 0.4rem;
}
```

<br><hr /><br>

### TOGGLE SIZE OF AN ELEMENT WITH :focus

<br>

When you click on the test, it grows and has red background.
When you click anywhere else, it closes back. **Browser handles returning to the state before :focus**.

<br><br>

HTML:
<br>

    <a href="#">Test</a>
    <a href="#">Test</a>
    <a href="#">Test</a>
    <a href="#">Test</a>

<br>

CSS:
<br>

a {
display: block;
width: 1em;
}

a:focus {
background: red;
color: white;
width: 3em;
}

<br><br>

<br><br>

### SHOW / HIDE ELEMENT

<br>

This combination allows to click on things and animate

`opacity: 1;` < > `opacity: 2;`

<br>

    opacity: 0;
    pointer-events: none;

<br><br>

<br><hr /><br>

## 3. JS

<br>
