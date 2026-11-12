# Lesson 3: HTML Elements, Tags, Attributes and Content Models

## 1. HTML Tag vs Element vs Attribute

These three terms are related, but they do not mean the same thing.

### HTML Tag

A tag is the markup syntax written inside angle brackets (`< >`) that identifies an HTML element.

Example:

```
<p>Hello World</p>
```

Here:

- `<p>` is the opening tag.
- `</p>` is the closing tag.

### HTML Element

An element consists of the opening tag, its content, and usually a closing tag.

```
<p>Hello World</p>
```

The complete structure above is a paragraph element.

An element can also contain other elements:

```
<p>This is <strong>important</strong> information.</p>
```

Here, the `p` element contains a `strong` element.

### HTML Attribute

An attribute provides additional information or configuration to an HTML element.

```
<a href="https://developer.mozilla.org/">Visit MDN</a>
```

Here:

- `a` is the element.
- `href` is the attribute.
- `https://developer.mozilla.org/` is the attribute value.
- `Visit MDN` is the visible content.

Attributes are generally written inside the opening tag.

Important: Not every element uses the same attributes. Some attributes are global and can be used on almost any HTML element, while others are specific to particular elements.

## 2. Types of HTML Elements

HTML elements can be classified according to how they are written and how they behave in the document.

### 2.1 Normal (Paired) Elements

Most HTML elements have an opening tag and a closing tag, with content between them.

```
<h1>HTML Learning</h1>
<p>Learning HTML step by step.</p>
<div>
    <p>This paragraph is inside a div.</p>
</div>
```

These are often called paired elements.

### 2.2 Void Elements

Void elements cannot contain child elements or text content, and they do not have closing tags.

Examples:

```
<br>
<hr>
<img src="photo.jpg" alt="A mountain">
<input type="text">
<meta charset="UTF-8">
<link rel="stylesheet" href="style.css">
```

Common void elements:

| Element    | Purpose                                  |
| ---------- | ---------------------------------------- |
| `<area>`   | Defines an area inside an image map      |
| `<base>`   | Specifies the base URL for relative URLs |
| `<br>`     | Creates a line break                     |
| `<col>`    | Specifies column properties in a table   |
| `<embed>`  | Embeds external content                  |
| `<hr>`     | Represents a thematic break              |
| `<img>`    | Embeds an image                          |
| `<input>`  | Creates a form input                     |
| `<link>`   | Links external resources                 |
| `<meta>`   | Provides document metadata               |
| `<source>` | Specifies media sources                  |
| `<track>`  | Provides text tracks for media           |
| `<wbr>`    | Specifies a possible line-break position |

Important: Do not write `</img>` or `</br>`. These are not valid HTML closing tags for void elements.

Also, writing `<img />` is permitted in HTML, but the slash does not make it a self-closing element. HTML void elements simply do not require closing tags.

## 3. Nesting of HTML Elements

Nesting means placing one HTML element inside another.

```
<div>
    <h1>Welcome</h1>
    <p>This is a <strong>nested</strong> element example.</p>
</div>
```

Here:

- `div` is the parent of `h1` and `p`.
- `h1` and `p` are children of `div`.
- `strong` is a child of `p`.

HTML element hierarchy

div — Parent

h1 — Child

p — Child

strong — Nested child

### Parent, Child and Sibling

- Parent: An element that directly contains another element.
- Child: An element directly contained inside another element.
- Sibling: Elements that share the same direct parent.
- Descendant: Any element contained inside another element, including children, grandchildren and deeper nested elements.
- Ancestor: Any element that contains another element, directly or indirectly.

Example:

```
<div>
    <section>
        <h2>Introduction</h2>
        <p>HTML is a markup language.</p>
    </section>
</div>
```

In this example:

- `div` is the parent of `section`.
- `section` is the parent of `h2` and `p`.
- `h2` and `p` are siblings.
- `h2` is a descendant of `div`.
- `div` is an ancestor of `p`.

These relationships are important when working with CSS selectors and JavaScript DOM manipulation.

## 4. Correct and Incorrect Nesting

HTML elements should be nested according to their content rules.

Correct nesting:

```
<p>This is <strong>important text</strong>.</p>
```

Incorrect nesting:

```
<p>This is <strong>important text.</p></strong>
```

The tags must be closed in the reverse order in which they were opened.

