# sync-bower [![NPM version](https://img.shields.io/npm/v/sync-bower.svg?style=flat)](https://www.npmjs.com/package/sync-bower) [![NPM monthly downloads](https://img.shields.io/npm/dm/sync-bower.svg?style=flat)](https://npmjs.org/package/sync-bower)  [![NPM total downloads](https://img.shields.io/npm/dt/sync-bower.svg?style=flat)](https://npmjs.org/package/sync-bower) [![Linux Build Status](https://img.shields.io/travis/jonschlinkert/sync-bower.svg?style=flat&label=Travis)](https://travis-ci.org/jonschlinkert/sync-bower)

> Sync package.json with bower.json.

## Install

Install with [npm](https://www.npmjs.com/):

```sh
$ npm install --save sync-bower
```

### API

```js
var fs = require('fs');
var sync = require('sync-bower');
var pkg = require('./package.json');
var bower = require('./bower.json');

var updatedBower = sync(pkg, bower);

fs.writeFile('bower.json', updatedBower, function(err) {
  if (err) console.log(err);
});
```

## CLI

Run `sync-bower` in the command line to update bower.json.

```sh
$ sync-bower
```

* If `bower.json` exists, it will be updated with values in package.json.
* If `bower.json` does not exist, you will be asked if you want to create one.

### Commands

#### bower

Create a bower.json file and/or update the existing bower.json without prompting you for feedback.

```sh
$ sync-bower bower
```

#### diff

See a visual diff of proposed changes between package.json and bower.json. Does not modify any files.

```sh
$ sync-bower diff
```

**Example output**

<img width="669" alt="screen shot 2016-05-13 at 12 50 11 pm" src="https://cloud.githubusercontent.com/assets/383994/15255318/54996aa2-1909-11e6-99a3-90f6129dd7da.png">

## properties

The [following fields](https://github.com/bower/bower.json-spec) from package.json are used:

* `name`: **required**
* `description`: recommended
* `license`: recommended
* `main`: recommended
* `ignore`: recommended
* `keywords`: recommended

These fields are also included, but are considered optional by bower:

* `repository`
* `homepage`
* `authors`
* `dependencies`
* `devDependencies`

Pull requests or feature requests are welcome!

## About

### Related projects

* [gulp-normalize-pkg](https://www.npmjs.com/package/gulp-normalize-pkg): Gulp plugin for normalize-pkg. | [homepage](https://github.com/jonschlinkert/gulp-normalize-pkg "Gulp plugin for normalize-pkg.")
* [normalize-pkg](https://www.npmjs.com/package/normalize-pkg): Normalize values in package.json using the map-schema library. | [homepage](https://github.com/jonschlinkert/normalize-pkg "Normalize values in package.json using the map-schema library.")
* [sync-pkg](https://www.npmjs.com/package/sync-pkg): CLI to sync only basic properties from package.json to bower.json. | [homepage](https://github.com/jonschlinkert/sync-pkg "CLI to sync only basic properties from package.json to bower.json.")

### Contributing

Pull requests and stars are always welcome. For bugs and feature requests, [please create an issue](../../issues/new).

Please read the [contributing guide](.github/contributing.md) for advice on opening issues, pull requests, and coding standards.

### Building docs

_(This project's readme.md is generated by [verb](https://github.com/verbose/verb-generate-readme), please don't edit the readme directly. Any changes to the readme must be made in the [.verb.md](.verb.md) readme template.)_

To generate the readme, run the following command:

```sh
$ npm install -g verbose/verb#dev verb-generate-readme && verb
```

### Running tests

Running and reviewing unit tests is a great way to get familiarized with a library and its API. You can install dependencies and run tests with the following command:

```sh
$ npm install && npm test
```

### Author

**Jon Schlinkert**

* [github/jonschlinkert](https://github.com/jonschlinkert)
* [twitter/jonschlinkert](https://twitter.com/jonschlinkert)

### License

Copyright © 2017, [Jon Schlinkert](https://github.com/jonschlinkert).
Released under the [MIT License](LICENSE).

***

_This file was generated by [verb-generate-readme](https://github.com/verbose/verb-generate-readme), v0.4.3, on March 16, 2017._