## CSS continued
In this chapter, you will learn more about CSS.

### Styling lists
It is possible to change how the default list looks, both ordered and unordered lists. You can do this by changing the bullet point, and where the bullet should be located.

The `list-style-type` property allows you to control the shape or style of a bullet point. It can be used on rules that apply to the `<ol>`, `<ul>` and `<li>` elements.

For an unordered list you can use the following values:

<ul>
  <li style="list-style-type: none;">none</li>
  <li style="list-style-type: disc;">disc</li>
  <li style="list-style-type: circle;">circle</li>
  <li style="list-style-type: square;">square</li>
</ul>

The code for this list looks like this:

```html
<ul>
  <li class="none">none</li>
  <li class="disc">disc</li>
  <li class="circle">circle</li>
  <li class="square">square</li>
</ul>
```

```CSS
.none{list-style-type: none;}
.disc{list-style-type: disc;}
.circle{list-style-type: circle;}
.square{list-style-type: square;}
```

For an ordered (numbered) list you can use the following values:

<ol>
  <li style="list-style-type: decimal;">decimal</li>
  <li style="list-style-type: decimal-leading-zero;">decimal-leading-zero</li>
  <li style="list-style-type: lower-alpha;">lower-alpha</li>
  <li style="list-style-type: upper-alpha;">upper-alpha</li>
  <li style="list-style-type: lower-roman;">lower-roman</li>
  <li style="list-style-type: upper-roman;">upper-roman</li>
</ol>

The code for this list looks like this:

```html
<ol>
  <li class="decimal">decimal</li>
  <li class="decimal-leading-zero">decimal-leading-zero</li>
  <li class="lower-alpha">lower-alpha</li>
  <li class="upper-alpha">upper-alpha</li>
  <li class="lower-roman">lower-roman</li>
  <li class="upper-roman">upper-roman</li>
</ol>
```

```CSS
.decimal{list-style-type: decimal;}
.decimal-leading-zero{list-style-type: decimal-leading-zero;}
.lower-alpha{list-style-type: lower-alpha;}
.upper-alpha{list-style-type: upper-alpha;}
.lower-roman{list-style-type: lower-roman;}
.upper-roman{list-style-type: upper-roman;}
```

You can also replace the bullet with an image, using the `list-style-image` property. The value for this property starts with the letters url, and is followed by a pair of parantheses. Inside the parantheses, the path to the image is given inside double quotes. This rule can be used on rules that apply to the `<ul>` and `<li>` elements.

```html
<ul> The people I like best
  <li>Me</li>
  <li>Myself</li>
  <li>I</li>
</ul>
```

```css
ul {
  list-style-image: url("path/to/image.png");
}
```

Lists are indented into the page by default and the `list-style-position` property indicates whether the marker should appear on the inside or the outside of the box containing the main points. This property can take one of two values:

* **outside:** The marker sits to the left of the block of text (this is the default behaviour if this property is not used).
* **inside:** The marker sits inside the box of text (which is indented).

```html
<ul class="outside">
  <li>It's really hard to come up with something funny to write in these list elements.</li>
  <li>Thus I wrote this boring text in stead. The width of the list has been limited to 250 px, so that you see the effect of outside vs inside.</li>
</ul>
<ul class="inside">
  <li>It's really hard to come up with something funny to write in these list elements.</li>
  <li>Thus I wrote this boring text in stead. The width of the list has been limited to 250 px, so that you see the effect of outside vs inside.</li>
</ul>
```

```css
ul.outside {
  list-style-position: outside;
}

ul.inside {
  list-style-position: inside;
}
```

<ul style="list-style-position: outside">
  <li>It's really hard to come up with something funny to write in these list elements.</li>
  <li>Thus I wrote this boring text in stead. The width of the list has been limited to 250 px, so that you see the effect of outside vs inside.</li>
</ul>
<ul style="list-style-position: inside">
  <li>It's really hard to come up with something funny to write in these list elements.</li>
  <li>Thus I wrote this boring text in stead. The width of the list has been limited to 250 px, so that you see the effect of outside vs inside.</li>
</ul>


## Change between inline and block elements
The `display` property allows you to turn an inline element into a block-level element or vice versa, and can also be used to hide an element from the page. The values this property can take are:

