# dollar.js - Bitdollar JavaScript API

[![Join the chat at https://gitter.im/bitdollar-network/dollar.js](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/bitdollar-network/dollar.js?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

[![npm](https://img.shields.io/npm/dm/@bitdollar/dollar.svg)](https://www.npmjs.com/package/@bitdollar/dollar)

This is the Bitdollar Javascript API
which connects to Dollar protocol.


You need to run a local or remote Bitdollar node to use this library.

## Installation

### Node

```bash
npm install @bitdollar/dollar
```

### Yarn

```bash
yarn add @bitdollar/dollar
```

### Meteor

*Note*: works only in the Browser for now. (PR welcome).

```bash
meteor add bitdollar:dollar
```

### In the Browser

Use the prebuild ``dist/dollar.min.js``, or
build using the [dollar.js][repo] repository:

```bash
npm run-script build
```

Then include `dist/dollar.js` in your html file.
This will expose `Dollar` on the window object.

## Usage

```js
// Currently not supporting NodeJS, but supporting use as vanilla JS
// Please move and use the dist/dollar-signer.min.js file.

// require('@bitdollar/dollar') only necessary for NodeJS
var Dollar = require('@bitdollar/dollar'); // currently not supporting nodejs

// Moving dist/dollar.min.js to your folder and after starting dollar client,
var dollar = new Dollar(new Dollar.providers.HttpProvider('http://localhost:8545'));
console.log(dollar);

```

Additionally you can set a provider using `dollar.setProvider()` (e.g. WebsocketProvider)

```js
dollar.setProvider('http://localhost:8545');
// Or
dollar.setProvider(new Dollar.providers.HttpProvider('http://localhost:8545'));
```

There you go, now you can use it:

```js
dollar.btd.getAccounts()
.then(console.log);
```


**Please note:** If you have any issue with `dollar.js` please create an issue here.

## Documentation

Documentation can be found at [read the docs][docs]


## Building

### Requirements

* [Node.js](https://nodejs.org)
* npm

```bash
sudo apt-get update
sudo apt-get install nodejs
sudo apt-get install npm
```

### Building (gulp)

Build only the dollar.js package

```bash
npm run-script build
```

Or build all sub packages as well

```bash
npm run-script build-all
```

This will put all the browser build files into the `dist` folder.


### Testing (mocha)

```bash
npm test
```

### Contributing

- All contributions have to go into develop branch
- Please follow the code style of the other files.
- Please use 4 spaces as tabs.

### Community
 - [Gitter](https://gitter.im/bitdollar-network/dollar.js?source=orgpage)
 - [Forum](https://forum.bibicle.com/categories/dollar-js)

[repo]: https://github.com/bitdollar-network/dollar.js
[docs]: http://dollarjs.readthedocs.io/
[npm-image]: https://badge.fury.io/js/@bitdollar/dollar.png
[npm-url]: https://npmjs.org/package/@bitdollar/dollar
[dep-image]: https://david-dm.org/bitdollar/dollar.js.svg
[dep-url]: https://david-dm.org/bitdollar/dollar.js
[dep-dev-image]: https://david-dm.org/bitdollar/dollar.js/dev-status.svg
[dep-dev-url]: https://david-dm.org/bitdollar/dollar.js#info=devDependencies
