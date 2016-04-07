# Get started

You can find the source code for this example on [github](https://github.com/alexandrebodin/webpack-book-get-started)

## Installation

First install Webpack globally

```
npm install -g webpack
```

Next create a folder and initialize your npm project

```
mkdir project_dir && cd project_dir
npm init
```

Answer to the questions (if you are not planning on publishing your code you can press enter until it's finished)

## Setup

Now let's create some files.

```
project_dir/
-- index.html
-- index.js
-- webpack.config.js
```

* `webpack.config.js` Is the default name for Webpack configuration file. You can setup a full project work-flow just with this file.

In your `index.html` we load the file that Webpack will create for you.

```html
<script src="bundle.js"></script>
```

In your `index.js` let's say "Hi".

```javascript
console.log('Hello World!');
```

In your `webpack.config.js` we will initialize the application configuration.

```javascript
module.exports = {
  entry: './index.js',
  output: {
    filename: 'bundle.js'
  }
};
```

The configuration tels Webpack the file it needs to process is `index.js` and it has to output a file `bundle.js`in the `build` directory.

Let's try and run Webpack then !

```
webpack
```

Here Webpack automatically looks for a `webpack.config.js` file. You can specify another file using `'--config=PATH_TO_CONFIG`

Now your project should look like this (ignoring npm stuff)

```
project_dir/
-- bundle.js
-- index.js
-- index.html
-- webpack.config.js
```

In some browsers you cannot load local Javascript files, that's where `webpack-dev-server` comes in.

Among other awesome features `webpack-dev-server` can process your files and create a HTTP server to serve them.

Let's install it in your project

```
npm install --save-dev webpack-dev-server
```

Now run

```
./node_modules/.bin/webpack-dev-server
```

Go to the url `http://localhost:8080`. You should see `Hello World!` in your `console`.

You will notice in your `terminal` that Webpack is still running.
If you change your `index.js`file it will reprocess it on the fly. You can just reload your browser then.

Webpack offers features for automatic page reload and much more thanks to [plugins](../GLOSSARY.md#plugins) and [loaders](../GLOSSARY.md#loaders).

## Some code 

It's all well but for now you have an empty Javascript file. Let's add some code.

Create a folder `app` and a `my_module.js` file in it.

### `my_module.js`
```javascript
module.exports = {
  sayHi: function(firstname) {
    console.log('Hi ' + firstname);
  }
};
```

### `index.js`

```javascript
var myModule = require('./app/my_module');

myModule.sayHi('Webpack');
```

If you left `webpack-dev-server` running refresh your browser or restart `webpack-dev-server`. 

![magic](https://proxy.spigotmc.org/549de25581587a39657162f37f16dc374c122e4d?url=http%3A%2F%2Fs2.quickmeme.com%2Fimg%2F72%2F7221f725e518793a71eaec4da3d0d5b60fa961b374f3b33f8a83867da2dc331e.jpg)

You can see 'Hi Webpack' in the `console`.

To recap, Webpack can load modules just like [NodeJs](https://nodejs.org/docs/latest/api/modules.html) and compile them all into one file. You can now use open-source libraries and organize your code much better.

## Npm sugar 

Previously you add to use `./node_modules/.bin/webpack-dev-server` to use `webpack-dev-server` because it isn't installed globally.

Let's setup a `npm` script to simplify this. Add this to the `"scripts"` in your `package.json`

```
"dev": "webpack-dev-server"
```

Now you can just run 

```
npm run dev
```

Npm will first look in the `./node_modules` folder of your project when you use modules in your `package.json` scripts so you don't to specify the folder by hand. 