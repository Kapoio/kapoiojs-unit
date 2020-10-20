## kapoiojs-unit

<div>
  <!-- Dependency Status -->
  <a href="https://david-dm.org/kapoiojs/kapoiojs-unit">
    <img src="https://david-dm.org/kapoiojs/kapoiojs-unit.svg"
    alt="Dependency Status" />
  </a>

  <!-- devDependency Status -->
  <a href="https://david-dm.org/kapoiojs/kapoiojs-unit#info=devDependencies">
    <img src="https://david-dm.org/kapoiojs/kapoiojs-unit/dev-status.svg" alt="devDependency Status" />
  </a>

  <!-- Build Status -->
  <a href="https://travis-ci.org/kapoiojs/kapoiojs-unit">
    <img src="https://travis-ci.org/kapoiojs/kapoiojs-unit.svg"
    alt="Build Status" />
  </a>

  <!-- NPM Version -->
  <a href="https://www.npmjs.org/package/kapoiojs-unit">
    <img src="http://img.shields.io/npm/v/kapoiojs-unit.svg"
    alt="NPM version" />
  </a>

  <!-- Test Coverage -->
  <a href="https://coveralls.io/r/kapoiojs/kapoiojs-unit">
    <img src="https://coveralls.io/repos/github/kapoiojs/kapoiojs-unit/badge.svg" alt="Test Coverage" />
  </a>

  <!-- Javascript Style -->
  <a href="http://airbnb.io/javascript/">
    <img src="https://img.shields.io/badge/code%20style-airbnb-brightgreen.svg" alt="js-airbnb-style" />
  </a>
</div>

<br />

A simple module for handling Kapoio unit convertion.

## Install

```
npm install --save kapoiojs-unit
```

## Usage

```js
const unit = require('kapoiojs-unit');

var val1 = unit.toWei(249824778, 'kappa');

// result <BN ...> 249824778000000000000000000

var val2 = unit.fromWei('249824778000000000000000000', 'kappa');

// result '249824778'
```

## About

A port from the `web3.js` library, that just handles the unit convertion between the various types of Ethereum currency units.

Note, the `toWei` returns a BN instance while `fromWei` always returns a string number.

## Amorphic Data Formatting

`kapoiojs-unit` uses the [number-to-bn](http://github.com/silentcicero/number-to-bn) module to format all number values (hex or otherwise) into digestable BN.js number instances.

## Methods Available & Objects

```
unitMap         { unitName: singleUnitWeiValue, ... }
getValueOfUnit  <Function (unit) : (BN)>
toWei           <Function (value, unit) : (BN)>
fromWei         <Function (value, unit) : (String)>
```

## Supported Units

```
'wei':          '1',
'kwei':         '1000',
'Kwei':         '1000',
'babbage':      '1000',
'femtokappa':   '1000',
'mwei':         '1000000',
'Mwei':         '1000000',
'lovelace':     '1000000',
'picokappa':    '1000000',
'gwei':         '1000000000',
'Gwei':         '1000000000',
'shannon':      '1000000000',
'nanokappa':    '1000000000',
'nano':         '1000000000',
'szabo':        '1000000000000',
'microkappa':   '1000000000000',
'micro':        '1000000000000',
'finney':       '1000000000000000',
'millikappa':   '1000000000000000',
'milli':        '1000000000000000',
'kappa':        '1000000000000000000',
'kkappa':       '1000000000000000000000',
'grand':        '1000000000000000000000',
'mkappa':       '1000000000000000000000000',
'gkappa':       '1000000000000000000000000000',
'tkappa':       '1000000000000000000000000000000'
```

## Why BN.js?

`kapoiojs` has made a policy of using `BN.js` accross all of our modules. Here are some reasons why:

  1. Lighter than alternatives (BigNumber.js)
  2. Faster than most alternatives, see [benchmarks](https://github.com/indutny/bn.js/issues/89)
  3. Used by the Ethereum foundation across all [`kapoiojs`](https://github.com/kapoiojs) repositories
  4. Is already used by a critical JS dependency of many kapoio packages, see package [`elliptic`](https://github.com/indutny/elliptic)
  5. Does not support decimals or floats (for greater precision), remember, the Ethereum blockchain cannot and will not support float values or decimal numbers

## Contributing

Please help better the ecosystem by submitting issues and pull requests to default. We need all the help we can get to build the absolute best linting standards and utilities. We follow the AirBNB linting standard and the unix philosophy.

## Guides

You'll find more detailed information on using `kapoiojs-unit` and tailoring it to your needs in our guides:

- [User guide](docs/user-guide.md) - Usage, configuration, FAQ and complementary tools.
- [Developer guide](docs/developer-guide.md) - Contributing to `kapoiojs-unit`, writing coverage and updates.

## Help out

There is always a lot of work to do, and will have many rules to maintain. So please help out in any way that you can:

- Create, enhance, and debug kapoiojs rules (see our guide to ["Working on rules"](./github/CONTRIBUTING.md)).
- Improve documentation.
- Chime in on any open issue or pull request.
- Open new issues about your ideas for making `kapoiojs-unit` better, and pull requests to show us how your idea works.
- Add new tests to *absolutely anything*.
- Create or contribute to ecosystem tools, like modules for encoding or contracts.
- Spread the word.

Please consult our [Code of Conduct](CODE_OF_CONDUCT.md) docs before helping out.

We communicate via [issues](https://github.com/kapoiojs/kapoiojs-unit/issues) and [pull requests](https://github.com/kapoiojs/kapoiojs-unit/pulls).

## Important documents

- [Changelog](CHANGELOG.md)
- [Code of Conduct](CODE_OF_CONDUCT.md)
- [License](https://raw.githubusercontent.com/kapoiojs/kapoiojs-unit/master/LICENSE)

## Licence

This project is licensed under the MIT license, Copyright (c) 2016 Nick Dodson. For more information see LICENSE.md.

```
The MIT License

Copyright (c) 2016 Nick Dodson. nickdodson.com

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
```
