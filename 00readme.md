## Setup

Generate `npm-browser.js` npm package bundle:

```sh
$ npm i
$ npm run build
```

## Run successful case

```sh
$ node case-success.mjs
```

Accessed from nodejs helia to content on browser helia at first, the browser helia can access content on the nodejs helia.

## Run halt case

```sh
$ node case-halt.mjs
```

The browser helia halt to access content on the nodejs helia at first.
