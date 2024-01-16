# CSS Style Guide

This document aims to provide you, the developer, a **standardized way of writing CSS for the committee's existing web development projects**.

While this guide is subjective, you are free to follow it on personal and commercial projects that have little to no relation with this committee.

There are plenty of CSS style guides like this on the Internet. This is one of them.

## Table of contents

-   [Why enforce this guide?](<#Why enforce\ this\ guide?>)
-   [Browser compatibility](<#Browser\ compatibility>)
-   [Style formatting](<#Style\ formatting>)
-   [The global stylesheet](<#The\ global\ stylesheet>)

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
