# Get started

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
    path: './build',
    filename: 'bundle.js'
  }
};
```

`[Entry](../GLOSSARY.md#entry)`


