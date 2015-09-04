# strip-sourcemap-loader

strip sourcemapping urls from bundled webpack resources to not confuse safari

## why?

some packages are distributed with `//# sourceMappingURL =` comments embedded in them. Safari will find the first such comment and use that to find your source map. If it finds the wrong one, you lose.

## how?

In your webpack config,

```js
module.exports = {
  // ...
  module: {
    loaders: [
      {
        test: /\.js$/,
        include: /node_modules/,
        loaders: ['strip-sourcemap-loader']
      }
    ]
  }
}
```

## License

See LICENSE.

## Author

Eric O'Connell
eric.oconnell@gmail.com
