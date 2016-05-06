---
title: Fun With Clip-paths
date: 2016-05-06 15:39:36
tags:
---

The `clip-path` CSS property allows you to display a portion of an element rather than displaying the whole thing. In Photoshop, this could be called masking. This is mostly used to show or hide a portion of an image, but it can also be used on `<p>`s and `<div>`s as well. This could be used to shape divs, say if you have a crazy design to match and can’t just use a square-shaped element or you don’t want everything on your site to just be an image or SVG. 

Note that there used to be a `clip` property, but that is mostly deprecated and `clip-path` is what should now be used

There are several different ways to use `clip-path`. The one I am most familiar with is `clip-path: polygon();` This allows you to use different grid points to specify which part of the image or element you want to display.

You can think of the points you are using as the X and Y axis, so when you start and use 
`clip-path: polygon(0 0)`, your first point will be at `left:0;` and `top:0;`. You can pass percentages or pixel values into this. Also, you separate your points by using commas.
So, if I were to do
`clip-path: polygon(0 0, 0 100px, 100px 100px, 100px 0);`, that would display a box 100px wide and 100px tall.

Here is how to make a simple square:
<p data-height="266" data-theme-id="0" data-slug-hash="yOZBBJ" data-default-tab="css,result" data-user="chreeswright" data-embed-version="2" class="codepen">See the Pen <a href="http://codepen.io/chreeswright/pen/yOZBBJ/">Clip-path Square</a> by Chris Wright (<a href="http://codepen.io/chreeswright">@chreeswright</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

Here is how to make a simple triangle:
<p data-height="266" data-theme-id="0" data-slug-hash="BKMBag" data-default-tab="css,result" data-user="chreeswright" data-embed-version="2" class="codepen">See the Pen <a href="http://codepen.io/chreeswright/pen/BKMBag/">Clip-path Triangle</a> by Chris Wright (<a href="http://codepen.io/chreeswright">@chreeswright</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

Here is an Octagon: 
<p data-height="266" data-theme-id="0" data-slug-hash="NNoKxP" data-default-tab="css,result" data-user="chreeswright" data-embed-version="2" class="codepen">See the Pen <a href="http://codepen.io/chreeswright/pen/NNoKxP/">Clip-path Octagon</a> by Chris Wright (<a href="http://codepen.io/chreeswright">@chreeswright</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

And lastly, here is an example of a more complex use of `clip-path`:
<p data-height="412" data-theme-id="0" data-slug-hash="GZMyGV" data-default-tab="css,result" data-user="chreeswright" data-embed-version="2" class="codepen">See the Pen <a href="http://codepen.io/chreeswright/pen/GZMyGV/">HTML 5 Logo in Pure CSS</a> by Chris Wright (<a href="http://codepen.io/chreeswright">@chreeswright</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

Building a polygon is not the only use of `clip-path`. You can also use the following:
```
/* referencing path from an inline SVG <clipPath> */
  clip-path: url(#c1); 

  /* referencing path from external SVG */
  clip-path: url(path.svg#c1);

  /* polygon */
  clip-path: polygon(5% 5%, 100% 0%, 100% 75%, 75% 75%, 75% 100%, 50% 75%, 0% 75%);

  /* circle */
  clip-path: circle(30px at 35px 35px);

  /* ellipse */
  clip-path: ellipse(65px 30px at 125px 40px);

  /* inset-rectangle() may replace inset() ? */
  /* rectangle() coming in SVG 2 */

  /* rounded corners... not sure if a thing anymore */
  clip-path: inset(10% 10% 10% 10% round 20%, 20%);
```
### Browser Support
Any version of Chrome, Safari and Firefox is supported, Opera is 7+, IE is 8+, Android ? and IOS is 2+

