# rc-upload
---

upload ui component for react

[![NPM version][npm-image]][npm-url]
[![npm download][download-image]][download-url]

[npm-image]: http://img.shields.io/npm/v/rc-upload.svg?style=flat-square
[npm-url]: http://npmjs.org/package/rc-upload
[download-image]: https://img.shields.io/npm/dm/rc-upload.svg?style=flat-square
[download-url]: https://npmjs.org/package/rc-upload

## Development

```
npm install
npm start
```

## Example

http://localhost:8000/examples/

online example: http://react-component.github.io/upload/examples/simple.html


## Feature

* support ie8,ie8+,chrome,firefox,safari

## install

[![rc-upload](https://nodei.co/npm/rc-upload.png)](https://npmjs.org/package/rc-upload)

## Usage

```js
var Upload = require('rc-upload');
var React = require('react');
React.render(<Upload />, container);
```

## API

### props

|name|type|默认值| 说明|
|-----|---|--------|----|
|name | string | file| file param post to server |
|action| string | | from action url |
|data| object | | other data object to post |
|accept | string | | input accept attribute |
|forceAjax | bool | | force to use ajax render. used for server render |
|multiple | boolean | false | only support ie10+|
|onStart | function| | start upload file |
|onError| function| | error callback |
|onSuccess | function | | success callback |
|onProgress | function || progress callback, only for modern browsers|
|beforeStart| function |null| before upload check, return a Promise, only for modern browsers|

#### onError arguments

1. `err`: request error message
2. `responce`: request responce, not support on iframeUpload
3. `file`: upload file object

### onSuccess arguments

1. `result`: request body
2. `file`: upload file


### IE8/9 Note

In iframe uploader way, the content-type of response should be `text/plain` or `text/html`.[referense](https://github.com/blueimp/jQuery-File-Upload/wiki/Setup#content-type-negotiation)

If the Page set document.domain, then server should output document.domain according to _documentDomain parameter.

```js
var ret = '';
if (postData._documentDomain) {
  ret += '<script>document.domain="'+postData._documentDomain+'";</script>';
}
this.body = ret + '{"url":"xx.jpq"}';
```

## License

rc-upload is released under the MIT license.
