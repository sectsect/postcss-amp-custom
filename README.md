# postcss-amp-custom

PostCSS plugin to optimize CSS source for AMP HTML.

## Install

```
npm install --save-dev postcss-amp-custom
```

## Use

```js
// postcss.config.js
module.exports = () => ({
    plugins: [
        require('postcss-amp-custom')({
            enableByteLimit: true
        })
    ]
});
```

```css
/* ./src/test.css */

@charset "UTF-8";
body {
  font-size: 16px;
}
@page {
  margin: 15mm;
}
@page hoge {
  size: portrait;
  margin: 15mm;
}
a {
  color: #39c !important;
  text-decoration: none;
}
@viewport {
  min-width: 640px;
  max-width: 800px;
}
@supports not (display: flex) {
  .flexbox {
    overflow: hidden;
  }
  .flexbox div {
    float: left;
  }
}


/* ./dist/test.css */

body{font-size:16px}a{color:#39c;text-decoration:none}
```

## Options

- enableByteLimit `Boolean` - If the CSS source exceeds 50 KB, it issues an error.(Default: `false`)

## License

[MIT License](https://github.com/kmrk/postcss-amp-custom/blob/master/LICENSE).