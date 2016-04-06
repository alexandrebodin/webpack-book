# What is Webpack

Webpack is a module bundler for the Javascript ecosystem. It's main goal is to [Bundle](../GLOSSARY.md#Bundle) all your application code and dependencies targeting the browser.

## What does it do for real ?

Let's say your are using a library like [Boostrap](http://getbootstrap.com/) and you need to use it in your application. The naive approach is:

```html
<!DOCTYPE html>
  <head>
  <link href="css/bootstrap.min.css" rel="stylesheet">
  </head>
  <body>
    <!-- You would need to load jQuery first because bootstrap requires it  -->
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.3/jquery.min.js"></script>
    <script src="js/bootstrap.min.js"></script>
  </body>
</html>
```

When your app starts to grow you can see what a hassle it would be to handle all your dependencies.

Now, imagine being able to `require` the Javascript libraries you need directly into your `.js` files like that:

```javascript
var boostrap = require('boostrap');

// ... your code depending on the lib you just loaded
```

And then just have to do that:

```html
<!DOCTYPE html>
  <head>
  </head>
  <body>
    <!-- That's where the webpack magic happens -->
    <script src="js/bundle.js"></script>
  </body>
</html>
```

Well that's what Webpack is all about. It worries about loading and creating a final `js` file to import into your `index.html`