* **inline:** This causes a block-level element to act like an inline element
* **block:** This causes an inline element to act like a block-level element
* **inline-block:** This causes a block-level element to flow like an inline element, while retaining other featers of a block-level element.
* **none:** This hides an element from the page. In the example below, the element acts as though it is not on the page at all (although a user could still see the content of the box by viewing the source in their browser).

If you use this property, it is important to note that inline elements are not supposed to create block-level elements.

In the example below you can see a list. Each item in the list is usually treated as a block-level element, but the rule for the `<li>` elements indicates that they should be treated as inline elements, which means they will sit alongside each other rather then appearing on new lines.

This technique is often used to create navigation for a site, and in this example a margin has been added to the right of each of the items to separate them out. The rule that applies to the `<li>` element whose class is `coming-soon` has been hidden as if it were not in the page at all.

```html
<ul>
  <li>Home</li>
  <li>Products</li>
  <li class="coming-soon">Services</li>
  <li>About</li>
  <li>Contact</li>
</ul>
```

```css
li {
  display: inline;
  margin-right: 10px;
}

li.coming-soon {
  display: none;
}
```

TODO: INSERT IMAGE OF EXAMPLE


### Hide boxes
The `visibility` property allows you to hide boxes from users but it leaves a space where the element would have been. The property can take two values:

* **hidden:** This hides the element
* **visible:** This shows the element

If the `visibility` of an element is set to `hidden`, a blank space will appear in its place. If you do not want a blank space to appear, then you should use the `display` property with a value of `none` instead.

Do note that anyone can view the contents of any elements whose `visibility` property has been set to `hidden` by viewing the source in their browser.

```html
<ul>
  <li>Home</li>
  <li>Products</li>
  <li class="coming-soon">Services</li>
  <li>About</li>
  <li>Contact</li>
</ul>
```

```css
li {
  display: inline;
  margin-right: 10px;
}

li.coming-soon {
  visibility: hidden;
}
```

TODO: INSERT IMAGE OF EXAMPLE

### Document flow
In addition to styling elements, CSS can manipulate how the elements flow. The flow refers to how the element follow each other in the document, and how they behave next to each other. Each element has a default rule, e.g. block elements will start on a new line, while the inline elements will continue on the same line. This behavior can be changed using the CSS properties `float`, `position` and `z-index`.

If one block element sits inside another block element, then the outer element is know as the containing or parent element. It is common to group a number of elements together inside a `<div>` (or other block-level) element. E.g., you might group together all of the elements that form the header of a site (such as the logo and the main navigation). The `<div>` element that contains this group of elements is then referred to as the containing (or parent) element. An element may be nested inside several other block-level elements. The containing element is always the direct parent of that element.

TODO: INSERT IMAGE OF GROUPED ELEMENTS (pg. 362)

CSS has the following position schemes that allow you to control the layout of a page: normal flow, relative positioning, and absolute positioning. You specify the positioning scheme using the `position` property. You can also float elements using the `float` property.

#### Normal flow
Every block element appears on a new line, causing each item to appear lower down on the page than the previous one. Even if you specify the width of the boxes and there is space for two elements to sit side-by-side, they will not appear next to each other. This is the default behavior (unless you tell the browser to do something else).

TODO: INSERT IMAGE OF NORMAL FLOW

In normal flow, each block-level element sits on top of the next one. Since this is the default way in which browsers treat HTML elements, you do not need a CSS property to indicate that elements should appear in normal flow, but the syntax would be `position: static;`.

In the example below, the width property for the heading has not been specified, so you can see how it stretches the width of the entire browser window by default. The paragraphs are restricted to 450 pixels wide. This shows how the elements in normal flow start on a new line even if they do not take up the full width of the browser window. <i>All of the examples demonstrated in this section, and the rest about document flow, will use a similar HTML structure.</i>

```html
<body>
  <h1>Positioning</h1>
  <p>

  </p>
</body>
```

```css
body {
    width: 750px;
    font-family: Arial, Verdana, sans-serif;
    color: #040404;
    background-color: #FCFCFC;
}

h1 {
  background-color: #EFEFEF;
  padding: 10px;
}

p {
  width: 450px;
}
```

#### Relative positioning
This moves an element from the position it will be in normal flow, shifting it to the top, right, bottom, or left of where it would have been placed. This does not affect the position of surrounding elements; they stay in the position they would be in in normal flow.

TODO: INSERT IMAGE OF REALTIVE PSOTIONSNIGN

The second paragraph has been pushed down and right from where it would otherwise have been in a normal flow.

