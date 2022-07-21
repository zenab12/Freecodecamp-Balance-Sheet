# [Balance-Sheet](https://zenab12.github.io/Freecodecamp-Balance-Sheet/)
## few tips i learned while coding this task :
- Screen readers announce HTML elements based on the document flow. so You can use CSS to reverse the order of the text on the page, but the HTML order will make more sense for a screen reader.
- if you want any element to be hidden from screen readers,  give it the `aria-hidden` attribute set to **true**
- The caption element should always be the first child of a table, but can be positioned with the caption-side CSS property


- > The CSS `clip` property is used to define the visible portions of an element. Set the `span[class~="sr-only"]` selector to have a `clip` property of `rect(1px, 1px, 1px, 1px)`. The `clip-path` property determines the shape the clip property should take. Use both the `clip-path` and `-webkit-clip-path` selectors to set the value to `inset(50%)`, forming the clip-path into a **rectangle** within the element.we will need to take these hidden elements out of the document flow. Give the span[class~="sr-only"] selector a position property set to absolute, a padding property set to 0, and a margin property set to -1px. This will ensure that not only are they no longer visible, but they are not even within the page view.
```
span[class~="sr-only"] {
     border: 0 !important;
     clip: rect(1px, 1px, 1px, 1px) !important;
     clip-path: inset(50%) !important;
     -webkit-clip-path: inset(50%) !important;
     height: 1px !important;
     width: 1px !important;
     position: absolute !important;
     overflow: hidden !important;
     white-space: nowrap !important;
     padding: 0 !important;
     margin: -1px !important;
}
```

<p align="center">
<img src="https://user-images.githubusercontent.com/78083890/180297257-d5cb8945-c400-45d4-981f-70b73915e8c7.png" alt="laptopScreen" width="600">
</p>

