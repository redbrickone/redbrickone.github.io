---
title: Attribute Selectors in CSS
date: 2016-05-17 10:53:42
tags:
---


In HTML, sometimes you need to be very specific with your selectors. You can actually select elements based on their attributes rather than their class or ID.

## CSS [attribute] Selector
This is used to target any element that has a certain html attribute (in the example, we are targeting the "download" attribute).
The selector `a[download]` selects  an anchor tag with a download attribute.

``` 
a[download] {
  background-color: blue;
}
```
will select `<a href="#" download>Click me!</a>`

## The [attribute="value"] Selector
This selects an html element with a specific attribute **and** a specific value. For example: 
`a[target="_blank"]` 
selects any element with a `target` attribute whose value is `"_blank"`.
```
a[target="_blank"] { 
    color: blue;
    font-weight: bold;
}
```
will select `<a href="#" target="_blank"></a>`

## The [attribute~="value"] Selector
This selector is similar to the previous selector but it selects a specific attribute and value but the value must be a space-separated word. For example:
`[title~="namespace"]`
selects any element with a title that contains the word "namespace". It can contain other words, but the word namespace must be separated from any other words by a space rather than a hyphen.
```
[title~="namespace"] {
  color: white;
    font-weight: 200;
}
```
This selects `<a href="#" title="namespace">Click me!</a>` but not `<a href="#" title="namespace-top">Click me!</a>`

## The [attribute|="value"] Selector
This selector selects an element with a specific attribute but the value begins with a specific word. For example:
`[class|="top"]`
will select an element whose class begins with the word top. The value has to be a whole word, either alone or separated by a hyphen. So, this will select an element with a class of `"top"`, `"top-bar"` and `"top-stuff"` but will not select an element with a class of `"topbar"` because it is not separated by a hyphen.
```
a[class|="top"] {
    background: #CCCCCC;
}
```
will select `<a href="" class="top top-bar">Click me!</a>` but will not select `<a href="#" class="topbar">Click me!</a>`

## The [attribute^="value"] Selector

This is just like the last selector, however the value does not have to be a whole word. For example:
`[class^="top"]`
will select will select any element whose class begins with the word "top", but it does **not** have to be separated by a hyphen, so "topbar" would be selected by this selector.
```
h2[class^="top"] {
    background: red;
}
```
will select `<a href="#" class="topbar">Click me!</a>`

## The [attribute$="value"] Selector
This selector is the exact opposite as the last two because it selects an element with a specific attribute that **ends** with a specific value, rather than beginning with that value. For Example:
`[class$="test"]`
will select any element with a class that ends in the word "test". This value does **not** have to contain a full word, so you won't need to worry about hyphens.
```
a[class$="te"] {
    background: green;
}
```
Will select `<a href="#" class="greatest">Click me!</a>`

## The [attribute*="value"] Selector
This selector is like the last three, but will select any html element that has a specific attribute and contains a string of text**anywhere** in the value, so it does not need to begin or end with it as long as it contains the value. For example:
`[class*="te"]`
will select any html element that has a class that contains the string `"te"` inside it, so in your example below, the class is `"state"` so our CSS selector will style that div.
```
a[class*="te"] {
    background: blue;
}
```
Will select `<a href="#" class="state">Click me!</a>`

## Styling Forms
This is what CSS Attribute selectors are most used for. Rather than putting a class or ID on form inputs, you can just select the elements based on their type.
`input[type="text"]` will select a form input and 
`input[type="button"]` will select a form button