Relative positioning moves an element in relation to where it would have been in normal flow. E.g., you can move it 10 pixels lower than it would have been in normal flow, or 20% to the right. You can indicate that an element should be relatively positioned using the `position` property with the value `relative`.

You then use the offset properties (`top`, `bottom`, `left` or `right`) to indicate how far to move the element from where it would have been in normal flow. To move the box up or down, you can use either the `top` or `bottom` properties. To move the box horizontally you can use either the `left` or `right` properties. The values of the box offset properties are usually given in pixels, percentages or ems.

```html
<body>
  <h1>Positioning</h1>
  <p>

  </p>
</body>
```

```CSS
p.example{
  position: relative;
  top: 10px;
  left: 100px;
}
```

TODO: IMAGE OF EXAMPLE

#### Absolute positioning
This positions the element in relation to its containing element. It is taken out of normal flow, meaning that it does not affect the position of any surrounding elements (as they simply ignore the space it would have taken up). Absolutely positioned elements move as users scroll up and down the page.

TODO: INSERT IMAGE OF ABSOUTE positioning

The heading is positioned to the top right, and the paragraphs start at the top of the screen (as if the heading were not there).

When the `position` property is given a value of `absolute`. the box is taken out of normal flow and no longer affects the position of other elements on the page (they act like it is not there). The box offset properties (`top`, `bottom`, `left` or `right`) specify where the element should appear in relation to its containing element.

In this example, the heading has been positioned at the top of the page and 500 pixels from its left edge. The width of the heading is set to be 250 pixels wide. The `width` property has also been applied to the `<p>` elements in this example to prevent the text from overlapping and becoming unreadable.

```html
<body>
  <h1>Positioning</h1>
  <p>

  </p>
</body>
```

```CSS
h1 {
  position: absolute;
  top: 0px;
  left: 500px;
  width: 250px;
}

p {
  width: 450px;
}
```

TODO: IMAGE OF EXAMPLE

#### Fixed positioning
This is a form of absolute positioning that positions the element in relation to the browser window, as opposed to the containing element. Elements with fixed positioning do not affect the position of surrounding elements and they do not move when the user scrolls up or down the page.

TODO: INSERT IMAGE OF FIXED position

The heading has been placed in the center of the page and 25% from the top of the screen (the rest appears in normal flow).

In the example below, the heading has been positioned to the top left hand corner of the browser window. When the user scrolls down the page, the paragraphs disappear behind the heading. The `<p>` elements are in normal flow and ignore the space that the `<h1>` element would have taken up. Therefore, the `margin-top` property has been used to push the first `<p>` element below where the fixed position `<h1>` element is sitting.

```html
<body>
  <h1>Positioning</h1>
  <p>

  </p>
</body>
```

```css
h1 {
  position: fixed;
  top: 0px;
  left: 0px;
  padding: 10px;
  margin: 0px;
  width: 100%;
  background-color: #efefef;
}

p.example {
  margin-top: 100px;
}

```
TODO: Image of example

#### Floating elements
Floating an element allows you to take that element out of the normal flow and position it to the far left or right of a containing box. The floated element becomes a block-level element around which other content can flow.

TOOD: INSERT IMAGE OF FLOATING elements

The heading has been floated to the left, allowing the paragraph of text to flow around it.

When you use the `float` property, you should also use the `width` property to indicate how wide the floated element should be. If you do not, results can be inconsistent but the box is likely to take up the full width of the containing element (just like it would in normal flow).

In the example below, a `<blockquote>` element is used to hold a quotation. It's containing element is the `<body>` element. The `<blockquote>` element is floated to the right, and the paragraphs that follow the quote flow around the floated element.

```html
<body>
  <h1>Positioning</h1>
  <blockquote>

  </blockquote>
  <p>

  </p>
</body>
```

```css
blockquote {
  float: right;
  width: 275px;
  font-size: 130%;
  font-style: italic;
  font-family: Georgia, Times, serif;
  margin: 0px 0px 10px 10px;
  padding: 10px;
  border-top: 1px solid #665544;
  border-bottom: 1px solid #665544;
}
```

You can use float to place elements side-by-side, if you e.g. would like a design with boxes next to each other.

When elements are floated, the height of the boxes can affect where the following elements sit. In the example below, you can see six paragraphs, each of which has a `width` and a `float` property set. The fourth paragraph does not go across to the left hand edge of the page as one might expect. Rather it sits right under the third paragraph. The reason for this is that the fourth paragraph has space to start under the third paragraph, but it cannot go any further to the left because the second paragraph is in the way.

