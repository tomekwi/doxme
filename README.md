# doxme

[![build status](https://secure.travis-ci.org/tmcw/doxme.png)](http://travis-ci.org/tmcw/doxme)

create markdown docs for dox output


### `doxme(dox, readme, package, travis)`

A [Markdown](http://daringfireball.net/projects/markdown/) formatter
for [dox](https://github.com/tj/dox). Takes dox's JSON output as stdin
and writes Markdown to stdout.

## CLI Usage

    dox -r < index.js | doxme

## See Also

* [gulp-doxme](https://github.com/tomekwi/gulp-doxme) runs doxme within a
  [Gulp](http://gulpjs.com/) pipeline


### Parameters

| parameter | type    | description                                      |
| --------- | ------- | ------------------------------------------------ |
| `dox`     | Object  | the output of dox as a parsed JSON object        |
| `readme`  | boolean | whether to output a readme or just docs          |
| `package` | Object  | a parsed package.json                            |
| `travis`  | boolean | whether to output a travis badge along with docs |


### Example

```js
var fs = require('fs');
var dox = require('dox');
var doxme = require('doxme');

var sourceCode = fs.readFileSync('./index.js', 'utf8');
var documentation = doxme(dox.parseComments(sourceCode));
```


**Returns** `String`, documentation

## Installation

Requires [nodejs](http://nodejs.org/).

```sh
$ npm install doxme
```

## Tests

```sh
$ npm test
```


