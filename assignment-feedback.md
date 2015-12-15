## Notes from the Assignment:

---
### `<head>` or `<header>`?
The `<header>` is an html5 structural element meant to contain the _visible_ header in a website's design. It is different from the `<head>` element, which is _unseen_, and contains the site's meta information, links to CSS and other documents, and a few other weird things. The `<header>` element will **always** be inside of the `<body>` element, as everything on the page is. The `<body>` element should be the very first thing written after the closing `<head>` tag.  
Example:  
```
<head>
    <title>This The Way</title>
    <!-- other head stuff -->
</head>
<body>
    <header>
        <h1>This The Way</h1>
    </header>
    <!-- other body stuff -->
</body>
```

---
### Keep your code DRY (Don't Repeat Yourself)
You'll often encounter situations where multiple elements require the same styling, and in those situations it is better to apply the styles to multiple chained selectors then to rewrite the rules for each one indivudually over, and over. A common example is this: 
```
body {
    /* the overall body copy is serif */
    font-family: serif;
}

/* but headings are set in sans-serif */
h1 {
    color: #444;
    font-size: 48px;
    font-weight: bold;
    font-family: sans-serif;
}
h2 {
    color: #444;
    font-size: 36px;
    font-weight: bold;
    font-family: sans-serif;
}
h3 {
    color: #444;
    font-size: 24px;
    font-weight: bold;
    font-family: sans-serif;
}
h4 {
    color: #444;
    font-size: 16px;
    font-weight: bold;
    font-family: sans-serif;
}
```
Notice the only change in all of those headings was the font-size — so why write the common styles four times out? Let's combine those babies!
```
h1, h2, h3, h4 {
    color: #444;
    font-weight: bold;
    font-family: sans-serif;
}
h1 {
    font-size: 48px;
}
h2 {
    font-size: 36px;
}
h3 {
    font-size: 24px;
}
h4 {
    font-size: 16px;
}
```
Ahh, that's better! Now we can update them all at once, and we didn't repeat ourselves for no reason!

---
### Avoid "Presentational Markup"
Remember why "inline styles" are bad? Because you are adding styling directly to your markup, instead of doing it in your CSS document, which is meant for styling, and it becomes very unmanageable and hard to debug — well presentational markup is the same way — things like adding `<br>` tags to create spacing, and adding `align="right"` to an `img`. Basically, if it can be done in CSS, it _should_ be done in CSS — so don't use `<br>`s for creating space, and don't add any style-related attributes to your markup.