Think of it as a stack:

1. Open `p`.
2. Open `strong`.
3. Close `strong`.
4. Close `p`.

Incorrect nesting can cause browsers to repair the HTML automatically, potentially producing an unexpected DOM structure.

## 5. Block-Level and Inline Behaviour

This is an important concept, especially before learning CSS.

HTML elements are often informally described as block-level or inline elements. However, technically, block and inline describe CSS display behaviour, not the fundamental HTML content categories.

### 5.1 Block-Level Behaviour

An element with `display: block` normally starts on a new line and occupies the available width of its containing block by default.

Examples of elements commonly displayed as block:

- `<div>`
- `<p>`
- `<h1>` to `<h6>`
- `<section>`
- `<article>`
- `<header>`
- `<footer>`

Example:

```
<h1>First Heading</h1>
<p>First paragraph.</p>
<p>Second paragraph.</p>
```

Each normally appears on a separate line.

### 5.2 Inline Behaviour

An element with `display: inline` normally flows within the surrounding text and occupies only the space required by its content.

Examples commonly displayed inline:

- `<span>`
- `<a>`
- `<strong>`
- `<em>`
- `<code>`

Example:

```
<p>
    Learn <strong>HTML</strong> and
    <a href="https://developer.mozilla.org/">CSS</a>.
</p>
```

The `strong` and `a` elements appear within the same text flow.

### 5.3 Block vs Inline

| Feature          | Block                                       | Inline                                                 |
| ---------------- | ------------------------------------------- | ------------------------------------------------------ |
| New line         | Normally starts on a new line               | Normally stays in the same line                        |
| Width            | Default is available containing-block width | Based on content                                       |
| Height and width | Generally applicable                        | Generally do not affect the inline box in the same way |
| Example          | `div`, `p`                                  | `span`, `a`                                            |

Important CSS connection: CSS can change an element's display behaviour.

```
<span style="display: block;">This behaves like a block.</span>

<div style="display: inline;">This behaves like inline.</div>
```

The HTML element remains a `span` or `div`; only its CSS display behaviour changes.

## 6. HTML Content Models

Content models define what type of content an HTML element is allowed to contain.

This is more fundamental than simply classifying elements as block or inline.

For example, a paragraph can contain text and phrasing elements, but it cannot contain another paragraph or a `div`.

### Common HTML Content Categories

| Category            | Meaning                                                              | Examples                                |
| ------------------- | -------------------------------------------------------------------- | --------------------------------------- |
| Metadata content    | Provides information about the document or controls its presentation | `title`, `meta`, `link`, `style`        |
| Flow content        | General content used in the body                                     | `div`, `p`, `section`, `article`        |
| Sectioning content  | Defines sections of a document                                       | `article`, `section`, `nav`, `aside`    |
| Heading content     | Defines headings                                                     | `h1`–`h6`, `hgroup`                     |
| Phrasing content    | Text and text-level markup                                           | `span`, `strong`, `em`, `a`             |
| Embedded content    | Includes external resources or media                                 | `img`, `video`, `audio`, `iframe`       |
| Interactive content | Elements designed for user interaction                               | `button`, `input`, `select`, `textarea` |

Some elements belong to multiple categories. For example, `a` is phrasing content and can also be interactive depending on its attributes.

### Example: Paragraph Content Model

A paragraph (`p`) accepts phrasing content.

Valid:

```
<p>
    This is <strong>important</strong> and
    <em>emphasized</em> text.
</p>
```

Invalid:

```
<p>
    This is a paragraph.
    <div>This is a div.</div>
</p>
```

A `div` is not allowed inside a `p` element. When the browser encounters such markup, it may implicitly close the paragraph before processing the `div`.

This is why understanding content models matters: browsers may repair invalid HTML, but the resulting DOM might not match your intended structure.

## 7. Global Attributes

Global attributes can be used on all HTML elements, although their usefulness depends on the element and context.

### 7.1 `id`

The `id` attribute assigns a unique identifier to an element within a document.

```
<h1 id="main-heading">Welcome to HTML</h1>
```

Uses:

- Targeting an element with CSS.
- Accessing an element with JavaScript.
- Linking to a specific section using a fragment URL.

Example:

```
<a href="#about">Go to About</a>

<h2 id="about">About Us</h2>
```

Important: An `id` should be unique within the document. Do not assign the same ID to multiple elements.

