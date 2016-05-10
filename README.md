[![npm](http://img.shields.io/npm/v/gulp-file-process.svg?style=flat-square)](https://www.npmjs.com/package/gulp-file-process)
![npm](http://img.shields.io/npm/l/gulp-file-process.svg?style=flat-square)
[![Dependency Status](https://david-dm.org/aliaksandr-pasynkau/gulp-file-process.svg?style=flat-square)](https://david-dm.org/aliaksandr-pasynkau/gulp-file-process)
[![devDependency Status](https://david-dm.org/aliaksandr-pasynkau/gulp-file-process/dev-status.svg?style=flat-square)](https://david-dm.org/aliaksandr-pasynkau/gulp-file-process#info=devDependencies)

# gulp-file-process
Process file with pipe interface without creating special task

## Getting started 

ES2015, NODE 5+

To install `gulp-file-process` from npm, run:
```shell
npm install gulp-file-process --save-dev
```

## Use the library:

```javascript
const gulpFileProcess = require('gulp-file-process');

gulp.task('someTask', () =>
  gulp.src('**/*')
    .pipe(gulpFileProcess({
      process: (file, content) => content.replace('some', 'any') // do something useful
      run: (file) => { console.log(file.path); } // do something else, for instance notify user about processed file
    }))
    .pipe(gulp.dest('/some/path'))
);

```

## Options

### options.read(file)
Type `Function`, Default `(file) => file.contents.toString('utf8')`

This function can returns promise

### options.write(file, processedContent)
Type `Function`, Default `(file, content) => { file.contents = new Buffer(content, 'utf8'); }`

This function can returns promise

### options.run(file)
Type `Function`, Default `null`

This function can returns promise

### options.process(file, content)
Type `Boolean`, Default `false`

This function can returns promise

### Enjoy!

## Support
If you have any problems, you cached a bug, or you have any suggestion - please [find an existing issue or create new](https://github.com/aliaksandr-pasynkau/gulp-file-process/issues)

## Contributing
If you want to develop this library do not be shy - Do that! [How to contribute open-source projects](https://guides.github.com/activities/contributing-to-open-source/)
