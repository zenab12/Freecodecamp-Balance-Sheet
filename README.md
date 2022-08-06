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

## few tips i leaned From Mahratech:
### display attribute to make table or list 
1- `display:list-item` (list-style-position: inside or outside) inside or out side to make bullet of list inside element or outside it 

2- `display:table` ;  it is inside display which affect on it’s children for parent element div.table ; and children will take different values for display as for caption we will use

```
<!DOCTYPE html>
<html>
	<head>
	<style>
		 .table{display:table;width:300px;margin:50px auto;}
		 .caption{display:table-caption;text-align:center;}
		 .header{display:table-header-group;text-align:center;font-weight:bold;}
		 .body{display:table-row-group}
		 .footer{display:table-footer-group}
		 .row{display:table-row}
		 .cell{display:table-cell;text-align:center;border:3px dashed #ff3355;padding:10px;}
	</style>
	</head>
	<body>

		<div class="table">
		<h2 class="caption">Table Caption</h2>
		<div class="header">
		   <div class="row">
			 <div class="cell">Name</div>
			 <div class="cell">Age</div>
			 <div class="cell">Address</div>
		   </div>
		</div>

		<div class="body">
		   <div class="row">
			 <div class="cell">Zienab</div>
			 <div class="cell">22</div>
			 <div class="cell">Mansoura</div>
		   </div>
		  <div class="row">
			 <div class="cell">Souad</div>
			 <div class="cell">22</div>
			 <div class="cell">Mansoura</div>
		   </div>
		  <div class="row">
			 <div class="cell">Sanaa</div>
			 <div class="cell">22</div>
			 <div class="cell">Mansoura</div>
		   </div>
		</div>

		<div class="footer">
			 <div class="row">
			 <div class="cell">Amira</div>
			 <div class="cell">22</div>
			 <div class="cell">Mansoura</div>
		   </div>
		</div>

		</div>

	</body>
</html>

```
