# mozjpeg-stream

The awesome JPEG minifying power of [mozjpeg](https://www.npmjs.com/package/mozjpeg) wrapped up as a `.pipe` friendly node duplex stream.

Grab flying pugs over http and automagically minify them with mozjpeg before letting them near your hard drive.

```js
var fs require('fs')
var http require('http')
var mozjpeg = require('mozjpeg-stream')

http.get('http://aboutpug.com/wp-content/uploads/2015/01/flying-monkey-cute-pug.jpg')
  .on('response', function (resp) {
    resp
      .pipe(mozjpeg())
      .pipe(fs.createWriteStream('flying-pug.min.jpg'))
  })
```

And so this chunky `2.1M` of [raw pug](https://raw.githubusercontent.com/tableflip/mozjpeg-stream/master/test/flying-pug.jpg)

...becomes `200K` of streamed, mozjpeg'd, [flying pug](https://raw.githubusercontent.com/tableflip/mozjpeg-stream/master/test/flying-pug.min.jpg):

![a svelte, 200K, mozjpeg pug](https://raw.githubusercontent.com/tableflip/mozjpeg-stream/master/test/flying-pug.min.jpg)

mozjpeg-stream wraps the most excellent: https://www.npmjs.com/package/mozjpeg by the [imagemin crew](https://github.com/imagemin)


which in turn wraps mozjpeg...

# More info on mozjpeg:
- https://blog.mozilla.org/research/2014/07/15/mozilla-advances-jpeg-encoding-with-mozjpeg-2-0/
- https://hacks.mozilla.org/2014/08/using-mozjpeg-to-create-efficient-jpegs/
- https://github.com/mozilla/mozjpeg/blob/7faa703ebf7360e5c0a37d71a74c293232998340/usage.txt#L68

----

A [(╯°□°）╯︵TABLEFLIP](https://tableflip.io) side project.