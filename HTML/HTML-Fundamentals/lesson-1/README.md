# Lesson 1: Introduction to HTML

Welcome to Lesson 1. We are starting our HTML journey from the fundamentals, but our goal is to develop a professional understanding of HTML.

By the end of this lesson, you should understand what HTML is, why it is needed, how browsers process HTML, and how HTML works with CSS and JavaScript.

## 1. What is HTML?

HTML stands for HyperText Markup Language.

HTML is the standard markup language used to create and structure content on web pages. It tells the web browser what different parts of a webpage represent, such as headings, paragraphs, images, links, tables and forms.

Let's understand the three words.

1\. HyperText

HyperText refers to text that contains links (hyperlinks) connecting one document or resource to another.

For example, when you click a link on a webpage and navigate to another webpage, you are using HyperText.

2\. Markup

Markup means using special elements (tags) to define and organize content.

For example:

```
<h1>Welcome to HTML</h1>
<p>HTML is a markup language.</p>
```

Here:

- `<h1>` identifies a main heading.
- `<p>` identifies a paragraph.

These tags tell the browser how to interpret the content.

3\. Language

HTML is called a language because it follows a defined set of syntax rules and specifications that browsers understand.

However, HTML is not a programming language because it does not provide general-purpose programming logic such as loops, conditions and functions.

## 2. Why do we use HTML?

A browser needs instructions to understand the structure and meaning of webpage content.

Consider a webpage containing:

- A heading
- Some paragraphs
- An image
- Navigation links
- A registration form

Without HTML, the browser would not have the structured document that identifies these different content types.

HTML provides that structure.

For example:

```
<h1>My Website</h1>

<p>Welcome to my website.</p>

<a href="about.html">About Us</a>
```

The browser interprets these elements and constructs the webpage accordingly.

Important: HTML defines the structure and meaning of content. CSS controls its visual presentation, while JavaScript adds behaviour and interactivity.

## 3. How does a website work?

A website generally involves three important technologies.

## The three pillars of web development

