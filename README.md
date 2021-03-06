<p align="center">
  <a href="https://carbon.io" >
    <img width="50%" alt="Carbon.io" src="https://carbon.io/images/logo--dark--static.svg" >
  </a>
</p>

<p align="center">
  <a href="https://travis-ci.org/carbon-io/carbon-io" >
    <img alt="Travis build status" src="https://img.shields.io/travis/carbon-io/carbon-io.svg?style=flat-square">
  </a>
  
  <a href="https://www.npmjs.com/package/carbon-io" >
    <img alt="npm Version" src="https://img.shields.io/npm/v/carbon-io.svg?style=flat-square">
  </a>
  
  <a href="https://www.npmjs.com/package/carbon-io" >
    <img alt="npm downloads" src="https://img.shields.io/npm/dm/carbon-io.svg?style=flat-square">
  </a>
  
  <a href="https://www.npmjs.com/package/carbon-io" >
    <img alt="supported node versions" src="https://img.shields.io/node/v/carbon-io.svg?style=flat-square">
  </a>
  
  <a href="./LICENCE.txt" >
    <img alt="MIT License" src="https://img.shields.io/github/license/carbon-io/carbon-io.svg?style=flat-square">
  </a>
</p>

Carbon.io is an application framework based on Node.js and MongoDB for building command line programs, microservices, and APIs.

With Carbon.io you can create simple, database-centric microservices with virtually no code. At the same time Carbon.io is designed to let you under the hood and allows you to write highly customized APIs much like you would with lower-level libraries such as Express.js.

## Quickstart

To install:

```
$ npm install carbon-io
```

Copy the following code into `service.js`:

```js
var carbon = require('carbon-io')

var o  = carbon.atom.o(module).main
var __ = carbon.fibers.__(module)

__(function() {
  module.exports = o({
    _type: carbon.carbond.Service,
    port: 8888,
    endpoints: {
      hello: o({
        _type: carbon.carbond.Endpoint,
        get: function(req) {
          return { msg: "Hello world!" }
        }
      })
    }
  })
})
```

This will create a Carbon.io service which will respond with "Hello world!" on the `/hello` endpoint. Run the service with:

```
$ node service
```

And test it using:

```
$ curl localhost:8888/hello
```

## Documentation

Interested in getting started with Carbon.io? [__Check out our detailed documentation on the Carbon.io website.__](https://docs.carbon.io)

## Contributing

Interested in contributing to Carbon.io? We love to receive new contributions! There are many ways to contribute, from writing tutorials or blog posts, improving the documentation, submitting bug reports and feature requests or writing code which can be incorporated into Carbon.io itself.

Check out our [CONTRIBUTING.md](./CONTRIBUTING.md) for tips on how to get started!

## License

[MIT License](./LICENSE.txt)
