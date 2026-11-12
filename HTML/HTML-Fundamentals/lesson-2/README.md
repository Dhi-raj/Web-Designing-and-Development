# Lesson 2: HTML Document Structure and Anatomy

## 1. What is an HTML Document?

An HTML document is a text file containing HTML markup that defines the structure and content of a webpage.

HTML documents generally use the `.html` or `.htm` file extension.

Example:

```
index.html
about.html
contact.html
services.html
```

When a browser opens an HTML document, it parses the markup and constructs a DOM (Document Object Model), which represents the document as a tree of objects.

Important: An HTML document is not simply a collection of tags. It follows a defined document structure and content rules.

## 2. Standard HTML Document Structure

Let's look at a standard HTML5 document.

```
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My First Webpage</title>
</head>

<body>

    <h1>Welcome to HTML</h1>
    <p>This is my first webpage.</p>

</body>

</html>
```

[CS4640 - WebPL](https://images.openai.com/static-rsc-4/PYu8HDGK_j-0DquQ17iLYv_yYscMuozHR_kXSzHeES98QZ5wCMolyrdFHn59TFirLTvZr-U6zEy7Ae8kGAFZ2Abgmwx-PP4Ro1uXoO9K73cjtf8MGVNocvbA-UpXPOS_QMmpxIdQXRfy6fRXzWWTiqak0hFaYHJNf5gNFoEvApI?purpose=inline)

[cs.virginia.edu](https://www.cs.virginia.edu/~up3f/cs4640/supplement/html-css/?utm_source=chatgpt.com)

This document has four major parts:

1. DOCTYPE declaration
2. HTML root element
3. Head section
4. Body section

Let's understand each part in detail.

## 3. DOCTYPE Declaration

```
<!DOCTYPE html>
```

What is DOCTYPE?

DOCTYPE stands for Document Type Declaration. It tells the browser which document type and parsing mode to use.

In modern HTML, we write:

```
<!DOCTYPE html>
```

Why do we use it?

Historically, browsers supported different rendering modes to maintain compatibility with older websites.

The DOCTYPE declaration helps the browser use standards mode instead of quirks mode.

### Browser rendering modes

There are three important terms:

| Mode                | Description                                                              |
| ------------------- | ------------------------------------------------------------------------ |
| Standards Mode      | Browser follows modern web standards as closely as possible.             |
| Quirks Mode         | Browser emulates certain behaviours of older browsers for compatibility. |
| Limited Quirks Mode | An intermediate mode with some legacy compatibility behaviour.           |

The modern HTML DOCTYPE triggers standards mode.

Important points:

- DOCTYPE is a declaration, not an HTML element.
- It is not written inside the `<html>` element.
- It does not have a closing tag.
- It is case-insensitive in HTML syntax, although uppercase is conventional.
- Modern HTML uses the simple `<!DOCTYPE html>` declaration.

Interview question: Why do we use `<!DOCTYPE html>`?

Answer: It tells the browser to use standards mode when parsing and rendering the HTML document, avoiding legacy quirks-mode behaviour.

## 4. The HTML Root Element

```
<html lang="en">

    <!-- Document content -->

</html>
```

The `<html>` element is the root element of an HTML document.

All other HTML elements, except the DOCTYPE declaration, are descendants of this element.

It generally contains two major sections:

- `<head>`
- `<body>`

### Important attributes of the HTML element

The `<html>` element supports global attributes. Some particularly useful ones are:

| Attribute | Purpose                                         | Example        |
| --------- | ----------------------------------------------- | -------------- |
| `lang`    | Specifies the primary language of the document. | `lang="en"`    |
| `dir`     | Specifies text direction.                       | `dir="ltr"`    |
| `id`      | Gives the element a unique identifier.          | `id="root"`    |
| `class`   | Assigns one or more classes.                    | `class="page"` |

### Understanding the `lang` attribute

```
<html lang="en">
```

Here, `lang="en"` indicates that the document's primary language is English.

Other examples:

```
<html lang="hi">
<html lang="fr">
<html lang="es">
<html lang="en-US">
```

The language attribute is important for:

- Screen readers and assistive technologies.
- Search engines.
- Browser language-related processing.
- Correct pronunciation and interpretation of content.

Important: `lang` is a global HTML attribute, so it can also be used on individual elements when a portion of the document uses a different language.

Example:

```
<html lang="en">
<body>

    <p>Hello, welcome to my website.</p>

    <p lang="hi">नमस्ते, मेरी वेबसाइट में आपका स्वागत है।</p>

</body>
</html>
```

### Understanding the `dir` attribute

The `dir` attribute specifies the directionality of text.

It has three common values:

| Value  | Meaning                           |
| ------ | --------------------------------- |
| `ltr`  | Left to right                     |
| `rtl`  | Right to left                     |
| `auto` | Determine direction automatically |

Example:

```
<html lang="en" dir="ltr">
```

For languages such as Arabic and Hebrew, right-to-left text direction is commonly needed.

Developer tip: Use `dir="auto"` when the text direction is determined by user-generated content and is not known in advance.

## 5. The Head Element

```
<head>
    <!-- Metadata and resource information -->
</head>
```

The `<head>` element contains metadata and information about the HTML document.

Metadata means information that describes the document rather than the main content displayed on the webpage.

The browser uses this information for document identification, character encoding, responsive behaviour, resource loading and other purposes.

### What can we place inside `<head>`?

Some important elements include:

| Element      | Purpose                                                              |
| ------------ | -------------------------------------------------------------------- |
| `<title>`    | Defines the webpage title.                                           |
| `<meta>`     | Provides metadata.                                                   |
| `<link>`     | Connects external resources, such as CSS files and favicons.         |
| `<style>`    | Contains internal CSS.                                               |
| `<script>`   | Embeds or references JavaScript.                                     |
| `<base>`     | Defines the base URL for relative URLs.                              |
| `<noscript>` | Provides fallback content when scripting is unavailable or disabled. |

Example:

```
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>My Website</title>

    <link rel="stylesheet" href="style.css">

    <script src="script.js" defer></script>
</head>
```

We will study each of these elements separately in upcoming lessons.

Important: The `<head>` element is not the same as the `<header>` element.

- `<head>` contains document metadata and resource references.
- `<header>` represents introductory content or navigation for a page or section and normally belongs inside `<body>`.

This is a common interview question.

## 6. The Meta Element

```
<meta>
```

The `<meta>` element provides metadata about an HTML document.

It is a void element, which means it does not have a closing tag.

The `<meta>` element is commonly used for:

- Character encoding.
- Responsive viewport configuration.
- Page description.
- Author information.
- Search engine instructions.

Let's understand the important meta configurations.

### 6.1 Character Encoding: charset

```
<meta charset="UTF-8">
```

What is character encoding?

Character encoding defines how characters are represented as bytes so that computers can store, transmit and interpret text.

UTF-8 is a Unicode encoding that supports characters from many writing systems, including English, Hindi and numerous other languages.

Example:

```
<meta charset="UTF-8">
```

This allows the browser to interpret the document using UTF-8 encoding.

Without correct character encoding, some characters may appear incorrectly (often called mojibake).

Why should charset be declared early?

The browser needs to know the character encoding before interpreting the document's text correctly.

For HTML documents, the UTF-8 declaration should appear within the first 1024 bytes of the document.

Interview question: What is UTF-8?

UTF-8 is a variable-length Unicode character encoding that represents Unicode characters using one to four bytes.

### 6.2 Viewport Meta Tag

```
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

This is important for responsive web development.

What is a viewport?

A viewport is the visible area of a webpage inside a browser window.

Different devices have different viewport dimensions.

For example:

- Desktop: Generally wider viewport.
- Tablet: Medium-sized viewport.
- Mobile: Generally narrower viewport.

Understanding its attributes:

| Property             | Meaning                                             |
| -------------------- | --------------------------------------------------- |
| `name="viewport"`    | Identifies the viewport configuration.              |
| `width=device-width` | Sets the layout viewport width to the device width. |
| `initial-scale=1.0`  | Sets the initial zoom level to 100%.                |

Example:

```
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

Why is it important?

Without a proper viewport declaration, mobile browsers may use a wider virtual layout viewport, making the page appear zoomed out or poorly scaled.

We will explore responsive design in detail when we start CSS.

### 6.3 Meta Description

```
<meta name="description" content="Learn HTML from basic to advanced with practical examples.">
```

The description provides a short summary of the webpage.

Search engines may use this description as the snippet displayed in search results.

Important points:

- Write a meaningful description.
- Keep it relevant to the actual page content.
- Avoid keyword stuffing.
- Search engines are not required to display your description.

### 6.4 Meta Author

```
<meta name="author" content="Your Name">
```

Specifies the author of the document.

Example:

```
<meta name="author" content="Web Development Learner">
```

### 6.5 Meta Robots

```
<meta name="robots" content="index, follow">
```

Provides instructions to search engine crawlers.

| Value      | Meaning                                  |
| ---------- | ---------------------------------------- |
| `index`    | Allows indexing of the page.             |
| `noindex`  | Requests that the page not be indexed.   |
| `follow`   | Allows links on the page to be followed. |
| `nofollow` | Requests that links not be followed.     |

Example:

```
<meta name="robots" content="noindex, nofollow">
```

Important: Meta robots directives are crawler instructions, not security controls. They cannot protect private content.

Also, `index, follow` is generally the default behaviour for indexable pages, so it does not need to be explicitly declared in every document.

## 7. The Title Element

```
<title>My Website</title>
```

The `<title>` element defines the title of the HTML document.

It is placed inside `<head>`.

The title can appear in:

- The browser tab.
- Browser bookmarks.
- Search engine result titles (search engines may choose another title).
- Browser history and other browser interfaces.

Example:

```
<head>
    <title>Complete HTML Learning</title>
</head>
```

[❤ 💻 How to set web browser tab name? - Dirask](https://images.openai.com/static-rsc-4/-IXYW0ZGBs4k_8zM69Ei7t3skh_evAn1eCUwYpSr2hG3dVjeOW3J20eXzRrk1Usn12F34A7IqUUFVCEPz9dC_owImdgXYe91o09x7ZN5R1Kc6VNzt3gp1GntJvgD3HFMZAVqgFJLes9nWzA8eRB7vK5uJtCcSewsgHgcqb8AVsA?purpose=inline)

[dirask.com](https://dirask.com/questions/How-to-set-web-browser-tab-name-Dn4mqj?utm_source=chatgpt.com)

### Best practices for title

1. Every webpage should have a meaningful title.
2. Each page should have a title that describes its own content.
3. Avoid unnecessarily long or repetitive titles.
4. Place important identifying words naturally near the beginning.

Example:

```
<title>HTML Forms - Complete HTML Learning</title>
```

Interview question: What is the difference between `<title>` and `<h1>`?

| `<title>`                                      | `<h1>`                                             |
| ---------------------------------------------- | -------------------------------------------------- |
| Defines the document title.                    | Defines a top-level heading in the content.        |
| Placed inside `<head>`.                        | Placed inside `<body>`.                            |
| Usually appears in the browser tab.            | Appears as webpage content.                        |
| Important for document identification and SEO. | Important for content structure and accessibility. |

## 8. The Body Element

```
<body>
    <!-- Visible webpage content -->
</body>
```

The `<body>` element contains the main content of an HTML document.

It includes elements such as:

- Headings and paragraphs.
- Images and videos.
- Links.
- Lists and tables.
- Forms.
- Semantic structural elements.
- Other embedded content.

Example:

```
<body>

    <h1>Welcome to My Website</h1>

    <p>This website is created using HTML.</p>

    <a href="https://example.com">Visit Example</a>

</body>
```

### Important attributes of body

The `<body>` element supports global attributes.

Some legacy presentation attributes, such as `bgcolor`, `background`, `text`, `link`, `vlink` and `alink`, are obsolete. Use CSS for presentation instead.

For example, rather than:

```
<body bgcolor="yellow">
```

We will eventually use CSS:

```
body {
    background-color: yellow;
}
```

Professional practice: Keep the body focused on document content. Avoid obsolete presentation attributes.

## 9. Complete Relationship Between HTML Elements

Let's understand how the elements are related.

```
HTML Document
│
├── DOCTYPE Declaration
│
└── html (Root Element)
    │
    ├── head
    │   ├── meta
    │   ├── title
    │   ├── link
    │   └── script
    │
    └── body
        ├── h1
        ├── p
        ├── a
        ├── img
        └── form
```

This is a simplified structural representation.

Remember:

- `html` is the root element.
- `head` and `body` are its primary structural children in a typical document.
- Metadata and resource declarations generally belong inside `head`.
- Main page content belongs inside `body`.

## 10. Global Attributes vs Element-Specific Attributes

This is an important topic for understanding HTML attributes.

### Global attributes

Global attributes can be specified on all HTML elements, subject to their individual applicability and semantics.

Important global attributes include:

| Attribute         | Purpose                                                           |
| ----------------- | ----------------------------------------------------------------- |
| `id`              | Unique identifier within the document.                            |
| `class`           | Assigns one or more classes.                                      |
| `style`           | Provides inline CSS declarations.                                 |
| `title`           | Provides advisory information, often exposed as a tooltip.        |
| `lang`            | Specifies the language of an element's content.                   |
| `dir`             | Specifies text directionality.                                    |
| `hidden`          | Indicates that an element is not currently relevant for display.  |
| `tabindex`        | Controls sequential focus navigation and focusability.            |
| `accesskey`       | Suggests a keyboard shortcut for an element.                      |
| `contenteditable` | Indicates whether an element's content can be edited by the user. |
| `draggable`       | Indicates whether an element can be dragged.                      |
| `spellcheck`      | Specifies whether spelling and grammar checking may be performed. |
| `translate`       | Indicates whether an element's text should be translated.         |
| `data-*`          | Stores custom data associated with an element.                    |
| `autocapitalize`  | Provides a hint for automatic capitalization of user input.       |
| `inputmode`       | Provides a hint about the virtual keyboard to display.            |

We will study these attributes in a dedicated chapter.

### Element-specific attributes

These attributes are intended for particular elements.

Examples:

| Element  | Attribute | Purpose                                 |
| -------- | --------- | --------------------------------------- |
| `a`      | `href`    | Specifies the link destination.         |
| `img`    | `src`     | Specifies the image resource.           |
| `img`    | `alt`     | Provides alternative text.              |
| `form`   | `action`  | Specifies where form data is submitted. |
| `input`  | `type`    | Specifies the input control type.       |
| `script` | `src`     | Specifies an external script resource.  |
| `meta`   | `charset` | Specifies character encoding.           |

Important distinction: An attribute being syntactically permitted on an element does not mean it has a meaningful effect there. Always follow the HTML specification for that element.

## 11. HTML Comments

HTML comments allow developers to write notes inside the source code.

Syntax:

```
<!-- This is an HTML comment -->
```

Example:

```
<body>

    <!-- Main heading -->
    <h1>My Website</h1>

    <!-- Introduction paragraph -->
    <p>Welcome to my website.</p>

</body>
```

### Uses of comments

- Explaining code.
- Separating logical sections.
- Leaving development notes.
- Temporarily excluding markup during debugging.

### Important rules

1. Comments begin with `<!--`.
2. Comments end with `-->`.
3. Comments are not displayed as normal webpage content.
4. Comments can be viewed in the page source.
5. Do not store passwords, secret keys or confidential information in comments.
6. Avoid using `--` inside comment content because it is not allowed by HTML comment syntax.

Example of an incorrect comment:

```
<!-- This -- is not valid comment content -->
```

Interview question: Are HTML comments visible to users?

They are not displayed as ordinary webpage content, but users can inspect the HTML source or DOM and read them.

## 12. HTML Whitespace Handling

Whitespace includes spaces, tabs and line breaks.

Consider:

```
<p>Hello World</p>
```

And:

```
<p>
    Hello
    World
</p>
```

In normal HTML text rendering, consecutive spaces and line breaks are generally collapsed into a single space.

Both examples normally display:

```
Hello World
```

### Important points

- Multiple consecutive spaces are generally collapsed.
- Line breaks in HTML source do not necessarily create visible line breaks.
- Indentation improves source-code readability.
- CSS controls visual spacing and layout.
- The `<pre>` element preserves whitespace formatting in its content, subject to HTML parsing rules.

Example:

```
<pre>
Name: Adhiraj
Course: HTML
Status: Learning
</pre>
```

We will explore whitespace and text formatting further in the elements chapter.

## 13. Optional HTML Tags and Browser Error Recovery

This is an important advanced concept that many beginner tutorials ignore.

Some HTML tags are technically optional under specific conditions.

For example, in certain valid HTML documents, the browser can infer omitted `html`, `head`, `body`, or some closing tags.

Consider:

```
<!DOCTYPE html>
<title>My Page</title>
<h1>Hello World</h1>
<p>Welcome to HTML.
```

A browser can parse this and construct a document with the necessary structural elements.

However, this does not mean we should write HTML this way.

Professional practice: Explicitly write the document structure and closing tags wherever required. It makes your code readable, maintainable and easier to debug.

### How does browser error recovery work?

Browsers are designed to handle imperfect HTML.

For example:

```
<p>First paragraph
<p>Second paragraph
```

A browser can automatically close the first paragraph when it encounters the second paragraph start tag.

This is part of HTML's defined parsing and error-recovery behaviour.

Another example:

```
<table>
    <tr>
        <td>Hello</td>
    </tr>
</table>
```

The browser's HTML parser can insert an implicit `<tbody>` element around the table row.

The resulting DOM may contain:

```
<table>
    <tbody>
        <tr>
            <td>Hello</td>
        </tr>
    </tbody>
</table>
```

Important distinction: The original HTML source and the resulting DOM are not always identical.

We will study HTML parsing algorithms in the advanced browser internals chapter.

## 14. HTML Syntax Rules and Important Conventions

HTML has defined syntax rules. Understanding these rules prevents common coding errors.

### 14.1 Case sensitivity

HTML tag and attribute names are ASCII case-insensitive.

These are equivalent in HTML:

```
<h1>Hello</h1>
```

```
<H1>Hello</H1>
```

However, professional developers generally use lowercase.

Recommended:

```
<html lang="en">
<head>
    <title>My Website</title>
</head>
</html>
```

### 14.2 Quotation marks in attributes

Attribute values containing spaces should be quoted.

Recommended:

```
<p class="main content">Hello</p>
```

Unquoted attribute values are permitted in certain circumstances, but quoted values are the professional convention.

Both single and double quotes can be used:

```
<p class="intro">Hello</p>
```

```
<p class='intro'>Hello</p>
```

Use one consistent style throughout your project.

### 14.3 Proper nesting

Elements must be nested correctly.

Correct:

```
<p>
    This is <strong>important</strong> information.
</p>
```

Incorrect:

```
<p>
    This is <strong>important</p>
</strong>
```

Incorrect nesting can produce unexpected DOM structures and browser behaviour.

### 14.4 Closing tags

Most HTML elements have opening and closing tags.

Example:

```
<p>Hello World</p>
```

Some elements are void elements and cannot have closing tags.

Examples:

```
<img src="photo.jpg" alt="A photograph">
<br>
<hr>
<input type="text">
<meta charset="UTF-8">
<link rel="stylesheet" href="style.css">
```

We will study void elements separately.

### 14.5 HTML entities

Some characters have special meanings in HTML syntax.

For example, the less-than sign can begin a tag.

To display special characters as text, use character references:

| Character | Entity    |
| --------- | --------- |
| `<`       | `&lt;`    |
| `>`       | `&gt;`    |
| `&`       | `&amp;`   |
| `"`       | `&quot;`  |
| `'`       | `&apos;`  |
| `©`       | `&copy;`  |
| `®`       | `&reg;`   |
| `₹`       | `&#8377;` |

Example:

```
<p>5 &lt; 10</p>
<p>HTML &amp; CSS</p>
<p>Copyright &copy; 2026</p>
```

We will cover named and numeric character references in detail in the text and formatting chapter.

## 15. Common Mistakes Developers Should Avoid

| Mistake                                  | Correct approach                                      |
| ---------------------------------------- | ----------------------------------------------------- |
| Forgetting the DOCTYPE                   | Start with `<!DOCTYPE html>`.                         |
| Missing `lang`                           | Specify the document language.                        |
| Missing character encoding               | Declare UTF-8 early.                                  |
| Missing viewport configuration           | Include the viewport meta element.                    |
| Putting visible content in `head`        | Place normal webpage content in `body`.               |
| Using multiple document titles           | Use one meaningful `<title>` per document.            |
| Using incorrect nesting                  | Maintain proper parent-child structure.               |
| Using obsolete presentation attributes   | Use CSS for presentation.                             |
| Adding sensitive information in comments | Never expose confidential information in source code. |
| Using meaningless page titles            | Describe each page accurately.                        |

## 16. Complete Professional HTML Boilerplate

Now let's combine what we have learned into a practical document template.

This is a good starting point for most ordinary HTML pages.

```

<!DOCTYPE html>
<html lang="en">

<head>
    <!-- Character encoding -->
    <meta charset="UTF-8">

    <!-- Responsive viewport -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <!-- Page information -->
    <title>Complete HTML Learning</title>
    <meta name="description" content="Learn HTML from basic to advanced with practical examples.">
    <meta name="author" content="Your Name">

    <!-- Website icon -->
    <link rel="icon" href="favicon.ico">

    <!-- External CSS -->
    <link rel="stylesheet" href="style.css">

    <!-- External JavaScript -->
    <script src="script.js" defer></script>
</head>

<body>

    <!-- Main webpage content -->
    <h1>Welcome to HTML</h1>

    <p>
        I am learning HTML from basic to advanced.
    </p>

</body>

</html>

```

Notice that we have also included a favicon, CSS and JavaScript references. These are useful in a practical project, although they are not all mandatory for every HTML document.

## 17. HTML Validation and Debugging

Professional developers should validate their HTML rather than assuming that code is correct just because it appears correctly in a browser.

### What is HTML validation?

HTML validation is the process of checking an HTML document against the HTML specification to identify markup errors and potential problems.

Our recommended tool:

[Assignment: Building a Simple HTML Page](https://images.openai.com/static-rsc-4/L6iOszcnAIkx-eOOYR3cDQV46HPPK3mLk17e7kW-juDpeXskT1HDvOX8yiaN1bTaeg8OEdv3DwNcwT2E6O_6Por_hSo2d9REt96aro2TsR_CP_x9mzxD-el3GC5FNYSTkdmtIn-3S7AFsFETj8fyCKuruolXiQ8VZ3hlyaEJ5ao?purpose=inline)

Nu HTML Checker

Checks HTML markup and reports errors and warnings.

[Open HTML Validator](https://validator.w3.org/nu/?utm_source=chatgpt.com)

Other useful debugging tools:

- Chrome DevTools → Inspect elements and DOM.
- View Page Source → Inspect original HTML source.
- Console → Identify JavaScript errors.
- Elements panel → Inspect the browser's current DOM.

Important: A webpage rendering successfully does not guarantee that its HTML is valid.

## 18. Interview-Level Knowledge

These questions are integrated into the concepts above. Here are some additional questions to test your understanding.

Q1. Is `<!DOCTYPE html>` an HTML element?

No. It is a document type declaration that instructs the browser to use standards mode.

Q2. What is the difference between `<head>` and `<header>`?

`<head>` contains metadata and resource information. `<header>` represents introductory content or navigation within the webpage.

Q3. Can an HTML document work without `<html>`, `<head>` and `<body>` tags?

Yes. HTML parsing rules allow browsers to infer certain omitted tags. However, explicitly including them is recommended for maintainability.

Q4. Is `<meta>` a void element?

Yes. It does not have a closing tag.

Q5. Why is UTF-8 preferred?

It supports Unicode characters from a wide range of languages and writing systems.

Q6. What happens if we omit the viewport meta tag?

Mobile browsers may use a wider layout viewport, causing the page to appear zoomed out or incorrectly scaled.

Q7. What is the difference between HTML source and DOM?

HTML source is the original markup. DOM is the browser's parsed object representation, which may differ because of parsing, error recovery and JavaScript modifications.

Q8. Does HTML support case-sensitive tag names?

No. HTML tag and attribute names are ASCII case-insensitive, although lowercase is the recommended convention.

Q9. Can we place CSS and JavaScript inside the HTML document?

Yes. CSS can be written using `<style>` and JavaScript using `<script>`. They can also be loaded from external files.

Q10. What is quirks mode?

It is a legacy browser rendering mode that emulates certain older browser behaviours to support outdated webpages.

## 19. Practical Exercises

Do these exercises yourself. They will help you understand the document structure instead of simply memorizing it.

Exercise 1: Create an HTML document

Create `index.html` with:

- DOCTYPE declaration.
- HTML root element.
- English language declaration.
- Character encoding.
- Viewport configuration.
- Meaningful title.
- Body containing a heading and two paragraphs.

Exercise 2: Meta elements

Add the following metadata to your document:

- Description.
- Author.
- UTF-8 encoding.
- Viewport configuration.

Exercise 3: HTML attributes

Create examples using:

- `lang`
- `dir`
- `id`
- `class`
- `title`
- `hidden`
- `contenteditable`
- `data-*`

Exercise 4: Browser investigation

1. Open your HTML document in Chrome.
2. Right-click and select Inspect.
3. Open the Elements panel.
4. Observe the `html`, `head` and `body` elements.
5. Compare the DOM with your original source code.
6. Experiment with changing an element's content using DevTools.

Exercise 5: Error recovery

Write an HTML document with an omitted closing paragraph tag and inspect how the browser constructs the DOM.
