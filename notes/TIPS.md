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
