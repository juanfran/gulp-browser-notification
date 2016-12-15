#gulp-browser-notification
> Show notifications in your browser

## Install

```shell
npm install gulp-browser-notification --save-dev
```

## Usage

### Import

```js
var browserNotification = require('gulp-browser-notification');
```

### Addinig middleware

```js
app.use(browserNotification.connect());
```

### Adding to tasks

```js
gulp.task('example-taks', function() {
  return gulp.src('/html/*.html')
    .pipe(browserNotification('the html has changed!'));
});
```

you can also call a function

```js
gulp.task('example-taks', function() {
  return gulp.src('/html/*.html')
    .pipe(browserNotification.notify(function(file) {
        return {
          title: 'the html has changed! ' + file.path
        }
    }))
});
```

#### options

##### changing port

- Type: `Integer`
- Default: 35728

```js
app.use(browserNotification.connect({
  port: 35728
}));
```

##### adding options to the notification

```js
.pipe(browserNotification.notify("Hi!"), {
  body: "notification body"
})
```

with function
```js
.pipe(browserNotification.notify(function(file) {
    return {
      title: file.path,
      options: {
        body: "notification body"
      }
    }
}))
```

[All notification options](https://developer.mozilla.org/es/docs/Web/API/notification)
