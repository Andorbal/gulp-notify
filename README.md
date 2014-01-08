# gulp-notify [![NPM version][npm-image]][npm-url] [![Dependency Status][depstat-image]][depstat-url]

> notification plugin for [gulp](https://github.com/gulpjs/gulp)

Use to send messages to Mac Notification center using the 
[node-notifier](https://github.com/mikaelbr/node-notifier) module. 
Can also specify custom notifier (e.g. Growl notification).

**Note: Without overriding the notifier, Mac OS X >= 10.8 is required for this to run.

## Usage

First, install `gulp-notify` as a development dependency:

```shell
npm install --save-dev gulp-notify
```

Then, add it to your `gulpfile.js`:

```javascript

var notify = require("gulp-notify");
gulp.src("./src/test.ext")
  .pipe(notify({
    message: "Hello Gulp!"
  }));
```

## API

### notify(String)

A message to notify per data on stream.

### notify(Function)
Type: `function(file)`  

The result of the function is used as message.
File from gulp stream passed in as argument.

### notify(options)

#### options.message
Type: `String`  
Default: File path in stream

The message you wish to attach to file.

#### options.title
Type: `String`  
Default: "Gulp Notification"

The title of the notification


#### options.notifier
Type: `Function(options, callback)`  
Default: node-notifier module

Swap out the notifier by passing in an function. 
The function expects two arguments: options and callback.

The callback must be called when the notification is finished. Options
will contain both title and message.


## License

[MIT License](http://en.wikipedia.org/wiki/MIT_License)

[npm-url]: https://npmjs.org/package/gulp-notify
[npm-image]: https://badge.fury.io/js/gulp-notify.png

[depstat-url]: https://david-dm.org/mikaelbr/gulp-notify
[depstat-image]: https://david-dm.org/mikaelbr/gulp-notify.png
