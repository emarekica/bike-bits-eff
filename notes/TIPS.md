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
