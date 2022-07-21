# few tips i learned while coding this task :
- Screen readers announce HTML elements based on the document flow. so You can use CSS to reverse the order of the text on the page, but the HTML order will make more sense for a screen reader.
- if you want any element to be hidden from screen readers,  give it the `aria-hidden` attribute set to **true**
- The caption element should always be the first child of a table, but can be positioned with the caption-side CSS property