### 7.2 `class`

The `class` attribute assigns one or more class names to an element.

```
<p class="important">First paragraph.</p>
<p class="important">Second paragraph.</p>
```

Multiple classes can be assigned using spaces:

```
<p class="important highlighted">Important information.</p>
```

Unlike `id`, the same class can be used on multiple elements.

### 7.3 `style`

The `style` attribute applies inline CSS to an element.

```
<p style="color: blue; font-size: 18px;">
    Learning HTML.
</p>
```

It is useful for quick demonstrations, but professional projects generally keep styling in separate CSS files or appropriate style blocks.

### 7.4 `title`

The `title` attribute provides advisory information about an element.

```
<p title="This is additional information">
    Move your pointer over this text.
</p>
```

Browsers commonly display this information as a tooltip on pointer hover. However, it is not a reliable replacement for visible instructions or accessible labels.

### 7.5 `lang`

The `lang` attribute specifies the language of an element's content.

```
<p lang="en">This is English.</p>

<p lang="hi">यह हिंदी है।</p>
```

It helps browsers and assistive technologies determine how to process the text.

### 7.6 `dir`

The `dir` attribute specifies the direction of text.

```
<p dir="ltr">Left to right text.</p>

<p dir="rtl">Right to left text.</p>
```

Common values:

- `ltr`: Left to right.
- `rtl`: Right to left.
- `auto`: Determines direction based on the text.

### 7.7 `hidden`

The `hidden` attribute indicates that an element is not currently relevant and should not be presented.

```
<p hidden>This paragraph is hidden.</p>
```

The browser normally does not display the element. JavaScript can remove or change the attribute when the content needs to be shown.

### 7.8 `tabindex`

The `tabindex` attribute controls whether an element can receive keyboard focus and, where applicable, its position in sequential keyboard navigation.

```
<button tabindex="0">Normal keyboard focus</button>

<div tabindex="0">Focusable div</div>

<div tabindex="-1">Programmatically focusable</div>
```

Common values:

- `0`: Allows an element to participate in the normal keyboard focus order.
- `-1`: Allows programmatic focus but excludes it from sequential keyboard navigation.
- Positive values: Assign an explicit focus order. Generally avoid these because they can create confusing keyboard navigation.

### 7.9 `contenteditable`

Makes an element's content editable by the user.

```
<p contenteditable="true">
    You can edit this text in the browser.
</p>
```

This does not automatically save the changes to a database or file.

### 7.10 `draggable`

Specifies whether an element can be dragged using the browser's drag-and-drop functionality.

```
<p draggable="true">Try dragging this text.</p>
```

It commonly uses `true` or `false`. A complete drag-and-drop application also requires JavaScript event handling.

## 8. Boolean Attributes

Boolean attributes represent true or false states.

For a Boolean attribute, its presence means true, and its absence means false.

Example:

```
<input type="text" required>
```

The input is required because `required` is present.

These are also valid:

```
<input type="text" required="">

<input type="text" required="required">
```

But this is a common mistake:

```
<input type="text" required="false">
```

This still means `required` is true because the attribute is present.

Common Boolean attributes include:

| Attribute   | Purpose                                                    |
| ----------- | ---------------------------------------------------------- |
| `required`  | Makes a form control mandatory                             |
| `disabled`  | Disables a form control                                    |
| `readonly`  | Prevents editing of a form control                         |
| `checked`   | Checks a checkbox or radio button by default               |
| `selected`  | Selects an option by default                               |
| `multiple`  | Allows multiple values or selections where supported       |
| `autofocus` | Requests automatic focus when the page loads               |
| `hidden`    | Indicates that an element is not currently relevant        |
| `controls`  | Displays media controls                                    |
| `loop`      | Repeats media playback                                     |
| `muted`     | Starts media in a muted state                              |
| `open`      | Shows the content of certain disclosure or dialog elements |

Interview concept: Why does `required="false"` still enable required validation?

Because HTML Boolean attributes are controlled by their presence, not by the text written as their value.

## 9. Custom Data Attributes (`data-*`)

Custom data attributes allow developers to store extra information on HTML elements without creating non-standard attributes.

They must begin with `data-`.

```
<button data-product-id="101" data-category="electronics">
    View Product
</button>
```

JavaScript can access these attributes using the `dataset` property:

