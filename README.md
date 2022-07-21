# few tips i learned while coding this task :
- Screen readers announce HTML elements based on the document flow. so You can use CSS to reverse the order of the text on the page, but the HTML order will make more sense for a screen reader.
- if you want any element to be hidden from screen readers,  give it the `aria-hidden` attribute set to **true**
- The caption element should always be the first child of a table, but can be positioned with the caption-side CSS property


- > The CSS `clip` property is used to define the visible portions of an element. Set the `span[class~="sr-only"]` selector to have a `clip` property of `rect(1px, 1px, 1px, 1px)`. The `clip-path` property determines the shape the clip property should take. Use both the `clip-path` and `-webkit-clip-path` selectors to set the value to `inset(50%)`, forming the clip-path into a **rectangle** within the element.we will need to take these hidden elements out of the document flow. Give the span[class~="sr-only"] selector a position property set to absolute, a padding property set to 0, and a margin property set to -1px. This will ensure that not only are they no longer visible, but they are not even within the page view.
```
span[class~="sr-only"] {
  border: 0;
  clip: rect(1px, 1px, 1px, 1px);
  clip-path: inset(50%);
  -webkit-clip-path: inset(50%);
  height: 1px;
  width: 1px;
  position: absolute;
  overflow: hidden;
  white-space: nowrap;
  padding: 0;
  margin: -1px;
}
```

