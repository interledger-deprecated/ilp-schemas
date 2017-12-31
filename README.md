# ILP Schemas [![npm][npm-image]][npm-url] [![circle][circle-image]][circle-url]

[npm-image]: https://img.shields.io/npm/v/ilp-schemas.svg?style=flat
[npm-url]: https://npmjs.org/package/ilp-schemas
[circle-image]: https://circleci.com/gh/interledgerjs/ilp-schemas.svg?style=shield
[circle-url]: https://circleci.com/gh/interledgerjs/ilp-schemas

> JSON Schemas describing various ILP related protocols and formats.

## Installation

``` sh
npm install --save ilp-schemas
```

## Schema Validator

This module does not contain a schema validator. We recommend using an open-source validator like [ajv](https://github.com/epoberezkin/ajv).

``` js

const schemas = require('ilp-schemas')
const Ajv = require('ajv')

// create validator
const ajv = new Ajv()

// add all schemas
Object.keys(schemas).forEach(name => ajv.addSchema(schemas[name], name))

// validate something
const isValid = ajv.validate('Transfer.json', myTransfer)

if (isValid) {
  console.info('all good!')
} else {
  console.error('not a valid transfer!')
  console.error(ajv.errors)
}
```
