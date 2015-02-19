nw-shot
---
> Create screenshots using [nw.js](https://github.com/nwjs/nw.js)

## Install

```shell
npm install nw
```


## Usage

```js
var fs = require('fs');
var screenshot = require('nw-shot');

screenshot({
  url : 'http://google.com',
  width : 1024,
  height : 768
}).pipe(fs.createWriteStream('./out.png'));
```

#### screenshot(options)

##### delay

Type: `number` *(seconds)*
Default: `0`

Delay capturing the screenshot.

Useful when the site does things after load that you want to capture.

##### format

Type: `string` png|jpeg
Default: `png`

Specify the image type fot he screenshot

##### width

Type: `int`
Default: `0`

Specify the with of the browser window

##### height

Type: `int`
Default: `0`

Specify the height of the browser window


##### eval

Type: `string`|`array<string>`
Default: `undefined`

Evaluate JavaScript in browser window context, if supplied
as an array of strings, each string will be evaluated and 
a shot will be taken after each evaluation. The result will
stream images seperated by new lines. 

Protip: use the [`line-stream`](http://npmjs.org/line-stream) 
module to group image data into a single buffer that can
be streamed in one go.

##### encoding

Type: `string`  base64|binary
Default: 'binary'




## Troubleshooting

If you like to use this on travis or with a framebuffer like xvfb than you need to set the environment variable
`NODESCREENSHOT_SHOW` to `1`. (`export NWSHOT_SHOW`).
See this [`.travis.yml`](https://github.com/FWeinb/node-webkit-screenshot/blob/master/.travis.yml) for more information



