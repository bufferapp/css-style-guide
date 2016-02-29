# Buffer CSS Style Guide

___

## Goal

To establish more consistency and readability across the Buffer team and our
open source projects.

___

## Ideals

> **Have a bias toward clarity** - from [The Buffer Values](http://www.slideshare.net/Bufferapp/buffer-culture-04)

___

## Table of Contents

  1. [Objects and Modifiers](#objects-and-modifiers)
  2. [Rule Declaration](#rule-declaration)
  3. [Preprocessors](#preprocessors)

___

## Objects and Modifiers

To write our CSS, we try and follow this simple naming convention:

### Objects

Objects are standalone entities that are meaningful on their own. Objects that are made up of multiple words are capitalized and connected by a single `-`.

**Examples:**

`Header`, `Sidebar`, `Button`, `Icon`, `Footer`, `Footer-Navigation`

### Modifiers

Modifiers change the appearance or behavior of objects. They are suffixed to the end of an object with a prefix of `--`. They should also be lowercase.

**Example:**

`Button--disabled`, `Icon--small`, `Navigation--hidden`

### In Practice

**HTML:**

```html
<button class="Button">
  Filter
</button>

<button class="Button Button--primary">
  Add to Queue
</button>

<button class="Button">
  <i class="Icon Button-Icon Icon-Calendar"></i>
  Schedule
</button>

<button class="Button Button--primary">
  <i class="Icon Button-Icon--primary Icon-Plus"></i>
  Add New Account
</button>
```

**CSS:**

```css
/* Buttons
------------------------------------------------------------ */
.Button {
  padding: 0 24px;

  height: 32px;

  font-size: 14px;
  line-height: 32px;
  color: #323b43;

  background-color: #ffffff;
  border: 1px solid #ced7df;
  border-radius: 4px;
}

.Button--primary {
  color: #ffffff;

  background-color: #168eea;
  border-color: rgba(0, 0, 0, 0.2);
  border-radius: 32px;
}

.Button-Icon {
  @include Button-Icon-Margin

  color: #323b43;
}

.Button-Icon--primary {
  @include Button-Icon-Margin

  color: #ffffff;
}

/* Icons
------------------------------------------------------------ */
.Icon {
  width: 16px;
  height: 16px;
}
```

### Benefits

#### Modularity

Objects styles should not have dependencies on other elements on a page. This will reduce any problems from cascading. It'll also give us the ability to transfer objects from one area to another without the risk of breaking a page's structure.

#### Reusability

Composing independant objects in a different way and reusing them reduces the amount of CSS needed and also helps maintainability.

A goal that we're keen to focus on is to have a library of production-ready objects as part of our style guide that we can simply copy and paste in to our projects as we're building Buffer.

#### Structure

Buffer's OM methodology, inspired by BEM, gives us a simple and understandable structure in how we write our CSS.

___

## General Formatting Rules

### Indentation

We indent by 2 spaces at a time and try to avoid mixing tabs and spacing:

```css
.Button {
  color: #fff;
}
```

### Lowercase

CSS that isn't an object name should be lower case:

```css
.Button--primary {
  color: #ffffff;

  background-color: #168eea;
  border-color: rgba(0, 0, 0, 0.2);
  border-radius: 32px;
}
```

### Declaration Order

We use the [box model](http://codeguide.co/#css-declaration-order) coupled with a line space between each section:

```css
.Button {
  padding: 0 24px;

  height: 32px;

  font-size: 14px;
  line-height: 32px;
  color: #323b43;

  background-color: #ffffff;
  border: 1px solid #ced7df;
  border-radius: 4px;
}
```

### Declaration Stops

We should end every declaration with a semicolon:

```css
.Button {
  background-color: #ffffff;
  border: 1px solid #ced7df;
  border-radius: 4px;
}
```

### Property Name Stops

We use a single space between the property and value and no space between the property and the colon:

```css
.Button {
  height: 32px;
}
```

### Declaration Block Separation

We use a single space between the last selector and the opening brace that begins the declaration block. The opening brace should be on the same line as the last selector in a given rule:

```css
.Button {
  // ...
}
```

### Selector and Declaration Separation:

We start a new line for each selector and declaration:

```css
h1,
h2,
h3 {
  font-weight: 600;
}
```

### Rule Separation

We put a blank line between rules:

```css
html {
  background: #f4f7f9;
}

body {
  font-size: 14px;
}
```

### CSS Quotation Marks

We use single quotation marks for attribute selectors and property values. We try and omit quotation marks completely in URI values (`url()`):

```css
@import url(//www.buffer.com/css/someCSSFile.css);

html {
  font-family: 'open sans', sans-serif;
}
```

___

## Preprocessors

*TODO*