```html
<body>
  <h1>Positioning</h1>
  <p>

  </p>
</body>
```

```css
body {
  width: 750px;
  font-family: Arial, Verdana, sans-serif;
  color: #665544;
}

p {
  width: 230px;
  float: left;
  margin: 5px;
  padding: 5px;
  background-color: #efefef;
}
```

TODO: IMage of example

Setting the height of the paragraphs to be the same height as the tallest paragraph would solve this issue, but it is rarely suited to real world designs where the amount of text in a paragraph or column may vary. It is more common to use the `clear` property (discussed further down) to solve this.

#### Clearing floats

The `clear` property allows you to say that no element (within the same containing element) should touch the left or right-hand side of a box. It can take the following values:
* **left:** The left-hand side of the box should not touch any other elements appearing in the same containing element.
* **right:** The right-hand side of the box will not touch elements appearing in the same containing element.
* **both:** Neither the left nor right-hand sides of the box will touch elements appearing in the same containing element.
* **none:** Elements can touch either side.

In the example below, the fourth paragraph has a class called `clear`. The CSS rule for this class uses the clear property to indicate that nothing should touch the left-hand side of it. The fourth paragraph is therefore moved further down the page so no other element touches its left-hand side.

```HTML
<p class="clear">

</p>
```

```css
body {
  width: 750px;
  font-family: Arial, Verdana, sans-serif;
  color: #665544;
}

p {
  width: 230px;
  float: left;
  margin: 5px;
  padding: 5px;
  background-color: #efefef;
}

.clear {
  clear: left;
}
```

#### Z-index
When you use relative, fixed or absolute positioning, boxes can overlap. If boxes do overlap, the elements that appear later in the HTML code sit on top of those that are earlier in the page.

If you want to control which elements sits on top, you can use the `z-index` property. Its value is a number, and the higher the number the closer that element is to the front. E.g., an element with a z-index of 10 will appear over the top of one with a z-index of 5.

### Inheritance
In CSS, child elements inherit from their parent element, even when the parent element is not the containing block. An element only inherits properties if the element itself does not define that property.

In the example below, you can see that the `<body>` element has the font property set. All elements within the body will now use the font Georgia, unless something else is specified. And guess what! `<h1>` has something else specified, so within the `<h1>` element, Helvetica will be the chosen font.

What will the color of the intro element be?

```HTML
<body>

  <h1>Hello inheritance</h1>
  <p class="intro">
    Let me introduce you to the world of inheritance.
    It's important to learn.
  </p>
  <p>
    If a child element has not defined a property,
    it will take that property from it's parent.
  </p>
</body>
```

```css
body{
  font-family: Georgia, serif;
  color: black;
}

h1{
  font-family: Helvetica, sans-serif;
}

.intro{
  color: #FAA21B;
}
```

That is correct, as intro has specified it's own `color` property, that rule will be chosen (because it's more specific).

### More pseudo classes
In the previous chapter you learned the pseudo classes to style something on hover. In this chapter you will learn some more. We start with refreshing the syntax:

```css
selector:pseudo-class {
  property: value;
}
```
#### :nth-child()
With this pseudo class you can style the nth child of a parent element, or any child element whose numeric position in the series of children matches the pattern an+b. The formula an+b is placed inside the parantheses, e.g.: nth-child(1n+0) would match every child element.

The values a and b must both be integers, and the index of an element's first child is 1. A common use case is to match every other row in a table.

In a list with list elements, the following code would affect every odd numbered list element:

```HTML
<ul>
  <li>li:nth-child(2n+1)</li>
  <li>li:nth-child(odd)</li>
  <li>li:nth-child(2n)</li>
  <li>li:nth-child(even)</li>
  <li>li:nth-child(0n+1)</li>
  <li>li:nth-child(1)</li>
  <li>li:nth-child(-n+3)</li>
</ul>
```

```css
li:nth-child(2n+1){
  color: blue;
}
```

* **tr:nth-child(2n+1)**  
Represents the odd rows of an HTML table.
* **tr:nth-child(odd)**  
Represents the odd rows of an HTML table.
* **tr:nth-child(2n)**  
Represents the even rows of an HTML table.
* **tr:nth-child(even)**  
Represents the even rows of an HTML table.
* **span:nth-child(0n+1)**  
Represents a span element which is the first child of its parent; this is the same as the :first-child selector.
* **span:nth-child(1)**  
Equivalent to the above.
* **span:nth-child(-n+3)**  
Matches if the element is one of the first three children of its parent and also a span.

