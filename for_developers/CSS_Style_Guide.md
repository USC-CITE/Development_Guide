# CSS Style Guide

This document aims to provide you, the developer, a **standardized way of writing CSS for the committee's existing web development projects**.

While this guide is subjective, you are free to follow it on personal and commercial projects that have little to no relation with this committee.

There are plenty of CSS style guides like this on the Internet. This is one of them.

## Table of contents

-   [Why enforce this guide?](#why-enforce-this-guide)
-   [Browser compatibility](#browser-compatibility)
-   [Style formatting](#style-formatting)
-   [The global stylesheet](#the-global-stylesheet)

## Why enforce this guide?

Without a standard, developers working on a software project **create things based on their existing perception**.

This can lead to problems like:

-   Inconsistency, for example on the CSS class names and architecture.
-   Conflict, two developers with different mindsets on how to approach CSS will have a hard time working with each other.
-   Distress, because of the complexity since everybody is "_doing things in their own direction_".

A guide like this rallies developers to one point that they can follow and debate what to agree on.

## Browser compatibility

The baseline years are between **2016-2017**.

It was a time where the [ES6 \(ECMAScript 2015\)](https://caniuse.com/?search=ES6) JavaScript specification is on its way to implementation across major browsers like Chrome, Firefox, Safari, and Edge.

[This guide does not support Internet Explorer.](https://www.computerworld.com/article/3663442/death-of-internet-explorer-good-riddance-to-bad-rubbish.html)

One CSS feature that was added between those years was **Custom CSS Variables/Properties**.

```css
:root {
    --my-custom-variable: my-value;
}

.selector {
    property: var(--my-custom-variable);
}
```

[Check support for the CSS functionality you are going to use](https://caniuse.com/) and benchmark it with our baseline.

> **What happens if I use an unsupported functionality?**
>
> Your browser will ignore the unrecognized style and move on to parse another. It won't return an error and make your webpage stop loading.

## Style formatting

The formatting rules are copied and altered from [Principles of writing consistent, idiomatic CSS](https://github.com/necolas/idiomatic-css) by Nicolas Gallagher and is licensed under the [Creative Commons Attribution 3.0 Unported License](http://creativecommons.org/licenses/by/3.0/).

---

### Whitespace

Only one style should exist across the entire source of your codebase. Always be consistent in your use of whitespace. Use whitespace to improve readability.

-   **Never** mix spaces and tabs for indentation.
-   Choose between soft indents (spaces) or real tabs. Stick to your choice without fail. **(Preference: tabs)**
-   If using spaces, choose the number of characters used per indentation level. **(Preference: 4 spaces)**

### Comments

Well commented code is extremely important. Take time to describe components, how they work, their limitations, and the way they are constructed. Don't leave others in the team guessing as to the purpose of uncommon or non-obvious code.

Comment style should be simple and consistent within a single code base.

- Place comments on a new line above their subject.
- Keep line-length to a sensible maximum, **(Preference: 80 columns)**.
- Make liberal use of comments to break CSS code into - discrete sections.
- Use "_sentence case_" comments and consistent text indentation.

Tip: configure your editor to provide you with shortcuts to output agreed-upon comment patterns.

Example:
```css
/* ==========================================================================
   Section comment block
   ========================================================================== */

/* Sub-section comment block
   ========================================================================== */

/**
 * Short description using Doxygen-style comment format
 *
 * The first sentence of the long description starts here and continues on this
 * line for a while finally concluding here at the end of this paragraph.
 *
 * The long description is ideal for more detailed explanations and
 * documentation. It can include example HTML, URLs, or any other information
 * that is deemed necessary or useful.
 *
 * @tag This is a tag named 'tag'
 *
 * TODO: This is a todo statement that describes an atomic task to be completed
 *   at a later date. It wraps after 80 characters and following lines are
 *   indented by 2 spaces.
 */

/* Basic comment */
```

### Formatting

The chosen code format must ensure that code is: easy to read; easy to clearly comment; minimizes the chance of accidentally introducing errors; and results in useful diffs and blames.

-   Use one discrete selector per line in multi-selector rulesets.
-   Include a single space before the opening brace of a ruleset.
-   Include one declaration per line in a declaration block.
-   Use one level of indentation for each declaration.
-   Include a single space after the colon of a declaration.
-   Use uppercase hex values, e.g., `#FFAAEE.
-   Use single or double quotes consistently. **Preference is for single quotes**, e.g., `content: ''`.
-   Quote attribute values in selectors, e.g., `input[type='checkbox']`.
-   Where allowed, avoid specifying units for zero-values, e.g., `margin: 0`.
-   Include a space after each comma in comma-separated property or function values.
-   Include a semi-colon at the end of the last declaration in a declaration block.
-   Place the closing brace of a ruleset in the same column as the first character of the ruleset.
-   Separate each ruleset by a blank line.

```css
.selector-1,
.selector-2,
.selector-3[type="text"] {
    -webkit-box-sizing: border-box;
    -moz-box-sizing: border-box;
    box-sizing: border-box;
    display: block;
    font-family: helvetica, arial, sans-serif;
    color: #333333;
    background: #FFFFFF;
    background: linear-gradient(#FFFFFF, rgba(0, 0, 0, 0.8));
}

.selector-a,
.selector-b {
    padding: 10px;
}
```

### Declaration order

If declarations are to be consistently ordered, it should be in accordance with a single, simple principle.

Smaller teams may prefer to cluster related properties (e.g. positioning and box-model) together.

```css
.selector {
    /* Positioning */
    position: absolute;
    z-index: 10;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;

    /* Display & Box Model */
    display: inline-block;
    overflow: hidden;
    box-sizing: border-box;
    width: 100px;
    height: 100px;
    padding: 10px;
    border: 10px solid #333;
    margin: 10px;

    /* Other */
    background: #000;
    color: #fff;
    font-family: sans-serif;
    font-size: 16px;
    text-align: right;
}
```

Larger teams may prefer the simplicity and ease-of-maintenance that comes with alphabetical ordering.

### Exceptions and slight deviations

Large blocks of single declarations can use a slightly different, single-line format. In this case, a space should be included after the opening brace and before the closing brace.

```css
.selector-1 { width: 10%; }
.selector-2 { width: 20%; }
.selector-3 { width: 30%; }
```

Long, comma-separated property values - such as collections of gradients or shadows - can be arranged across multiple lines in an effort to improve readability and produce more useful diffs. There are various formats that could be used; one example is shown below.

```css
.selector {
    background-image: 
	    linear-gradient(#FFFFFF, #CCCCCC), 
	    linear-gradient(#FF33CC, #44EECC);
    box-shadow: 
	    1px 1px 1px #000000, 
	    2px 2px 1px 1px #CCCCCC inset;
}
```

## The global stylesheet

A stylesheet is global because it is present in every HTML page you render. This is where you **include styles that are common for every page**.

For example: a website and its webpages always have a header so it makes sense to include it in the global stylesheet.

```css
/* global.css */

.header {
    position: relative;
    height: 13.5rem;
    border-bottom: 0.1rem solid #187516;
    border-bottom: 0.1rem solid var(--bilbao);
}

.header-logo {
    position: absolute;
    top: 15%;
    left: 50%;
    transform: translateX(-50%);
}

```

Headers include a navigation bar and on some websites one of the navigation links change appearance to indicate the webpage you are on. 

This unique style can be appended in two ways:
1. Add the style to the unique stylesheet for that page.
2. Add a utility class on the global stylesheet and append it to the HTML tag.

Let's try the second one:

```css
/* global.css */

.link--isInPage > a {
    color: #212121;
    color: var(--black);
}
```

```html
<!-- some-page.html -->

<nav>
    <ul class="links">
      <li class="link link--isInPage"><a href="/login">Log-In</a></li>
      <li class="link"><a href="/signup/profile">Sign-Up</a></li>
    </ul>
</nav>
```

If we go with the first one, we risk repeating the same style for every page. What happens if we want to make a change? Then we have to modify that change repeatedly on every page as well.

The second one allows us to make that change only on the global stylesheet. Whatever changes we make is replicated across all HTML tags that bear the same class. 

> _This allows you to have a single source of truth... [This is the definition of scalability and maintainability](https://frontstuff.io/in-defense-of-utility-first-css). All you have to do is reuse the available code you wrote proactively, instead of having to tweak existing code reactively. - Sarah Dayan_

Again **include the styles that can be generalized to your website**. If a HTML tag requires some uniqueness and is reused across other pages, include it in the global stylesheet. **If a style is only unique to that page**, put it in its own stylesheet or `<style>` tag whichever makes sense.