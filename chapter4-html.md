## HTML

HTML describes the structure of a page.

HTML code are the characters that are inside the angled brackets, e.g. ```<body>```. These are called elements. Elements are usually made up by two tags, an opening and a closing tag. The closing tag has an forward slash before the element name, e.g. ```</body>```. Some elements, such as ```<img>``` does not need a closing tag because it is not possible to have content between the tags.  

Each element acts as a container, telling you something about the information that lies in it.

Tags and elements might be a bit confusing to separate. In short elements represents some structure in the document, and consists of an opening and closing tag. E.g. `<body>` is a tag while `<body></body>` is an element, enclosed by two tags.

### Document structure
An HTML document has some requirements in order to be rendered correctly. Most browsers tries to guess the meaning of the document if it is not correctly set up. Thus you might end up with the right result, but it can be implemented incorrectly. This may lead to your page looking differently across browsers, because browsers guess differently. To ensure that your page looks consistent across browsers should write HTML correctly.

The correct way to set up a HTML document is like this:

```
<!DOCTYPE html>
<html>
  <head>
    ...
  </head>
  <body>
    ...
  </body>
</html>
```

I'll now give an explanation of the elements present in the setup, namely `<html>`, `<head>`, `<body>`, and the document declaration `<!DOCTYPE html>`.

#### Document declaration
At the top of the document, you should have a document declaration, telling your browser how to read the document. Writing `<!DOCTYPE html>` tells the browser to read the document as a HTML5 page.

#### Html
The `<html>` element encloses everything on the page. All your code should be within those opening and enclosing tags.
The child elements of `<html>` is the `<head>` and `<body>` elements.

#### Head
This element contains information about the document, and will not be rendered in the browser. Examples are link to resources, metadata, and the title shown in browser tabs.

Below are some useful tags to know:

`<meta charset="UTF-8">` tells the browser how to interpret characters. Using UTF-8 you can display nordic characters correctly. There are also other uses for the meta element. Look [here](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta) for more information.

`<title>` is the title of the page and is usually shown on the tab for that page, and should reflect both the title on your page and where on the site the user is.

`<link href="style.css" rel="stylesheet">` includes a stylesheet for your document, separating your style from the document. Link can also include other resources, look [here](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link) for more information.

#### Body
Everything inside the body is shown inside the browser window, and thus is the content of your page.

The elements inside the `<body>` element are often either <i>inline</i> or <i>block</i> elements, depending on their default `display` value.

Block level elements always start on a new line and takes up the full width available. Examples of block level elements are:
* div
* h1 - h6
* p
* form

Inline elements does not start on a new line, and only takes up as much width as necessary. Examples of inline level elements are:
* span
* a
* img

It will become clear later on what these example elements are. Just remember that block levels start on a new line, while inline elements stays on the same line.