#### :required
The `:required` pseudo class represents any `<input>` element that has the `required` attribute set on it. This allows forms to easily indicate which fields must have valid data before the form can be submitted.

```css
input:required {
  property: value;
}
```

#### :focus
The :focus pseudo class is applied when an element has received focus, either from the user selecting it with the use of a keyboard or by activating with the mouse (e.g. a form input).

```css
input:focus {
  property: value;
}
```

#### :checked
The :checked pseudo class selector represents any radio (`<input type="radio">`), checkbox (`<input type="checkbox">`) or option (`<option>` in a `<select>`) element that is checked or toggled to an on state. The user can change this state by clicking on the element, or selecting a different value, in which case the :checked pseudo class no longer applies to this element, but will to the relevant one.

```css
/* any "checkable" element */
:checked {
  color: green;
}

/* only radio elements */
input[type="radio"]:checked {
  color: green;
}

/* only checkbox elements */
input[type="checkbox"]:checked {
  color: green;
}

/* only option elements */
option:checked {
  color: green;
}
```

#### :disabled and :enabled

The :enabled pseudo class represents any enabled element. An element is enabled if it can be activated (e.g. selected, clicked on or accept text input) or accept focus. The element also has an disabled state, in which it can't be activated or accept focus.

```css
input:enabled {
  color: #green;
}
```

The :disabled pseudo class represents any disabled element. An element is disabled if it can't be activated (e.g. selected, clicked on or accept text input) or accept focus. The element also has an enabled state, in which it can be activated or accept focus.

```css
input[type="text"]:disabled { background: #ccc; }
```

#### :valid and :invalid

The :valid pseudo class represents any `<input>` or `<form>` element whose content validates correctly according to the input's type setting. This allows to easily make valid fields adopt an appearance that helps the user confirm that their data is formatted properly.

The :invalid pseudo class represents any `<input>` or `<form>` element whose content fails to validate according to the input's type setting. This allows you to easily have invalid fields adopt an appearance that helps the user identify and correct errors.

```html
<form>
  <label>Enter a URL:</label>
  <input type="url" />
</form>
```

```css
input:invalid {
  background-color: #ffdddd;
}

input:valid {
  background-color: #ddffdd;
}
```

#### :lang()

The :lang pseudo class matches elements based on the language the element is determined to be in. In HTML, the language is determined by a combination of the lang attribute, the `<meta>` element, and possibly by information from the protocol (such as HTTP headers).

```html
<div lang="en"><q>This English quote has a <q>nested</q> quote.</q></div>
<div lang="fr"><q>This French quote has a <q>nested</q> quote.</q></div>
<div lang="de"><q>This German quote has a <q>nested</q> quote.</q></div>
```

```css
:lang(en) > q { quotes: '\201C' '\201D' '\2018' '\2019'; }
:lang(fr) > q { quotes: '« ' ' »'; }
:lang(de) > q { quotes: '»' '«' '\2039' '\203A'; }
```

### Overflow
The overflow property specifies whether to clip content, render scrollbars or just display content when it overflows its block level container.

Using the overflow property with a value different to visible (its default) will create a new block formatting context. This is technically necessary — if a float intersected with the scrolling element it would forcibly rewrap the content. The rewrap would happen after each scroll step, leading to a slow scrolling experience.

In order for the overflow property to have an effect, the block level container must either have a bounding height (height or max-height) or have white-space set to nowrap.

The overflow property can have four values:
* **visible:** Default value. Content is not clipped, it may be rendered outside the content box.
* **hidden:** The content is clipped and no scrollbars are provided.
* **scroll:** The content is clipped and desktop browsers use scrollbars, whether or not any content is clipped. This avoids any problem with scrollbars appearing and disappearing in a dynamic environment. Printers may print overflowing content.
* **auto:** Depends on the user agent. Desktop browsers like Firefox provide scrollbars if content overflows.

You write it as follows, inside a rule:

```css
/* Content is not clipped */
overflow: visible;

/* Content is clipped, with no scrollbars */
overflow: hidden;

/* Content is clipped, with scrollbars */
overflow: scroll;

/* Let the browser decide */
overflow: auto;
```
