# Bootstrap

## Used for

- To design responsive web pages and applications.
- It takes a mobile-first approach to web development and includes pre-built CSS styles and classes, plus some JavaScript functionality.

## Enable it in the HTML file

```html
<link
  rel="stylesheet"
  href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css"
  integrity="sha384-BVYiiSIFeK1dGmJRAkycuHAHRg32OmUcww7on3RYdg4Va+PmSTsz/K68vbdEjh4u"
  crossorigin="anonymous"
/>
```

## Container fluid

All Bootstrap content must live inside this div

```html
<div class="container-fluid">content</div>
```

## Grid to align elements

- `col-md-*` // medium
- `col-xs-4` // extra small and number of columns to determine the width of the element
- Must be placed in a div element to work

Example:

```html
<div class="container-fluid">
  <div class="row">
    <div class="col-xs-4">
      <button class="btn btn-block btn-primary">Like</button>
    </div>
    <div class="col-xs-4">
      <button class="btn btn-block btn-info">Info</button>
    </div>
    <div class="col-xs-4">
      <button class="btn btn-block btn-danger">Delete</button>
    </div>
  </div>
</div>
```

## Make Images Mobile Responsive

Just add the "img-responsive" class to your image.

## Create a visual sense of depth for columns

Just use the class="well" in a div.

## Center Text

Add the class "text-center" to the `h` and `p` elements.

```html
<h2 class="red-text text-center text-primary">your text</h2>
```

## Input text

```html
<input type="text" class="form-control" placeholder="cat photo URL" required />
```

## Buttons

### Basic

```html
<button class="btn btn-default">Like</button>
```

### Block Element

The button would take up 100% of the available width

```html
<button class="btn btn-default btn-block">Submit</button>
```

### Primary color

```html
<button class="btn btn-primary btn-block">Like</button>
```

### Info styling

```html
<button class="btn btn-block btn-info">Like</button>
```

### Danger styling: btn-danger

## Use a span to Target Inline Elements

```html
<p>Top 3 things cats <span class="text-danger">hate:</span></p>
```

## Add Font Awesome Icons to Buttons

These icons can be web fonts or vector graphics; they are treated just like fonts.

```html
<link
  rel="stylesheet"
  href="https://use.fontawesome.com/releases/v5.8.1/css/all.css"
  integrity="sha384-50oBUHEmvpQ+1lW4y57PTFmhCaXp0ML5d60M1M7uH2+nqUivzIebhndOJK28anvf"
  crossorigin="anonymous"
/>
```

The `i` element was originally used to make other elements italic but is now commonly used for icons.

```html
<button type="submit" class="btn btn-primary">
  <i class="fa fa-paper-plane"></i> Submit
</button>
```

The `span` element is also acceptable for use with icons.

```html
<button type="submit" class="btn btn-primary"><span><i class="fa fa-paper-plane"></i></span> Submit</button>
```
