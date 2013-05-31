Axis CSS
---------

Axis is a terse, feature-rich css library built on top of stylus. It's a child of the [roots build system](http://github.com/jenius/roots), but is totally old enough to live on it's own. It can be integrated as a plugin for stylus or included manually.

**Detailed documentation for axis [can be found here!](http://roots.cx/axis)**

### Usage

Axis is already integrated into [roots](http://roots.cx) by default, and it's super easy to use it there. Definitely the easiest way if you are setting up a project that uses stylus anyway, and it comes with jade and coffeescript already ready out of the box. However, if you do want to include it yourself, here's how to make it happen with stylus/express:

```js
var connect = require('connect')
  , stylus = require('stylus')
  , axis = require('axis-css');

var server = connect();

function compile(str, path) {
  return stylus(str)
    .set('filename', path)
    .use(axis());
}

server.use(stylus.middleware({
    src: __dirname
  , compile: compile
}));
```

You should have access to all the axis mixins once this is done. Whoo!