You can read about all the different display values [here](https://developer.mozilla.org/en-US/docs/Web/CSS/display), but note that display is a CSS property, and block and inline are the two values you should know at this point.

### Attributes
Attributes provide additional information about the content of an element. They appear inside the opening tag and consists of a name (the attribute) and a value, separated by an equal sign. The name part indicates what kind of extra information you are providing. The value part is the setting of the attribute.

```
<p lang="no">Et element med norsk tekst</p>
```

In the example above the attribute *lang* indicates that you will give information about the language of the element. The value for this attribute is "no", indicating that the paragraph is in Norwegian.

Such attributes makes it easier for browsers to render the elements correctly, also it helps screen readers and those trying to make sense of your markup, e.g. search engines.

### Text

In this section you will learn a lot about text, and how to best mark it up. In order to create a orderly document, you should use the elements correctly.

#### Headings

A heading should briefly describe the section it introduces, and are written between the the opening and closing tags `<h*></h*>` (the * is a number between 1 and 6). The tags thus are:

```
<h1></h1>
<h2></h2>
<h3></h3>
<h4></h4>
<h5></h5>
<h6></h6>
```

These tags are ordered in a hierarchy. `<h1>` is the most important, and `<h6>` the least. You should use `<h1>` on the most important heading on your page, e.g. the main title or page title. Other than being readable by the user, headings can be used by agents to, for example, automatically construct table of contents.

The heading elements has different visual style to differentiate the importance of the heading. The heading level have a semantic meaning so you should not skip levels. In the code example below you can see that the different heading levels are used. Two headings also have the same content, but because one in on a lower level, we are fine (though you should try to have different titles). The heading level tells us which heading it is a subheading to.

```
<h1>IT2805</h1>
...
<h2>Introduction</h2>
...
<h2>HTML</h2>
...
<h3>Document structure</h3>
...
<h4>Html</h4>
...
<h4>Head</h4>
...
<h3>Attributes</h3>
...
<h2>Site structure</h2>
...
```

The ... indicates that there should be some content there.

Only use one `<h1>` tag per page. By convention it is used to display the page title, and other headings starting with `<h2>`. And don't use lower level headings to decrease font size, use CSS' font-size property instead.

#### Paragraphs

A paragraph is a block of text, surrounded by the opening and closing tag `<p></p>`. `<p>` is a block element, thus each element will be shown on a new line.

#### Special markup
We can change how our text looks with inline elements. E.g. making the text bold or italic. Later we will learn to use CSS to style our text, but even then these elements are not obsolete. The browser gives them default styling, and you could change this with CSS. Keep in mind the function of e.g. bold text, it should really be bold.

##### Bold
You make the text bold by enclosing it in the tags `<b></b>`. These tags does not bear any semantic meaning other than highlighting the text. It should not be used for continuous text (body text), as it makes for worse readability, and looses it's function of highlighting keywords.

##### Italic
To make text italic, surround it with the tags `<i></i>`. As with bold, you should only use it to make some words stand out, not on an entire text.

##### Superscript and subscript
When writing about math or chemistry, or any other topic in need of superscript and subscript, you can use the tags `<sup></sup>` and `</sub></sub>` respectively. E.g. 2<sup>n</sup> is typed `2<sup>n</sup>` and H<sub>2</sub>O is typed `H<sub>2</sub>O`.

##### White space
In HTML, we have white space collapsing. That means that you can write as many white spaces after each other that you  like, and they will be treated as one white space. The same is true for line breaks. Coders can use this to organize their coding, making it easier to read. E.g.

```
The whites                doesn't scare me
```
will be rendered as:

The whites doesn't scare me

You can use this to indent your code, so that you will have a structure similar to this:

```
<body>
  <header>
    <h1>This is an header</h1>
  </header>
  <section>
    <p>
      This is a really short paragraph.
    </p>
    <p>
      This is shorter.
    </p>
  </section>
</body>
```
This will make the code easier to read, and see the document structure, e.g. which elements encloses other elements.

##### Line breaks
The paragraph tag `<p>` will give you space between each paragraph. If you only want to have a new line (a soft line break, if you want to sound like a pro) within the same paragraph, you can use `<br>`. No closing tag is necessary.

### Lists

In HTML we have two kinds of lists, ordered and unordered. The difference being that the ordered use numbers, while the unordered uses bullets. You create a list by writing the opening and closing tags, and inside them you write your list elements `<li>List element</li>`. The list element tag is common for ordered and unordered lists.

An ordered list is enclosed in the `<ol></ol>` element. You write an ordered list as such:
```
<ol>
  <li>List element</li>
  <li>List elementer</li>
  <li>Even list elementer</li>
  <li>List elementest</li>
</ol>
```
... which gives the following output:
1. List element
2. List elementer
3. Even list elementer
4. List elementest

The unordered list is enclosed in the `<ul></ul>` element. You write an unordered list as such:

```
<ul>
  <li>List element</li>
  <li>List elementer</li>
  <li>Even list elementer</li>
  <li>List elementest</li>
</ul>
```

... which gives the following output:
* List element
* List elementer
* Even list elementer
* List elementest

You can also have a nested list, both in ordered and unordered lists. To do this you create another list within a list element. E.g. for an ordered list you will write:

```
<ol>
  <li>List element</li>
  <li>List within a list
    <ol>
      <li>Look at this list</li>
      <li>It is within another list</li>
    </ol>
  </li>
  <li>I'm just a regular list element</li>
</ol>
```

This will give:
1. List element
* List within a list  
    1. Look at this list
    * It is within another list
* I'm just a regular list element

Notice how 'List within a list' have a opening tag in front of it, but not a closing tag after it. That is because the list element is closed after the sublist is written.

You can change `<ol>` to `<ul>` to get an unordered list. You can also mix list types, just remember to open and close with the same tags.

### Links

Create a link using the `<a></a>` element. An user can click on anything between the opening `<a>` and closing `</a>`, even images! Using the `href` attribute, you specify where you want to link to. It looks like this:

```
<a href="http://it2805.github.com">IT2805</a>
```

The value of the `href` attribute is called an URL. URL is short for Uniform Resource Locator, and says where the resource is located. You can read more about URLs, and their superset URIs, in chapter 5.

#### Absolute URLs
When linking to other sites, you need to use the full web address, starting with <i>http://</i>. This is known as an absolute URL. If you use the absolute URL, you will be taken to the same page, no matter where you are linking from.

#### Relative URLs
When we are linking to pages within our own web site, you should use relative URLs. Instead of describing the full URL, you use the shorthand notation to say where a resource is, relative to where you are linking from. This has an advantage when you are developing a site locally on your computer, as you do not need a domain name.

In the file hierarchy below we want to link from `index.html` to `starblaster.html`.

```
.
├── products
│   └── starblaster.html
└── index.html
```
We would then have to write:


```
<a href="products/starblaster.html">Starblaster</a>
```

If we want to link from starblaster.html to index.html, we would have to write:

```
<a href="../index.html">Home</a>
```

Notice the `../`. This indicates that the path is one folder up. Should we need to go two folders up in the hierarchy, we would write `../../`.

For both relative and absolute URLs, the URLs must be exact, or else the resource will not be found.

#### Linking to a specific part of the same page
We have now talked about how to link to other pages or resources. What if we want to link to something on the same page? Say you have a table of contents for a long page, and you want to link to the corresponding sections.

You do this by linking to the `id` of those paragraphs. `id` is an attribute you can set on opening tags. They do not magically appear though, you have to make them. In the case of creating a table of content, a good practice would be to add the `id` attribute in your headings, e.g. `<h2>`. The value of the `id` attribute should start with a letter or an underscore (not a number or any other character) and, on a single page, no two `id` attributes can have the same value.

To link to an element that uses an `id` attribute you use the `<a></a>` element, but the value of the `href` attribute starts with the `#` symbol, followed by the value of the `id` attribute of the element you want to link to. You can see the how it is done in the example below.

```
<a href="#summary">Summary</a>

<h2 id="summary">Summary</h2>
```

Clicking the first link would make the browser scroll down to where the title `summary` starts.

If you want to link to a specific part of another page, you add the `id` value, starting with the `#` symbol, after the address. E.g.:

```
<a href="http://it2805.github.com/html#specificpart">Linking to a specific part of the same page</a>
```

#### Opening links in a new tab
If you want to open a link in a new window, you can use the `target` attribute on the opening `<a>` tag. The value should then be `_blank`. E.g.:

```
<a href="http://it2805.github.com" target="_blank">NTNU</a>
```

One of the most common reasons a link would open in a new tab is if it points to another website. In such cases, we hope the user will return to our site after finishing looking at the other one.

As a good practice, only open links in a new tab when you have to, and when it is meaningful to do so.

#### Email links
To create a link that starts up the user's email client, and addresses an email to a specified email address, you use the `<a>` element and the `href` attribute. However, this time the value of `href` starts with `mailto:` followed by the email address. E.g.:

```
<a href="mailto:example@email.com">Email example</a>
```

### Images

Images in HTML is included using the `<img>` tag. You reference the image using the `src` attribute, with the value being the path to you image. E.g. for this file hierarchy:

```
.
├── products
│   └── starblaster.html
├── images
|   └── starblaster.jpg
└── index.html
```

... you would write it like this, when referencing to the image from `starblaster.html`:

```
<img src="../images/starblaster.jpg">
```

This will render an image in the browser that has the same height and width as the image it self. That might not always be desirable. To change this you can use the attributes height and width to constrain your image size. E.g.:

```
<img src="../images/starblaster.jpg" width="500px" height="400px">
```

Images often take longer to load than other HTML code. Thus it is a good idea to specify the size of the image so that the browser can render the rest of the text on the page while leaving he right amount of space for the image that is still loading.

Be aware that even if you resize your image using the width and height attributes, the file will have the same size measured in kilobytes and megabytes. Resize your image using a photo software (e.g. Photoshop or any other tool, there are web pages that does this) to reduce the file size.

There are a couple of other attributes you should know of `alt` provides a text description of the image which describes the image if you cannot see it. The `alt` attribute should give an accurate description of the image's content so it can be understood by screen readers and search engines. You can also use the `title` attribute to provide additional information about the image. Most browsers will display the content of this attribute in a tooltip when the user hovers over the image.

As `<img>` is a inline element, it will be placed on the same line as where you declare it. That is, if you declare it inside a paragraph, it will be inside the paragraph, and the height of that line will be the same as the image's height. You can place it before the paragraph in order to place it outside of the text. You will learn how to use CSS later, but the best way to style an image, e.g. aligning it, is best done using CSS.  

When you are using images, think of these three guidelines (some will call them rules):
1. <b>Save the image in the right format</b>  
The file formats JPG, gif and png are the most often used formats, and has the widest support among browsers. If you choose the wrong image format your images might not look as sharp as they should, and the web page might load slower.
* <b>Save the image at the right size</b>  
You should save the image at the same width and height as it will appear on the website (measured in pixels). If the image is smaller than the width or height that you have specified, the image can be distorted and stretched, and the pixels will be visible. If the image is larger than the width and height you have specified, the image will take longer to load on the page.
* <b>Measure images in pixels</b>  
As computer screens are made up of pixels, you should also measure your images in pixels (not centimeters).

#### Images as links
You can use the image element as a link if you want. In stead of a text between the `<a>` tags, put an image there.

```
<a href="products/starblaster.html"><img src="images/starblaster.jpg"></a>
```

#### Image formats
There are different image formats to choose from, and they all have their pros and cons. To understand the differences, there are two terms you should know about compression:
* <b>Lossless: </b> The image is made smaller, but this does not affect the quality
* <b>Lossy: </b> The image is made (even) smaller, and it affects the quality. Saving the image over and over again would make the image quality get progressively worse.

This information is gathered from [stack overflow](http://stackoverflow.com/questions/2336522/png-vs-gif-vs-jpeg-vs-svg-when-best-to-use). Here you can read more about other aspects of the formats.

Below are an explanation on the four most used image formats, their advantages and disadvantages.

##### JPEG
JPEG (or JPG) is the most common file format for showing images, and for photos and images with much details. It removes details not visible for the human eye, and is a lossy format, which means that each time you save it you will loose quality. The lossy compression means that it is bad for logos and line drawings (images with large areas covered by one color).

Good for photos and gradients, bad for logos illustrations.

##### PNG
PNG is a lossless format, meaning that it will not loose any details when being saved. Then why not use PNGs on photos? That is because the images would be ridiculous large, and are best used on graphics and logos.

Good for illustrations, logos and images where part of the image is transparent. Bad for photos.

##### GIF
It does not matter if you pronounce it "jif" og "gif", the gif format behaves the same either way. There is a limited number of colors available, so it is not suitable for showing photos with high resolution. GIFs are today most suitable for animations, or showing video snippets, without sound, in an image format. These files grow fast in size.

Good for animations, bad for anything else.

##### SVG
SVG is, unlike the previous formats, a vector format, rather than raster. That means that you can scale the image indefinitely without loosing quality. This is suitable for simple images such as logos and graphics, but not photos, as the lines are mathematically calculated, rather than being described with pixels. SVG files can be written using XML, or with software such as Adobe Illustrator.  

Good for logos, graphics and animations. Bad for photos.

### Tables

Tables are used to represent information in a grid format. In HTML, a table is written row by row. Each block in the grid is referred to as a table cell.

In order to make a table, you need rows and cells. To create the table, use the `<table></table>` element. Each row is encapsulated by the opening and closing tag `<tr></tr>` (tr stands for table row). Inside a row, each cell is represented using `<td></td>` (td stands for table data).

In order to create the table below:
<table>
  <tr>
    <td>Linjeforening</td>
    <td>Kontor</td>
  </tr>
  <tr>
    <td>Abakus</td>
    <td>P15</td>
  </tr>
  <tr>
    <td>Hybrida</td>
    <td>Gamle kjemi</td>
  </tr>
  <tr>
    <td>Leonardo</td>
    <td>Produktdesign/IPD</td>
  </tr>
  <tr>
    <td>Online</td>
    <td>P15</td>
  </tr>
</table>

... you would write:
```
<table>
  <tr>
    <td>Linjeforening</td>
    <td>Kontor</td>
  </tr>
  <tr>
    <td>Abakus</td>
    <td>P15</td>
  </tr>
  <tr>
    <td>Hybrida</td>
    <td>Gamle kjemi</td>
  </tr>
  <tr>
    <td>Leonardo</td>
    <td>Produktdesign/IPD</td>
  </tr>
  <tr>
    <td>Online</td>
    <td>P15</td>
  </tr>
</table>
```

Even if a cell has no content, you should still use a `<td>` element to represent the empty cell, otherwise the table will not render correctly.

#### Table headings
To represent the heading of a table, use the `<th>` tag. You use it as you would use the `<td>` tag. E.g.:

```
<table>
  <tr>
    <th>Linjeforening</th>
    <th>Kontor</th>
  </tr>
  <tr>
    <td>Online</td>
    <td>P15</td>
  </tr>
</table>
```

... would render:

<table>
  <tr>
    <th>Linjeforening</th>
    <th>Kontor</th>
  </tr>
  <tr>
    <td>Online</td>
    <td>P15</td>
  </tr>
</table>

Notice that the header is displayed as bold. This is the default style by most browsers. Using `<th>` to define the header helps people using screen readers, improves the ability for search engines index your page and gives you greater control over the table's appearance using CSS.

If you want to have row headings, you can do that also. You should then use the `scope` attribute with the value `row`. E.g.:

```
<table>
  <tr>
    <th scope="row" >Linjeforening</th>
    <td>Online</td>
  </tr>
  <tr>
    <th scope="row" >Kontor</th>
    <td>P15</td>
  </tr>
</table>
```
... would render:
<table>
  <tr>
    <th scope="row" >Linjeforening</th>
    <td>Online</td>
  </tr>
  <tr>
    <th scope="row" >Kontor</th>
    <td>P15</td>
  </tr>
</table>

#### Spanning columns and rows

Sometimes you might want to have columns or rows, or both, that stretch across more than one row or column. This might e.g. be in cases where the entries are longer than the given cell space.

On the `<th>` and `<td>` elements you would then use the `colspan` or `rowspan` attributes.

It might be hard to separate the two, so here are some examples. First out is `colspan`. The following code:

```
<table>
  <tr>
    <th></th>
    <td>8 am</td>
    <td>9 am</td>
    <td>10 am</td>
    <td>11 am</td>
  </tr>
  <tr>
    <th>Monday</th>
    <td colspan="2">IT2805</td>
    <td colspan="2">MA0001</td>
  </tr>
  <tr>
    <th>Tuesday</th>
    <td></td>
    <td></td>
    <td colspan="2">MA0001</td>
  </tr>
</table>
```
... would render this table:

<table>
  <tr>
    <th></th>
    <td>8 am</td>
    <td>9 am</td>
    <td>10 am</td>
    <td>11 am</td>
  </tr>
  <tr>
    <th>Monday</th>
    <td colspan="2">IT2805</td>
    <td colspan="2">MA0001</td>
  </tr>
  <tr>
    <th>Tuesday</th>
    <td></td>
    <td></td>
    <td colspan="2">MA0001</td>
  </tr>
</table>

Note that the first cell is empty, but written, so that the table will be rendered correctly.

As mentioned, if you want to stretch down across more than one row you would use `rowspan`. This code snippet:

```
<table>
  <tr>
    <th></th>
    <th>Monday</th>
    <th>Tuesday</th>
  </tr>
  <tr>
    <th>8 am</th>
    <td rowspan="2">IT2805</td>
    <td></td>
  </tr>
  <tr>
    <th>9 am</th>
    <td></td>
  </tr>
  <tr>
    <th>10 am</th>
    <td rowspan="2">MA0001</td>
    <td rowspan="2">MA0001</td>
  </tr>
  <tr>
    <th>11 am</th>
  </tr>
</table>
```

... would render this table:
<table>
  <tr>
    <th></th>
    <th>Monday</th>
    <th>Tuesday</th>
  </tr>
  <tr>
    <th>8 am</th>
    <td rowspan="2">IT2805</td>
    <td></td>
  </tr>
  <tr>
    <th>9 am</th>
    <td></td>
  </tr>
  <tr>
    <th>10 am</th>
    <td rowspan="2">MA0001</td>
    <td rowspan="2">MA0001</td>
  </tr>
  <tr>
    <th>11 am</th>
  </tr>
</table>

#### Long tables
There are three elements that help distinguish between the main content of the table and the first and last rows. These elements help people who use screen readers, and also allow you to style these sections in a different manner than the rest of your table.

These are the table header `<thead>`, table body `<tbody>` and the table footer `<tfoot>`. The headings of the table should go in the `<thead>` element. The body should be in the `<tbody>`, and the footer in the `<tfoot>` element.

You can see this used in the table below. The table isn't long in this example, that is just to save space. The following code:

```
<table>
  <thead>
    <tr>
      <th>Date</th>
      <th>Income</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>12th July</td>
      <td>612</td>
    </tr>
    <tr>
      <td>14th July</td>
      <td>765</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td></td>
      <td>1377</td>
    </tr>
  </tfoot>
</table>
```

... will render this table:
<table>
  <thead>
    <tr>
      <th>Date</th>
      <th>Income</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>12th July</td>
      <td>612</td>
    </tr>
    <tr>
      <td>14th July</td>
      <td>765</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td></td>
      <td>1377</td>
    </tr>
  </tfoot>
</table>

You don't see a difference, but that is just the lack of styling. We could use CSS to style only the `<thead>` element, should we want to.

Part of the reason for having separate `<thead>` and `<tfoot>` elements is so that, if you have a table that is taller than the screen (or, if printed, longer than one page) the browser can keep the header and footer visible whilst the contents of the table scroll. This is intended to make it easier for users to see which column the data is in.

### Comments
Often, to make your code more readable, you would want to add comments to it, but not have them render in the browser. This is done by enclosing a comment in `<!--` and `-->`. E.g., this code snipped:
```
<!-- Lenke til it2805.github.com -->
<a href="http://it2805.github.com">IT2805</a>
```
would render:  

<a href="http://it2805.github.com">IT2805</a>

This is often used when it is not clear from the code what is going on, or you want to make it easy to see what opening and closing tags belong together. Speaking by experience, you may get lost in the number of divs, and which closing tags belong to which opening tags. E.g.:

```
<div id="content">
  <div id="header">
  </div> <!-- /header -->
  <div id="body">
    ...
  </div> <!-- /body -->
</div> <!-- /content -->
```

In this case `/header` means that this is the end of the header tag.

Comments are also useful to quickly make code not render, in cases you want to see the difference without actually deleting the code.

Suddenly I introduced the div element. This is an element which does not represent anything. It is used to group elements together, most often for styling purposes using CSS. You will see a lot more of it in chapter 7. As the div element does not have any semantic meaning it should only be used when no other semantic element (such as `<article>` or `<footer>`) is appropriate (more on these semantic elements two sections down).

### Semantic elements

With HTML5, elements with a semantic meaning were introduced. This means that e.g. search engines can reason about the content of an element. You should thus strive to use these elements, rather than divs that bear no semantic meaning. Below are some of these elements listed, with an explanation on how they should be used. A complete overview over the HTML elements can be found at [Mozilla Developer Network](https://developer.mozilla.org/en-US/docs/Web/HTML/Element).

In order for these elements to have a semantic value, they have to be used correctly. That is that there are rules for what elements can be their parent and child. You will find more information about this in the link provided above.

#### Header
The `<header>` element holds a group of introductory or navigational aids, e.g. heading elements, logo, search forms and navigation bar.

```
<header>
  Logo
</header>
```

Do not confuse it with the `<head>` element, which contains metadata about the document. The `<header>` element has to be a child of the `<body>` element, that is, it has to reside within it.

#### Footer
The `<footer>` element represents a footer for its nearest section. That is, it can be at the bottom of the `<body>` element, or at the bottom of a `<section>` element (more on that later).

In the footer you often find a list of important sub pages on the website, contact information and other useful information that should be easily available for the user.

```
<footer>
  Contact us at some@email.com
</footer>
```

#### Section
The `<section>` element is a generic section of the document, i.e. a thematic grouping of the content, typically with a heading.

Be aware though, do not use the `<section>` element as a generic container, use the `<div>` element instead. A rule of thumb is that the `<section>` element should logically appear in the outline of a document.

```
<section>
  <h2>Chapter 4: HTML</h2>
  Bla bla
</section>
```

#### Article
The `<article>` element is a self-contained composition in a document, which is intended to be independently distributable or reusable. This could be a forum post, a blog entry, or a news site article. Each `<article>` should be identified, typically by including a heading element as a child of the `<article>` element.

This element can be used by e.g. search engines to filter out unnecessary information on the page, such as the navigation bar and adds.

```
<article>
  <header>
    <h2>– Webtech is such an awesome course<h2>
  </header>
  <section>
    <p> A man said that during the lecture and everyone
        agreed.
    </p>
  </section>
</article>
```  

#### Nav
The `<nav>` element is a section of a page that links to other pages or to parts within the page. It is a section with navigation links. This element is only intended for major blocks of navigation, such as the navigation in the header. Links in the footer e.g. does not need to be encapsulated in the `<nav>` element.

```
<nav>
  <ul>
    <li><a href="#">Home</a></li>
    <li><a href="/about">About</a></li>
  </ul>
</nav>
```

#### Input

The `<input>` element is used to create interactive controls for web-based forms in order to accept data from the user. How the element works varies considerably depending on the value of its type attribute.

In stead of copy/pasting that into this document, you can read about it at [MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input).

It is important to set the type of input, using the type `attribute` and a matching value, such as:
* Button: A push button with no default behavior.
* File: A control that lets the user select a file.
* Password: A single-line text field whose value is obscured.
* Submit: A button that submits the form.

Using the attribute `placeholder` you can have a placeholder text in your input field. If you use the attribute `autofocus`, the input field will get the focus automatically when the user opens the page.

If you have several input fields on the page and want the user to tab through them in a specific order, use the `tabindex` attribute, and a number as the value. This is also useable on other links and buttons.

```
<input type="text" placeholder="Your name">
```

In a form, as you will see later, it is good design to have a label, as the placeholder will disappear once the user sets his/hers cursor in the input field.

Note that the input field is a self enclosing element.

#### Output
The `<output>` element represents the result of a calculation or user action. It should be used within a form element, or as a general output element.

```
<output name="result">60</output>
```

#### Figure
The `<figure>` element represents self-contained content, frequently with a caption (see figcaption below), and is typically referenced as a single unit. While it is related to the main flow, its position is independent of the main flow. Usually this is an image or an illustration.

```
<figure>
  <img src="https://avatars2.githubusercontent.com/u/18331244" alt="IT2805 logo">
</figure>
```

##### Figure caption
The `<figcaption>` element represents a caption associated with a figure. `<figure>` is its immediate ancestor which means `<figcaption>` can be the first or last element inside a `<figure>` block. The figcaption element is optional, if it is not there the parent figure element will have no caption.

```
<figure>
  <img src="https://avatars2.githubusercontent.com/u/18331244" alt="IT2805 logo">
  <figcaption>Fig. 1: Web technologies logo</figcaption>
</figure>
```

#### Strong
Using the `<strong>` element indicates that the content has a strong importance.

Browsers will by default show the content of a `<strong>` element as bold. As you might, and should, remember, the `<b>` element renders the text as bold. Even though they look the same, they have different usages as the `<strong>` element has a semantic meaning.

The code snippet:
```
<p>
  <strong>Do not</strong> use the camera as a candle holder
</p>
```

... would render:
<p>
<strong>Do not</strong> use the camera as a candle holder
</p>

#### Em
The `<em>` element indicates emphasis that subtly changes the meaning of a sentence. Browsers will by default render the content in italic. The `<i>` element will also render the text italic, but `<em>` holds a semantic meaning.

The code snippet:
```
<p>
  I <em>think</em> I am the best person ever!
</p>
```
... would render:
<p>
  I <em>think</em> I am the best person ever!
</p>

#### Quotes
There are two elements used for making quotations, `<blockquote>` and `<q>`.

The `<blockquote>` element is used for longer quotes, taking up an entire paragraph. Note that browsers tend to indent the content of this element. You should not use this element to indent text, rather use CSS. Remember that this element bears semantic meaning, that it is a quote. Use the `<p>` element inside the `<blockquote>` element.

The code snippet:
```
<blockquote cite="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/blockquote">
  <p>
    The HTML blockquote Element (or HTML Block Quotation Element) indicates that the enclosed text is an extended quotation
  </p>
</blockquote>
```

... would render:
<blockquote cite="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/blockquote">
  <p>
    The HTML blockquote Element (or HTML Block Quotation Element) indicates that the enclosed text is an extended quotation
  </p>
</blockquote>

For shorter quotes, that sits within a paragrah, use the `<p>` element.

The code snippet:

```
<p>Eleanor Roosevelt said:
  <q cite="http://www.wiseoldsayings.com/anger-quotes/">Anger is one letter short of danger.</q>
</p>
```

... would render:

<p>Eleanor Roosevelt said:
  <q cite="http://www.wiseoldsayings.com/anger-quotes/">Anger is one letter short of danger.</q>
</p>

Both elements may use the cite attribute to indicate where the quote is from. Its value should be a URL that will have more information about the source of the quotation.

#### Address
The `<address>` element is used to contain contact details of the author. It can be a physical address, but it can also be a name, phone number or email address.

You can use it together with the `<article>` element to describe the author of that article.

```
<address>
  <a href="mailto:some@mail.com">some@email.com</a>
</address>
```