```
<script>
    const button = document.querySelector("button");

    console.log(button.dataset.productId);
    console.log(button.dataset.category);
</script>
```

Output:

```
101
electronics
```

The hyphenated attribute name is converted to camelCase in `dataset`.

For example:

- `data-product-id` → `dataset.productId`
- `data-user-name` → `dataset.userName`

Important: Data attributes are not a secure place to store passwords, secret keys, or sensitive information. Users can inspect them in the browser.

## 10. Attribute Syntax and Values

Attributes are generally written as:

```
<element attribute="value">Content</element>
```

Example:

```
<a href="https://example.com" target="_blank">
    Visit Website
</a>
```

### Quoted vs Unquoted Values

Quoted values are recommended.

```
<input type="text" placeholder="Enter your name">
```

Unquoted values are allowed in some cases:

```
<input type=text>
```

But values containing spaces or certain special characters must be quoted.

### Multiple Attributes

An element can have multiple attributes.

```
<img
    src="photo.jpg"
    alt="Mountain landscape"
    width="500"
    height="300"
    loading="lazy"
>
```

Attribute order generally does not affect HTML behaviour.

### Duplicate Attributes

Avoid duplicate attributes.

```
<!-- Incorrect -->
<input type="text" type="email">
```

An HTML element should not contain duplicate attribute names. Browsers may ignore later duplicates during parsing.

## 11. Common HTML Mistakes

| Mistake                                          | Correct approach                                    |
| ------------------------------------------------ | --------------------------------------------------- |
| Using closing tags for void elements             | Write `<br>` and `<img>` without closing tags       |
| Incorrect nesting                                | Close inner elements before outer elements          |
| Reusing the same `id`                            | Use unique IDs                                      |
| Using `required="false"`                         | Remove `required` to make it false                  |
| Putting a `div` inside a `p`                     | Use a suitable container such as `div` or `section` |
| Using HTML for visual styling                    | Use CSS                                             |
| Treating block/inline as permanent element types | Understand CSS `display` behaviour                  |
| Storing secrets in `data-*`                      | Keep sensitive data on secure server-side systems   |

## 12. Practical Example

Create the following file in your existing repository:

`HTML/HTML-Fundamentals/lesson-3/index.html`

```
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HTML Elements and Attributes</title>
</head>

<body>

    <div id="main-container" class="container">

        <h1 title="Main heading">HTML Elements and Attributes</h1>

        <p>
            HTML elements define the structure of a webpage.
            <strong>Attributes</strong> provide additional information.
        </p>

        <section id="about">

            <h2>About HTML</h2>

            <p>
                HTML is a <span class="highlight">markup language</span>
                used to structure web content.
            </p>

            <a href="https://developer.mozilla.org/"
               target="_blank"
               rel="noopener noreferrer">
                Learn HTML on MDN
            </a>

        </section>

        <section id="user-form">

            <h2>User Information</h2>

            <form>

                <label for="username">Username:</label>

                <input
                    type="text"
                    id="username"
                    name="username"
                    placeholder="Enter username"
                    required
                >

                <button type="submit">Submit</button>

            </form>

        </section>

        <p data-topic="html" data-level="beginner">
            Practising custom data attributes.
        </p>

        <hr>

        <footer>
            <p>HTML Learning Practice</p>
        </footer>

    </div>

</body>
</html>
```

Study this example and identify:

1. All paired elements.
2. All attributes and their values.
3. All parent-child relationships.
4. All global attributes.
5. The form's Boolean attribute.
6. The void elements.

## 13. Practice Exercises

Complete these exercises before moving to Lesson 4.

Exercise 1 — Basic elements

Create a webpage containing:

- One `h1` heading.
- Two paragraphs.
- One `strong` element.
- One `em` element.
- One `hr` and one `br`.

Exercise 2 — Nesting

Create this structure:

```
div
 ├── h1
 ├── section
 │    ├── h2
 │    └── p
 │         └── strong
 └── footer
      └── p
```

Exercise 3 — Attributes

Create a webpage using:

- `id`
- `class`
- `title`
- `lang`
- `dir`
- `hidden`
- `tabindex`
- `contenteditable`
- `data-*`

Exercise 4 — Boolean attributes

Create a form containing:

- A required input.
- A disabled input.
- A readonly input.
- A checked checkbox.

Observe how each behaves in the browser.
