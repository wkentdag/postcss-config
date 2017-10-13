# postcss-config

Basic demo of a pure PostCSS setup that includes all of (IMO) the important SCSS features. Designed for minimal headache when migrating from SCSS to PostCSS.

* import
* `$` variable definition
* nested properties, including concatenation

Plus some other goodies included out of the box from `css-next`, like:

* autoprefixing
* custom media queries, e.g. `@media (--tablet) { ... }`

Uses the following PostCSS packages:

* [`postcss-cssnext`](https://github.com/MoOx/postcss-cssnext)
* [`postcss-nested`](https://github.com/postcss/postcss-nested)
* [`postcss-simple-vars`](https://github.com/postcss/postcss-simple-vars)
* [`postcss-import`](https://github.com/postcss/postcss-import)
  * Note: `cssnext` actually uses this under the hood, but was throwing erroneous errors about importing variables without explicitly adding `postcss-import` as a plugin first. See [here](https://github.com/postcss/postcss-import/issues/277#issuecomment-336319580) for more.


TL;DR, you can do this:

```css
@import 'variables.css';

.container {
  background-color: $color1;

  @media (--tablet) {
    background-color: $color2;
  }

  &__child {
    color: $color2;
    transform: skewX(10deg);  /* I get autoprefixed yay */

    @media (--tablet) {
      color: $color1;
    }
  }

  & .solo {
    text-transform: uppercase;
  }
}

pre {
  display: inline-block;
}

```

## Run It

```
yarn install
yarn start
```

Open `dist/index.html` in your browser
