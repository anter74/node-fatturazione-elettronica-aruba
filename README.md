# fatturazione-elettronica-aruba

[![License: MIT](https://img.shields.io/badge/License-MIT-brightgreen.svg)](https://opensource.org/licenses/MIT) ![build](https://api.travis-ci.org/andreafalzetti/node-fatturazione-elettronica-aruba.svg?branch=master) [![npm version](https://img.shields.io/npm/v/fatturazione-elettronica-aruba.svg?style=flat)](https://www.npmjs.com/package/fatturazione-elettronica-aruba) [![Coverage Status](https://coveralls.io/repos/github/andreafalzetti/node-fatturazione-elettronica-aruba/badge.svg?branch=master)](https://coveralls.io/github/andreafalzetti/node-fatturazione-elettronica-aruba?branch=master) [![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://reactjs.org/docs/how-to-contribute.html#your-first-pull-request)

Node.js client to integrate the Aruba API for electronic invoicing ("Fatturazione Elettronica") within your project.

Currently in beta version and under development until Aruba releases a final version of their API. The API of this module should be stable and you can start using it.

## Roadmap

-   Complete support for Notifications
-   Implement MonitorCheck API
-   Add any new feature introduces by Aruba last minute

## Links

* Aruba API docs: <https://fatturazioneelettronica.aruba.it/apidoc/docs.html>
* npm: <https://www.npmjs.com/package/fatturazione-elettronica-aruba>

## Requirements

This module calls the Aruba Fatturazione Elettronica API, therefore you need a valid set of credentials with their service in order to use this module.

## Install

```
npm install fatturazione-elettronica-aruba
```

## How to use

```js
const ArubaClient = require('fatturazione-elettronica-aruba');

const arubaClient = new ArubaClient();

await arubaClient.signIn({
  username: 'YOUR_ARUBA_USERNAME',
  password: 'YOUR_ARUBA_PASSWORD'
});

await arubaClient.uploadInvoice({ dataFile: 'BASE64_ENCODED_XML' });
```

## Examples

See the [examples](EXAMPLES.md) page for additional use cases and demos.

## API

<!-- Generated by documentation.js. Update this documentation by updating the source code. -->

#### Table of Contents

-   [ArubaClient](#arubaclient)
    -   [Parameters](#parameters)
    -   [signIn](#signin)
        -   [Parameters](#parameters-1)
    -   [refreshToken](#refreshtoken)
    -   [searchInvoice](#searchinvoice)
        -   [Parameters](#parameters-2)
    -   [getInvoiceNotifications](#getinvoicenotifications)
        -   [Parameters](#parameters-3)
    -   [uploadInvoice](#uploadinvoice)
        -   [Parameters](#parameters-4)

### ArubaClient

ArubaClient constructor

#### Parameters

-   `options` **[Object](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)?**
    -   `options.env` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)?** Aruba environment (demo or prod)

Returns **[Object](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)** Returns an instance of ArubaClient

#### signIn

Calls Aruba to generate a JWT that will be used for future calls

##### Parameters

-   `data` **[Object](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)**
    -   `data.username` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** Aruba username
    -   `data.password` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** Aruba password

Returns **[Promise](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Promise)** Resolves to an boolean if successful, or an object
                   containing the error message

#### refreshToken

Calls Aruba to refresh the JWT

Returns **[Promise](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Promise)** Resolves to an boolean if successful, or an object
                   containing the error message

#### searchInvoice

Search an invoice by username, filename, or id

##### Parameters

-   `data`   (optional, default `{}`)

Returns **[Promise](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Promise)** Resolves to an boolean if successful, or an object
                   containing the error message

#### getInvoiceNotifications

Get the invoice notifications

##### Parameters

-   `data`   (optional, default `{}`)

Returns **[Promise](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Promise)** Resolves to an boolean if successful, or an object
                   containing the error message

#### uploadInvoice

Calls Aruba to upload an invoice

##### Parameters

-   `data` **[Object](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)**  (optional, default `{}`)
    -   `data.dataFile` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** base64 encoded XML
    -   `data.signed` **[boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean)** leave false if you are not sure (optional, default `false`)
    -   `data.credential` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)?** signature creds (leave false if you are not sure)
    -   `data.domain` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)?** signature domain (leave false if you are not sure)

Returns **[Promise](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Promise)** Resolves with the uploadFileName if successfull

## License

`node-fattura-elettronica-aruba` is MIT licensed.
