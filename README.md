# HTML-CSS-Basics
Workshop for HTML &amp; CSS BASICS (6/4/15)

**Led by James Traver**
- jamest@ga.co
- https://github.com/code-for-coffee
- @code4coffee

## Whiteboard

*Introduction/Objectives*
<img src="https://github.com/ga-chicago/HTML-CSS-Basics/blob/master/img_intro.JPG">
*HTML, CSS, and Javascript's Role*
<img src="https://github.com/ga-chicago/HTML-CSS-Basics/blob/master/img_html_css_js.JPG">
*HTML Tag breakdown*
<img src="https://github.com/ga-chicago/HTML-CSS-Basics/blob/master/img_html_tag_breakdown.JPG">
*HTML5 Tag Structure & Descriptions*
<img src="https://github.com/ga-chicago/HTML-CSS-Basics/blob/master/img_html_tags.JPG">
*Recap*
<img src="https://github.com/ga-chicago/HTML-CSS-Basics/blob/master/img_whiteboard.JPG">
*CSS Selector*
<img src="https://github.com/ga-chicago/HTML-CSS-Basics/blob/master/img_css_selector.JPG">

**Next Steps**
- https://dash.generalassemb.ly/
- http://learn.shayhowe.com/
- Check out GA's FEWD and WDI!

## Second Pass on HTML/CSS
 
To style these divs and give them a meaning, there are a variety of HTML styles that can be applied.
These are traditionally stored in an external stylesheet inside of the <head></head> HTML tags, ie:
  
  <link rel="style" href="myStylesheet.css">
  
These stylesheets are composed of selectors. Each selector looks like:
 
```css
myDiv {
  /* some code in here */
}
```
  
We'll style the div tags with selectors. Selectors come in three primary varieties: page elements (such as body, a, img), 
classes  (such as `<input class="myInput" type="number" />`, and IDs (`<div id="menu-section"></div>`). 
 
Page elements represent HTML tags. For example, you can have a selector that covers the entire page with:
 
```css
body {
  font-size: 16px;
  color: black;
}
```
 
You can also style your images (`<img src="myimage.png">`) with:
 
```css
img {
  border-right: 1px solid black;
  /* there is also border-left, border top, border-bottom */
}
```
 
Or you can style your anchor (`<a href="mypage.html">my page</a>`) tags:

```css
a {
  color: blue;
}
a:hover {
  color: purple;
}
```
  
Wait - before we go any further, notice the a:hover selector. Notice the ":hover" - that is called a pseudo selector. 
We'll dive into more of those later, but for reference right now you can use :visited and :active on the anchor tag also.
 
Moving on, there are "classes" - each CSS class can be added to *any* HTML tag to give it a specific style. Classes are 
meant to be re-used. You'll add them to HTML tags like so: 
  
```html
<input type="text" placeholder="enter your username" class="round-edges" />
```
  
We'll style that class like so:
 
```css
.round-edges {
  border-radius: 25px;
  border-color: black;
}
```
  
The "." preceding the class name denotes that it is a class to the browser when it reads your CSS. Speaking of which,
IDs are preced with "#"; they are also designed to only be used once. You want to use them to specify specific HTML elements. 
One could be for your header section, another for your menu, another for the content, and perhaps one for a footer? You can
always use as many as you want for targetting specific elements. You'll add an ID like so:

```html 
<div id="body-content" class="round-edges">
</div>
```
  
To target this with a CSS selector:
 
```css
#body-content {
  font-size: 24px;
  font-weight: bolder;
}
```
  
And yes, you can use a class at the same time as an ID. Now, what happens if you both the CSS class and the ID have code that
conflict with each other? Consider:
 
```css
#body-content{
  font-size: 20px;
}
.round-borders {
  font-size: 24px;
  border-radius: 25px;
}
```
  
This is tricky - depending on which CSS selector is declared LAST will be given preferred treatment and their CSS code will be
used. So in the above example, the font-size will be `24px` because `.round-borders` is declared AFTER the ID. You can get around this, 
however. How? Add the `"!important"` flag to the end of a declared selector:

```css 
#hero {
  font-color: blue !important;
  font-size: 64px !important;
  font-weight: bolder !important;
}
```
  
Whenever the #hero ID is placed somewhere, it will always overrride the declared style in any other selector that is attached 
to your HTML element. Consider it your CSS superhero - however, don't rely on it too much otherwise you'll end up with
hard to maintain code.