[HTML5 Logo PNG - Free Download and Icon for Websites](https://images.openai.com/static-rsc-4/Zrq_nz8vIJdCn4ob5URDN4R9vhNB9MQXAms3jsNnUT7UeAr7oxIdaudTvAQ3tMQpt5TBjHixaW6se93Duv1RUc5ogQQUBAtD6IcslDv9SoDSIHP40XMO9Vb2ZBRewphq4AA1VmDQuD0KJurxpCMYse7y8OEwZApHqnvzTopDvY0?purpose=inline)

HTML

Structure and content

[File:CSS3 logo.svg - Wikimedia Commons](https://images.openai.com/static-rsc-4/2MK3wvo41L0TqnyB_4dXtB__7ByYTDVzc_MxMXeZqrv2RuXuHrxTN7eNgAtgi5butKk_L5w2i8j-x0HsTh76g6rGt32a0zzLV-7JCy6X-LJ75Q8dQUmNdMT2prjsNCX-5OxqExjFvKdpVvn8agk5oEm0iOEJvd71HF_a1LRm6cQ?purpose=inline)

CSS

Design and layout

[JavaScript color icon in PNG, SVG](https://images.openai.com/static-rsc-4/tr6qZTUAn1whOfn0lXCVxhJFmyIYZXNtsFIA9qUaP24t1AZpVWRnxIhyvCLzzinoDuzy5ewSmCe_xtQgWpGRI6qCXGVf3_Qec9yjTvLG3eGny9looSH04-Iqbs7Q73TzXtYEuyNiilBOXZI6rmd7yutxo8_o1Vzgddp9dLfTXk8?purpose=inline)

JavaScript

Behaviour and interaction

Example: A login page

- HTML creates the username field, password field and login button.
- CSS controls their colours, sizes, spacing and layout.
- JavaScript can validate input and handle interactive behaviour.

Here is a simple comparison:

| Technology | Main responsibility |
| ---------- | ------------------- |
| HTML       | Structure           |
| CSS        | Presentation        |
| JavaScript | Behaviour           |

These technologies work together to create modern websites.

## 4. How does a web browser understand HTML?

A web browser is software that retrieves, processes and displays web content.

Examples include:

- Google Chrome
- Mozilla Firefox
- Microsoft Edge
- Safari

When you open an HTML document, the browser processes its markup and creates an internal representation called the DOM (Document Object Model).

Let's understand the process.

[웹 브라우저는 렌더링 프로세스](https://images.openai.com/static-rsc-4/2hewNy8OFXOdASzYqarpvks0jwMInOPuhuBlnZxdcb2H8g6m6rmuIwsT1cUh-QfIJz8GQzFeClvZYkkKNFloMIWw0sjWeXzzxLlIW1azrOP-gq__X4--tPoE_rvhxzbX3Vd9Ua9kRw4yy6YSO8FMTylOBW-SJ1ZNbL5SJc452Zc?purpose=inline)

[cresumerjang.github.io](https://cresumerjang.github.io/2019/06/24/critical-rendering-path/?utm_source=chatgpt.com)

The simplified process:

1. Browser receives or reads the HTML document.
2. HTML parser processes the markup.
3. Browser constructs the DOM tree.
4. CSS is processed into the CSSOM.
5. Browser combines the relevant structures to calculate rendering information.
6. Layout and painting produce the visible webpage.

JavaScript can also modify the DOM after the page has loaded.

Important terminology:

- HTML Source: The original HTML markup.
- HTML Parser: The browser component that parses HTML.
- DOM: The browser's object-based representation of the document.
- Rendering: The process of displaying webpage content.

We will study DOM and browser rendering in much greater depth in our advanced lessons.

## 5. What is a Webpage and a Website?

These terms are related but not identical.

Webpage: A single document or resource displayed in a web browser.

Example: A website's About page.

Website: A collection of related webpages and resources generally available under a common domain.

Example: A website might contain:

```
example.com/
│
├── index.html
├── about.html
├── services.html
└── contact.html
```

Each HTML file can represent a separate webpage.

## 6. What is the difference between HTML and HTML5?

HTML has evolved through multiple versions.

| Version              | Description                                                                |
| -------------------- | -------------------------------------------------------------------------- |
| HTML                 | Early versions of the markup language                                      |
| HTML 2.0             | Formalized early HTML standards                                            |
| HTML 3.2             | Added features such as tables and applets                                  |
| HTML 4.01            | Improved structure, forms and styling support                              |
| XHTML                | XML-based reformulation of HTML                                            |
| HTML5                | Major evolution introducing semantic elements, native audio/video and more |
| HTML Living Standard | Continuously maintained modern HTML specification                          |

Important: HTML5 is commonly used to describe the modern generation of HTML features. Today, HTML is maintained as a Living Standard by WHATWG rather than being developed through numbered HTML versions like the old model.

Modern HTML includes elements such as:

```
<header>
<nav>
<main>
<section>
<article>
<footer>
<video>
<audio>
```

We will study these elements in their appropriate chapters.

## 7. How to create and run an HTML file

Now let's start the practical part.

You will need:

- VS Code
- A web browser (Chrome is fine)
- A folder for your HTML learning repository.

Step 1: Create a project folder

Create a folder named:

```
Complete-HTML-Learning
```

Open it in VS Code.

Step 2: Create your first HTML file

Create a file named:

```
index.html
```

Step 3: Write the following code

```

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My First Webpage</title>
</head>
<body>

    <h1>Hello, World!</h1>

    <p>I am learning HTML from basic to advanced.</p>

</body>
</html>

```

Step 4: Run the file

1. Save the file using `Ctrl + S`.
2. Open the folder in File Explorer.
3. Double-click `index.html`.
4. It will open in your default browser.

[a web browser displaying a web page, with a welcome heading and a hello world paragraph](https://images.openai.com/static-rsc-4/zMIow12-p5jEktZ_JEpH6ThF0lcPv03tUBfNcRaAzSzmRHx0HI2Vjw65tB5Vn04Ot5XFwbFDXTV6izwh9Pv-vmQ6IWfHyo3bVssiTC-vbR8P2kWyflXEJj0KKyRZTRQ4KdqK8SEnnP26XocDDHLil5LUQsFDXT_kieK2URdxVHs?purpose=inline)

[bmoseley.com](https://www.bmoseley.com/cr/4-28?utm_source=chatgpt.com)

Congratulations! You have created your first HTML webpage.

## 8. Understanding your first HTML document

Let's understand what each line does. Don't worry if some elements are unfamiliar; we will study each one in detail in upcoming lessons.

| Code                     | Purpose                                                    |
| ------------------------ | ---------------------------------------------------------- |
| `<!DOCTYPE html>`        | Declares that the document uses modern HTML.               |
| `<html>`                 | Root element of the HTML document.                         |
| `lang="en"`              | Specifies that the document's primary language is English. |
| `<head>`                 | Contains document metadata and resource information.       |
| `<meta charset="UTF-8">` | Defines the character encoding.                            |
| `<meta name="viewport">` | Helps the page adapt to different device viewports.        |
| `<title>`                | Defines the browser tab title.                             |
| `<body>`                 | Contains the webpage's main document content.              |
| `<h1>`                   | Represents a top-level heading.                            |
| `<p>`                    | Represents a paragraph.                                    |

A useful distinction:

- `head` contains information about the document.
- `body` contains the document's visible content.

We will study the complete document structure in Lesson 2.

## 9. Important HTML terminology

Before moving forward, understand these terms because we will use them throughout the course.

| Term            | Meaning                                                |
| --------------- | ------------------------------------------------------ |
| Tag             | Markup such as `<p>` or `</p>`.                        |
| Element         | The complete HTML structure, such as `<p>Hello</p>`.   |
| Attribute       | Additional information provided inside an opening tag. |
| Attribute value | The value assigned to an attribute.                    |
| Nesting         | Placing one element inside another.                    |
| Parent element  | An element that contains another element.              |
| Child element   | An element directly contained inside another element.  |
| DOM             | Object-based representation of an HTML document.       |

Example:

```
<p class="intro">Welcome to HTML.</p>
```

Here:

- `<p>` = Opening tag
- `class` = Attribute
- `"intro"` = Attribute value
- `Welcome to HTML.` = Text content
- `</p>` = Closing tag
- Complete line = HTML element

We will revisit these concepts with more examples in Lesson 2 and Lesson 3.

## 10. HTML official documentation

As a professional developer, you should become comfortable reading official documentation instead of relying entirely on tutorials.

These will be our primary references:

[GitHub - whatwg/html: HTML Standard](https://images.openai.com/static-rsc-4/4Up9xX-B87ETG8G3QEreD88813MGihqLhkEBXID4-F31LwVahsNKs7i2cqyqNAxZg8XDMnS0akKGXBY5k42ckJGrZFxXtV6wSa_4kImw9b5AHRA54EfAwC4r6ySBZWMJnN_MqPCE6FeUpJk_mQmthd-Zur3_OYEteFaDfZRDNiU?purpose=inline)

WHATWG HTML Living Standard

Primary technical specification

[Read HTML Standard](https://html.spec.whatwg.org/?utm_source=chatgpt.com)

[MDN Web Docs (@MozDevNet) on X](https://images.openai.com/static-rsc-4/xkaqDT0Kxlt11lVFdYBiad4bF6x8MUIREB8ITBerapnVMSJykqelpuWHwnBufWKPx5u2hFaADl0ohXmiFYDPswjVEgDrKTlEGdCt7qupHtbO6n8mQWpQb0hyei7wdcyXPEkWh1LeRoRad5C6d-7vJoRpmlqCj4WVx5WhEibVFAs?purpose=inline)

MDN Web Docs

Explanations, examples and references

[Explore HTML documentation](https://developer.mozilla.org/en-US/docs/Web/HTML?utm_source=chatgpt.com)

[W3C - World Wide Web Consortium's activities/tech stack/c...](https://images.openai.com/static-rsc-4/FmL3VGxlCxgnYNnZbs_cxC0TQ3ldSgLSojaRYjajdp6kNr8NGc0EPGJdpQ_0aK9kXXnBpa_vFS6O2_Bfd6napBWfXX90HiaGDk9jDN-Pj7elDfqPSoOUt8OvLX04G2E4n9eqcK_XhsgNn4O_-kPnGz1N9QsDnH93Y6ylFTCfmSY?purpose=inline)

W3C

Web standards and accessibility resources

[Visit W3C](https://www.w3.org/?utm_source=chatgpt.com)
