# Nowland Grid

A light design driven float SCSS grid system.

## A *new* css-grid in 2016 really?

Yes, I know it's a bit odd publishing a grid in 2016 with the CSS grid spec sneaking up and the tried and trusted bootstrap grid or foundation grid being a safe bet to use.

## Configuring

In `settings/_breakpoints.scss`:

```
$breakpoints: (
  "menu"  : ( em(640px), false),
  "small" : ( em(768px), true),
  "huge"  : ( em(1800px), true)
)
```

In `settings/_grid.scss`:

```
$grid: (
  "columns"   : 10,
  "gutter"    : 36px,
  "max-width" : em(1400px),
  "debug"     : false
)
```

## Building the CSS/SASS

`npm install && npm run build-css`

------

Copyright (c) 2016, James Nowland

Permission to use, copy, modify, and/or distribute this software for any purpose with or without fee is hereby granted, provided that the above copyright notice and this permission notice appear in all copies.

THE SOFTWARE IS PROVIDED "AS IS" AND THE AUTHOR DISCLAIMS ALL WARRANTIES WITH REGARD TO THIS SOFTWARE INCLUDING ALL IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS. IN NO EVENT SHALL THE AUTHOR BE LIABLE FOR ANY SPECIAL, DIRECT, INDIRECT, OR CONSEQUENTIAL DAMAGES OR ANY DAMAGES WHATSOEVER RESULTING FROM LOSS OF USE, DATA OR PROFITS, WHETHER IN AN ACTION OF CONTRACT, NEGLIGENCE OR OTHER TORTIOUS ACTION, ARISING OUT OF OR IN CONNECTION WITH THE USE OR PERFORMANCE OF THIS SOFTWARE.
