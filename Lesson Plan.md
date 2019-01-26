# Lesson Planning

# Purpose

- Website basics
  - The relationship between HTML, CSS, and Javascript
- Essential HTML concepts
  - Closing tags vs self closing tags
  - Inline elements vs Block elements
  - IDs, classes, attributes
- Essential HTML tags and how they're used
- Basic CSS concepts
  - The cascade
  - Selectors
  - different units
- Essential CSS attributes
- How people with disabilities use the web
  - Keyboard navigation
  - Screen readers
  - Large text
  - How are sites are interpreted by assistive technology
    - Screen reader demo

# Essential HTML Concepts

## HTML tags

- HTML tags are marked by wrapping the tag's name in ankle brackets `<body>`.
- Most HTML tags have an opening and a closing tag that mark the beginning and ending of the tag A closing tag is the same as the opening tag except it has a forward slash after its first ankle `/` bracket. `<p>Hello</p>`.
- Some HTML tags are strange and do not require a closing tag like the image tag (`<img>`). They don't require a closing tag because it's information isn't contained between two tags.

## Structure of an HTML Document

- `<html>` tag wraps the document
- `<head>` contains information about the page
  - The title of the page, associated documents, etc
- `<body>` contains the page's content

## Inline Elements VS Block Elements

> **Block Elements:** Creates a new line on its container. It blocks others from sitting next to it.

```html
<h1>Heading 1</h1>
<p>Paragraph</p>
```

> **Inline Elements:** Does not create a new line. It will sit inline with other elements.

```html
<p>Paragraph with an <span style="color: red;">Inline Element</span>. <img src="/img/coding-toes.webp" alt="Animation of a fat man coding with his toes"></p>
```

## IDs, classes, attributes! Oh my!

> **IDs:** Are used to uniquely identify something on a page. Used for CSS and javascript selections and to link directly to a section of a page.

```html
<main id="main-content"></main>
```

> **Classes:** Are used to assign an element to a class name. Used for applying CSS Styles, and selecting elements in javascript.
> *Note:* Many styles can be applied to a single HTML element.

```html
<p class="big-text">This text is big</p>
<p class="big-text red-text">This text is big and red</p>
```

> **Attributes:** Other things that are sometimes put into HTML tags. Used to give additional information to a tag.
> *Examples:* The source of an image on an image tag or the destination of a link.

## Tag purposes

Some tags are used to add particular content on a page like images, paragraphs, headings, etc.

Others are used as generic containers used to simply group content together (generally for positioning and layout). Examples are divs and spans.

Finally others are known as Landmark elements which are tags that are used to annotate a document with information on where to find certain types of information like the main content, different sections, or the navigation. Landmarks are essential for people using assistive technology and are helpful for creating relevant search engine results.

# Essential HTML Tags

- p
  - Defines a paragraph.
  - Block element
- div
  - Generic container for other HTML elements
  - Used for grouping like tags together
  - Block element
- span
  - Generic inline container for phrasing content.
  - It is typically used to group elements for styling purposes.
  - Inline element
- h1 - h6
  - Different page headings
  - Used to create a hierarchy of information
  -  >**Note:** Don't skip heading tags (h1 to h3). It destroys the page hierarchy used by screen readers and search engine bots.
- a
  - An anchor tag. A bad name for a link.
  - Used to link other pages or other elements on the page.
  - Inline element
- ul
  - Unordered list
  - Creates a bulleted list
  - Block element
- ol
  - Ordered list
  - Creates a numbered list by default (can change it to other types of ordered lists, however)
  - Block element
- li
  - List item
  - What you put between of ul and ol tags
  - Block element
- img
  - Image tag
  - Requires 2 attributes: the src which defines where the image is located and the alt tag which is used to tell assistive technology what is in the image.
    - Note: you don't need to add text in an alt tag if the image is purely for decoration
  - Inline element
- main
  - HTML landmark element for defining the main content on a page.
  - Block element
- nav
  - HTML landmark element for defining where the page's navigation is
  - Block element
- section
  - HTML landmark element that defines a new section of a page's content. Generally has it's own heading within the section tags
  - Block element
- footer
  - HTML landmark element that defines what the footer of the page is.
  - Block element

# Essential CSS Concepts

## Syntax

CSS has 3 parts to its syntax (code grammar)

1. The selector
2. Curly braces
3. CSS properties

```css
/* 1. Selector */
div
/* 2. Curly braces */
{
  /* 3. CSS Property */
  font-size: 18px;
}
```

> **Note:** Each property ends with a semi-colon `;`

## Selectors

Selectors can be simple to very complicated. The most simple type of selection is just a tag selector. This is where you just give it a tag name

```css
h1 {
  color: red;
}
```

You can also select by class or id which you define in the HTML.

Classes selected by using a `.` followed by the class' name.

```css
.active {
  text-decoration: underline;
}
```

IDs are selected by using a `#` followed by the ID's name.

```css
#maincontent {
  background-color: white;
}
```

You may also use more than one selector that are separated by commas to apply the same style to multiple things.

```css
h1, h2 {
  color: aqua;
}
```

Finally you can target specific relationships using CSS selectors by first giving the selector the outer element followed by the inner element.

```css
ul li {
  text-decoration: none;
}
```

## The cascade

CSS stands for cascading style sheets. The cascade part is the concept that the later selectors in the document are the styles applied to the HTML elements.

```css
p {
  color: #BADA55
}

/* ... other code */

p {
  /* This style is applied instead of the original color */
  color: goldenrod;
}
```

## Specificity

The other rule for determining what style will be applied to an element is specificity. Specificity means the more specific the selector is selected over a less specific tag.

### Scale of specificity (low to high)

1. General tags (main, p, body)
2. Classes
3. IDs

![Star Wars Specificity Rules](img/css-specificity-wars.png)
[Stuff and Nonsense](https://stuffandnonsense.co.uk/archives/css_specificity_wars.html)

Each type of selector in the CSS declaration adds a certain amount of points to its specificity score. General gives 1 point, Classes give 10, IDs give 100.

`main{}` is less specific than `.container{}`. `.container{}` is less specific than