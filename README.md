# requires-port

[![Version npm](https://img.shields.io/npm/v/requires-port.svg?style=flat-square)](https://www.npmjs.com/package/requires-port)[![Build Status](https://img.shields.io/github/workflow/status/unshiftio/requires-port/CI/master?label=CI&style=flat-square)](https://github.com/unshiftio/requires-port/actions?query=workflow%3ACI+branch%3Amaster)[![Coverage Status](https://img.shields.io/coveralls/unshiftio/requires-port/master.svg?style=flat-square)](https://coveralls.io/r/unshiftio/requires-port?branch=master)

The module name says it all, check if a protocol requires a given port.

## Installation

This module is intended to be used with browserify or Node.js and is distributed
in the public npm registry. To install it simply run the following command from
your CLI:

```
npm install --save requires-port
```

## Usage

The module exports it self as function and requires 2 arguments:

1. The port number, can be a string or number.
2. Protocol, can be `http`, `http:` or even `https://yomoma.com`. We just split
   it at `:` and use the first result. We currently accept the following
   protocols:
   - `http`
   - `https`
   - `ws`
   - `wss`
   - `ftp`
   - `gopher`
   - `file`

It returns a boolean that indicates if protocol requires this port to be added
to your URL.

```js
'use strict';

var required = require('requires-port');

console.log(required('8080', 'http')) // true
console.log(required('80', 'http'))   // false
```

# License

MIT
