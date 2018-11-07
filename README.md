![alt text](header.png "Web development in a nutshell")


! Under development

# Introduction

To create a web pages, or web applications nowadays, we use **HTML**, **CSS** and **JavaScript**. Web browser receives the html-file from the server and renders it to the user. The styles and scripts can be embedded in the html-file or they can be downloaded as separate files from the server.

This document gives an overview of what is involved in creating web pages or web applications.

# W3C

World Wide Web (W3C) consortium is web standards organization that tries to get all the vendors to implement a set of core principles.

https://en.wikipedia.org/wiki/World_Wide_Web_Consortium

# HTML

HyperText Markup Language (HTML) describes the structure of a web page with elements. The web browser renders a visual representation of this structure.

```
<html>
    <head>
        <title>My website</title>
    </head>
    <body>
        <header>
            <h1>Header</h1>
        </header>
        <main>
            <p>A paragraph.</p>
            <img src="picture.jpg" />
        </main>
        <footer>
            all rights reserved
        </footer>
    </body>
</html>
```

## Elements

> _An HTML element is an individual component of an HTML (Hypertext Markup Language) document or web page, once this has been parsed into the Document Object Model. HTML is composed of a tree of HTML nodes, such as text nodes. Each node can have HTML attributes specified._ -[Wikipedia](https://en.wikipedia.org/wiki/HTML_element)

Elements are parts of a html structure that consist of a start tag, content of the element and a closing tag. The web page is build by structuring different elements together. An element can have attributes like image file path.

    <p> <- Start tag
        Some text  <- Content
    </p> <- Closing tag

#### Block elements

Block elements take the whole width of the container element and pushes down the it's sibling elements (line break). For example header elements like `<h1>` or`<div>`.

You can also change elements display properties in your style definitions.

#### Inline elements

Inline elements don't force a new line to begin after them. They can be inside a text paragraph for example. `span`, `a` and `img` are examples of inline elements.

#### Semantic elements

Semantic elements describe their meaning to the browser and the user. There are several different semantic elements like `header`, `footer`, `article` or `section`.

Even though you can build up a website with using only for example `div` block elements and not worry about semantics, it is a good practice to use correct elements to better support search engines and accessibility.

More information about accessibility: https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML

# CSS

Cascading Style Sheets (CSS) is a set of rules that define the layout and what the web page should look like visually. Styles can be loaded from an external file source or from inside a `style` element.

In the style definitions the syntax is this, first you give a selector of what elements you want to target and then inside the curly braces you give the styles for the selector.

If you want to target all the elements in the html, just give the element name like `p` for paragraph or `h1` for header.

    p   {
        color: red;
    }

In this case all the paragraph elements in the page will be red.
A good way to target specific elements is by giving the element a class attribute in the html and then target all the elements with that class.

```
<p class="center">
    This text will be centered
</p>
```

Now in the style definitions, target the center-class with `.center`

    .center {
        text-align: center;
    }

You can also target elements when they have a specific state like the cursor is hovering over them for example. **These are called pseudo classes.**

    a:hover {
        text-decoration: underline;
    }

You can also give an unique `id` attribute to an element and target it with `#`.
It is usually preferred to use class names rather than give unique id's to elements.

    #myid {
        color: hotpink;
    }

# JavaScript

JavaScript language is based on ECMAScript standard for scripting languages. It can be used to add dynamic functionalities to a web page. JavaScript is also used in Node.js environment in server side applications. JavaScript code can for example change the structure of a web page on the fly or get content from an API and render it to the page without need to refresh the page.

HTML can be embedded with scripts either from external file sources or inside a `<script>` and `</script>` tags.

> _JavaScript is an implementation of the ECMAScript standard._ -[Michael Aranda](https://medium.freecodecamp.org/whats-the-difference-between-javascript-and-ecmascript-cba48c73a2b5)
