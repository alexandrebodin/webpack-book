# Configuration

First let's create some files.

```
project_dir/
-- index.html
-- index.js
-- webpack.config.js
```

* `webpack.config.js` Is the default name for Webpack configuration file. You can setup a full project work-flow just with this file.

In your `index.html` file let's link the file that Webpack will create for you

```html
<!DOCTYPE html>
  <head></head>
  <body>
    <script src="bundle.js"></script>
  </body>
</html>

## Source Code

### `webpack.config.js`

```javascript
module.exports = {
  // configuration goes here
  entry: {
  
  }
};
```

