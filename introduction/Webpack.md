# Webpack

Webpack is a module bundler for the Javascript ecosystem. It's main goal is to [Bundle](/GLOSSARY.md#Bundle) all your application code and dependencies targeting the browser.

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

When your app starts to grow you can easily image the hassle of handling all those dependencies and there respective loading in your app.

Now, imagine being able to `require` the Javascript libraries you need directly into your `.js` files like that:

```javascript
var boostrap = require('boostrap');

// ... your code depending on the lib you just loaded
```

and then juste have to do:

```html
<!DOCTYPE html>
  <head>
  </head>
  <body>
    <!-- It's here were the webpack magic happens -->
    <script src="js/bundle.js"></script>
  </body>
</html>
```

Well that's what webpack is all about. It worries about loading and creating a final `js` file to import into your `index.html` 


Webpack as tools like [gulp](http://gulpjs.com/) [grunt](http://gruntjs.com/) or [browserify](http://browserify.org/)



