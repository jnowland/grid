# That Opinionated Float Grid

A design driven float grid system.

#### What do use for the grid?
I roll my own, because breakpoints are used to stop a design from breaking and grids should be used in the same way.

# Features:

### Manage responsive breakpoints.

In `settings/_breakpoints.scss`:

```
$breakpoints: (
  "menu"  : ( em(640px), false),
  "small" : ( em(768px), true),
  "huge"  : ( em(1800px), true)
)
```
 - Manage all parts your design breaks in one spot.
 - Control over code output via opt-in grid generation as not all designs require an entire grid at a breakpoints.

### Debugging built in:
In the top right corner you can know the active grid and breakpoint. These aren't always the same!

![Debug Grid and Breakpoints](https://cloud.githubusercontent.com/assets/1244314/14584946/aa311980-04a3-11e6-944e-6ac02eaefe4e.gif)

This is done with a `.debug` class when the `/settings/_grid.scss` has debug enabled.

### Number based so easier to tweak in dev mode

Use the `↑` `↓` keys to tweak grids in Chrome dev tools.

![Debug using arrow keys](https://cloud.githubusercontent.com/assets/1244314/14584861/3aa0b5b0-04a0-11e6-8c90-bfb1a8d6656f.gif)

### Syncs with inline media query mixin snippet

![Inline Media Query Snippet ](https://cloud.githubusercontent.com/assets/1244314/14584867/5496867a-04a0-11e6-870e-344287e12520.gif)

Includes a sublime snippet to make it easy to use the inline media query functions.

### Lighter on code.

The grid doesn't come with 100's of push/pull combination at every breakpoint.
From my experience you would lucky to have to use one of these in a design.

If you do you can just write that rule. See `layout/_customGrid.scss`

### File Size Comparison

This is a comparison of a default grid with 4 breakpoints.

|                      | Foundations | Bootstrap     | That Opinionated Float Grid  |    
|--------------------- |---          |---            |---                           |
| Lines of CSS         | 734         | 696           | 93                           |     
| Size(kb)             | 19kb        | 11kb          | 3kb                          |     
| Min Size             | 15kb        | 8kb           | 2kb                          |    

It should be worth mentioning both bootstrap and foundation have have push pull code.

### Naturally spoken syntax:

`<div class="col-9@palm">`

The use of the `@` symbol is used as name spacing in our modified BEM system to indicate a media query based `--modifier` extending on the BEM principals. A responsive grid system is essentially adding a modifier to the grid at a specific break point.

e.g `.col-6@sm` vs `col-sm-6` vs `medium-6`

### Supports inline-block grid easily

```
  <div class="row BlockGrid BlockGrid--top"><!--
  --><div class="col-6 col-8@sm">Inline comments</div><!--
  --><div class="col-6 col-4@sm">Remove whitespace</div><!--
--></div>
```

## How's it different to Bootstrap/Foundations?

- Main philosophy is that the grid should be used in the same way breakpoints are used.
- You should have a grid that is dictated from the design not devices.
- This is more aimed at people chasing perfect code - minimal amount of code.
- More of a widths based system than an all encompassing grid system.

## How's it similar?

- Mobile First Responsive.
- Percentage grid.
- Negative margin on `.row` to solve nesting.
- Padding for gutters padding based `box-sizing: border-box;`.

------

** Opinionated issues with bootstrap/foundations grids**

* Grid naming was made based on devices not the design.
* Adding/Removing a new break point wasn't easy.
* Media queries didn't sync with the grid.
* Majority of grid code generated was never used.
* No ability to debug grid and named breakpoint.

That list likely says a lot more about the me than other framework grids.

#### Micro Optimizing selectors to avoid columns

Default Column Class:
`[class^=col-]` 

**VS**

Foundations requires a  `.columns` class on every column.

**VS**

Bootstrap - Extend
`.col-lg-1, .col-lg-10, .col-lg-11, .col-lg-12, .col-lg-2, .col-lg-3, .col-lg-4, .col-lg-5, .col-lg-6, .col-lg-7, .col-lg-8, .col-lg-9, .col-md-1, .col-md-10, .col-md-11, .col-md-12, .col-md-2, .col-md-3, .col-md-4, .col-md-5, .col-md-6, .col-md-7, .col-md-8, .col-md-9, .col-sm-1, .col-sm-10, .col-sm-11, .col-sm-12, .col-sm-2, .col-sm-3, .col-sm-4, .col-sm-5, .col-sm-6, .col-sm-7, .col-sm-8, .col-sm-9, .col-xs-1, .col-xs-10, .col-xs-11, .col-xs-12, .col-xs-2, .col-xs-3, .col-xs-4, .col-xs-5, .col-xs-6, .col-xs-7, .col-xs-8, .col-xs-9`

------------

# Configuring

In `settings/_breakpoints.scss`:

```
$breakpoints: (
  "xs"    : ( em(480px) , false),
  "s"     : ( em(640px) , false),
  "sm"    : ( em(768px) , true),
  "m"     : ( em(960px) , false),
  "md"    : ( em(992px) , true),
  "lg"    : ( em(1200px) , true),
  "big"   : ( em(1300px) , false),
  "huge"  : ( em(1800px) , false)
);
```
*Note: not all breakpoints need to be grids as shown above by the `"menu"` breakpoint being `"false"`*. This breakpoint list controls inline queries as well.

In `settings/_grid.scss`:

```
$grid: (
  "columns"   : 10,
  "gutter"    : 36px,
  "max-width" : em(1400px),
  "debug"     : false
)
```
Yes… not all designs are or should be 12 columns.

-----

# Building the CSS

`npm install && npm run build-css`

------

Permission to use, copy, modify, and/or distribute this software for any purpose with or without fee is hereby granted, provided that the above copyright notice and this permission notice appear in all copies.

THE SOFTWARE IS PROVIDED "AS IS" AND THE AUTHOR DISCLAIMS ALL WARRANTIES WITH REGARD TO THIS SOFTWARE INCLUDING ALL IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS. IN NO EVENT SHALL THE AUTHOR BE LIABLE FOR ANY SPECIAL, DIRECT, INDIRECT, OR CONSEQUENTIAL DAMAGES OR ANY DAMAGES WHATSOEVER RESULTING FROM LOSS OF USE, DATA OR PROFITS, WHETHER IN AN ACTION OF CONTRACT, NEGLIGENCE OR OTHER TORTIOUS ACTION, ARISING OUT OF OR IN CONNECTION WITH THE USE OR PERFORMANCE OF THIS SOFTWARE.
