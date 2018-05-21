# Table of Contents

<!-- TOC -->

- [Table of Contents](#table-of-contents)
  - [BestAndMostUsefulSCSS](#bestandmostusefulscss)
    - [Progress](#progress)
    - [SASS Official Guide](#sass-official-guide)
    - [Lesson 01: Transpile SCSS to CSS using node-sass](#lesson-01-transpile-scss-to-css-using-node-sass)
    - [Lesson 02: Importing Partials](#lesson-02-importing-partials)
    - [Lesson 03: Importing Partials](#lesson-03-importing-partials)
    - [Lesson 04: Variables for Readability & Maintainability](#lesson-04-variables-for-readability--maintainability)
    - [Lesson 05: Built-In SCSS Functions](#lesson-05-built-in-scss-functions)
    - [Lesson 06: @mixin](#lesson-06-mixin)
    - [Lesson 07: @extend](#lesson-07-extend)
    - [Lesson 08: @for Control Directive](#lesson-08-for-control-directive)
    - [Lesson 09: @each Control Directive](#lesson-09-each-control-directive)
    - [Lesson 10: Custom Function @function](#lesson-10-custom-function-function)

<!-- /TOC -->

## BestAndMostUsefulSCSS

Egghead.io Course on SCSS by Ari Picker

[course link](https://egghead.io/courses/learn-the-best-and-most-useful-scss)

### Progress

- [X] ~~*SASS Guide*~~ [2018-05-21]
- [X] ~~*Lesson 01*~~ [2018-05-21]
- [X] ~~*Lesson 02*~~ [2018-05-21]
- [X] ~~*Lesson 03*~~ [2018-05-21]
- [X] ~~*Lesson 04*~~ [2018-05-21]
- [X] ~~*Lesson 05*~~ [2018-05-21]
- [X] ~~*Lesson 06*~~ [2018-05-21]
- [X] ~~*Lesson 07*~~ [2018-05-21]
- [X] ~~*Lesson 08*~~ [2018-05-21]
- [X] ~~*Lesson 09*~~ [2018-05-21]
- [X] ~~*Lesson 10*~~ [2018-05-21]

### SASS Official Guide

- SASS is a CSS preprocessor that enables:
  - variables
  - nesting
  - mixins
  - inheritance
  - and more!
- Variables
  - `$` declares a SASS variable

  ```SCSS
  $font-stack: Helvetica, sans-serif;

  body {
    font: 100% $font-stack;
  }
  ```

- Nesting
  - Beware of nesting too deep => leads to transpiled CSS that is over-qualified and could be difficult to maintain

```SCSS
nav {
  ul {
    margin: 0;
    padding: 0;
    list-style: none;
  }
}
```

- Partials
  - `_partial.scss` used in conjunction with `@import`

- Import
  - SCSS import improves on CSS import by minimizing HTTP request

```SCSS
// main.scss
// where _reset.scss exist in cur dir
@import 'reset.scss';

body {
  font: 100% Helvetica, sans-serif;
}
```

- Mixins
  - Powerful CSS Snippets that can included in CSS declaration statements, see example.

```SCSS
@mixin border-radius($radius) {
    -webkit-border-radius: $radius;
     -moz-border-radius: $radius;
      -ms-border-radius: $radius;
          border-radius: $radius;
}
.box { @include border-radius(10px); }
```

- Extend/Inheritance
  - Template Class
  - `%` symbol declares Template Class
  - `@extend` incorporates template styles into calling class

```SCSS
%message-shared {
  border: 1px solid #ccc;
  padding: 10px;
  color: #333;
}

.message {
  @extend %message-shared;
}
```

- Operators
  - Makes `+, -, *, /, %` available

```SCSS
.container { width: 100%; }

article[role="main"] {
  float: left;
  width: 600px / 960px * 100%;
}

aside[role="complementary"] {
  float: right;
  width: 300px / 960px * 100%;
}
```

- Script to Add to package.json:
  - `"scss": "node-sass --watch scss -o css"`

### Lesson 01: Transpile SCSS to CSS using node-sass

- `"scss": "node-sass --watch scss -o css"`

### Lesson 02: Importing Partials

- Partial filenames are prepended `_partial.scss`
- `@import _partial.scss`
- order matters

### Lesson 03: Importing Partials

- `&` immediate parent selector

```SCSS
img {
  transition: transform .8s ease-in-out;
  &:hover {
    transform: rotate(360deg);
  }
}
```

### Lesson 04: Variables for Readability & Maintainability

- `$` declares a SCSS variable
- variables are blocked scoped
- `.#{$wom}` similar to a template literate

### Lesson 05: Built-In SCSS Functions

- `lighten($base-color, 20%);`
- `darken($base-color, 35%);`
- `mix(color1, color2, 50%);`
- `complement(color);`
- [SASS built-in functions](http://sass-lang.com/documentation/Sass/Script/Functions.html)

### Lesson 06: @mixin

- `@mixin` defines a mixin

```SCSS
@mixin make-character($variable1: defaultValue) {
property: $variable1;
}
```

### Lesson 07: @extend

- Object inheritance in CSS
- `%` placeholder selector; only used if extended
- Extends: change the source order, mixins don’t. maintain relationships, mixins don’t. share inherited traits, mixins don’t. can extend multiple classes, mixins don’t. can create multiple class declarations in the compiled CSS, mixins don’t. can use the placeholder selector, mixins don’t.
- Mixins: can accept arguments, extends don’t. can pass additional content, extends don’t. repeat code when compiled, extends group class names together. work well wIth media queries, extends have a limited interaction wIth media queries.

### Lesson 08: @for Control Directive

- `@for $i from 1 through 10 {
  $value: .5 * $i;
}`

### Lesson 09: @each Control Directive

- `@each $hero in wonder-woman, spiderman, batman, superman {
  .#{$hero}-logo {
    color: red;
  }
}`

### Lesson 10: Custom Function @function

- Custom Functions
- `@function background($color) {@return $color;}`

_NOTE:_ This tutorial ran way too quick.