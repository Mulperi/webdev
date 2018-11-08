![alt text](header.png "Web development in a nutshell")

! Under development

# Introduction

This document is intended to give an overview of what is involved in creating web pages or web applications and it may be used as a tool when teaching web development basics.

To create a web pages, or web applications, we use _HTML_, _CSS_ and _JavaScript_. Web browser receives the html-file from the server and renders it to the user. The styles and scripts can be embedded in the html-file or they can be downloaded as separate files from the server.

## Website or web application?

A website that has an application-like user experience (desktop or mobile) can be referred to as a _web application_ or _Single Page Application_ rather than a website (even if it really is just a website). Usually it means that the website runs smoothly and there is no page reloads when switching to another sub page or view. This is achieved with JavaScript that downloads new content when needed and updates the page structure dynamically.

To make dynamic web applications you can use pure JavaScript but typically it is preferred to use either a UI-library like React or a framework like Angular that are built for web app development specifically.

# W3C

World Wide Web Consortium (W3C) is web standards organization that tries to get all the vendors to implement a set of core principles.

https://en.wikipedia.org/wiki/World_Wide_Web_Consortium

# HTML

HyperText Markup Language (HTML) describes the structure of a web page with **elements**. The web browser renders a visual representation of this structure.

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
                <img src="dog.jpg" />
            </main>
            <footer>
                all rights reserved
            </footer>
        </body>
    </html>

## Elements

> _An HTML element is an individual component of an HTML (Hypertext Markup Language) document or web page, once this has been parsed into the Document Object Model. HTML is composed of a tree of HTML nodes, such as text nodes. Each node can have HTML attributes specified._ [Wikipedia](https://en.wikipedia.org/wiki/HTML_element)

Elements are parts of a html structure that consist of a start tag, content of the element and a closing tag. Some elements don't have a closing tag but you write the `/` that marks the end of the element inside the opening tag like `<img src="dog.jpg" />` for example.

The web page is build by structuring different elements together. An element can have attributes like image file path.

    <p> <- Start tag
        Some text  <- Content
    </p> <- Closing tag

#### Block elements

Block elements take the whole width of the container element and pushes down the it's sibling elements (line break). For example header elements like `h1` or`div`.

You can also change elements display properties in your style definitions.

#### Inline elements

Inline elements don't force a new line to begin after them. They can be inside a text paragraph for example. `span`, `a` and `img` are inline elements.

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

`<p class="center">This text will be centered</p>`

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

## Preprocessors

There are several so called CSS _preprocessors_ like SCSS (Sass) for example that have their own advanced styling syntax. SCSS brings features like variables, functions (mixins), inheritance, loops and nesting. This advanced styling definition syntax needs to be preprocessed to regular CSS. This needs to be taken into consideration in the development environment.

> A preprocessor is a program that processes its input data to produce output that is used as input to another program. [Wikipedia](https://en.wikipedia.org/wiki/Preprocessor)

# JavaScript

JavaScript (or just JS) language is based on ECMAScript standard for scripting languages. It can be used to add dynamic functionalities to a web page. JavaScript is also used in Node.js runtime environment in server side applications. JavaScript code can for example change the structure of a web page on the fly or get content from an API and render it to the page without need to refresh the page.

HTML can be embedded with scripts either from external file sources or inside a `<script>` and `</script>` tags.

> _JavaScript is an implementation of the ECMAScript standard._ [Michael Aranda](https://medium.freecodecamp.org/whats-the-difference-between-javascript-and-ecmascript-cba48c73a2b5)

## Type checking

JavaScript is a weakly (or loosely) typed language. It means that there is no type checking and when you declare a variable, you don't declare a type, just **let** (variable) or **const** (constant). You can assign whatever you want to that variable too later on.

https://toddmotto.com/understanding-javascript-types-and-reliable-type-checking/

You can add type checking to JavaScript with tools like TypeScript or Flow. They add their own syntax on top of JavaScript which you need to _transcompile_ to regular JavaScript. This needs to be taken into consideration in the development environment.

> A source-to-source compiler, transcompiler or transpiler is a type of compiler that takes the source code of a program written in one programming language as its input and produces the equivalent source code in another programming language [Wikipedia](https://en.wikipedia.org/wiki/Source-to-source_compiler)
