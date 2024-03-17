# Styling with CSS

You may remember the following line from the `<head>` in our last lesson:

```html
<link href="style.css" rel="stylesheet" type="text/css" />
```

This loads a *stylesheet* named `style.css` (which is included in our files).  Using this we can make our content look better!

Visit [this page](https://developer.mozilla.org/en-US/docs/Web/CSS) or [this page](https://www.w3schools.com/cssref/default.asp) for all of the different styles we can apply.

## Selectors vs Properties

In order to style certain sections of our web page we first must *select* them, and then apply *properties*.  Below is a basic example:

```css
*{

	font-family: Arial;
	
}
```

`*` is a **universal selector** - it will apply to everything unless something more specific is applied.  All properties are contained in the `{ }`.

`font-family` is a property.  It is followed by a colon, the value we wish to set and then a semi-colon to end the line.

We will now go through different types of *selectors*, during which you will see some *properties* we can use.  The website above can show you all of the different *values* each *property* can have.

## Selectors

### Type

We can use **type** selectors to target all tags of a certain type.  For example:

```css

h1{
	color: blue;
}

p{
	text-align: center;
}

img{
	width: 50%;
}
```

With these selectors **all** `<h1>` elements will have blue text, **all** `<p>` elements will be centre aligned and **all** `<img>` elements will be displayed at 50% width (of the containing block);

### Class

Imagine that you don't want **all** `<h1>` elements to have the same styling, or you want to repeat the same styling with different types of elements. 

Going back to `index.html`, we can add a `class` name to certain elements to apply the same styling to them.

```html
<p class = "info">This paragraph has a class of "info"</p>

<p>This one does not.</p>

<p class = "info">But this one does.</p>
```

In this case, using a *type selector* would apply the same styling to **all** `<p>` elements.  But using a class I can target a certain few.

```css

p{
	font-size: 10px;
}

.info{
	font-size: 12px;
}
```

With this styling,  all `<p>` elements will have a font size of 10 pixels.  However, using classes is more *specific*, so any `<p>` tags with `info` classes will have a font size of 12 pixels.

Classes can be applied to anything - I could use `class="info"` on a hyperlink if I wanted to!

### ID

This is used to identify *one specific element* to apply styling.  It therefore has the highest priority.

```html
<img src= "corgi.jpg" id = "corgi">
```

```css
#corgi{
	width: 100px;
	border: 1px dotted blue;
}
```

This will give *only* the element with `id = corgi` a width of 100px and a blue dotted border of 1px.

## Display

As mentioned in the previous lesson, all of our elements will stack on top of each other by default.  What if we wanted some text to appear beside an image?

There are different methods to doing so, but I feel this is the easiest (and most fool-proof).

**Step 1**: Enclose the items you want side-by-side in a `<div>`.  Give it an appropriate class or id name.

```html
<div class = "corgi-container">
	<img src= "corgi.jpg" id = "corgi">
	
	<p>A Pembroke Welsh Corgi</p>
</div>
```

**Step 2**: Apply the following property to the containing `<div>`:

```css
.corgi-container{
	display: flex;
}

```

That should be it!  This is making use of a [flex box](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Aligning_Items_in_a_Flex_Container).  There's much more you can apply but this is a basic application.


## Sizing + Position

Sometimes it's difficult to see the size/positioning of the elements we are styling.  As you are starting, you may want to try the following to better visualize:

1) Apply a `border` to everything (`*`) or certain elements.  This will allow you to *see* it's actual size/positioning.

2) If using Chrome press `Ctrl-Shift-C` and hover over each element.  You'll again see the size/positioning, but there's a lot of other information that will be presented as well.   

## So much more!

There is so much more css styling that can be used!  Use the search function in the linked website (or a Google search of `"CSS ________"`) to see what else you can do.