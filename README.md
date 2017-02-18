# parse-hdr

Parses HDR (Radiance) files


## Usage

#### `hdrInfo = parseHDR(buffer)`

Parameters:  
`buffer` - Uint8Array or ArrayBuffer

Returned object properties:  
`shape` - an array representing `[width, height]` of the image  
`exposure` - exposure of the image  
`gamma` - gamma of the image  
`data` - floating point pixel array `[R, G, B, R, G, B, ..]` of `length = width * height * 3`  


## Example

```javascript
var parseHDR = require('parse-hdr')
var io = require('pex-io')
io.loadBinary(__dirname + '/garage.hdr', function (err, buffer) {
  var img = parseHDR(buffer)
  console.log(img.shape)    // [1024, 512]
  console.log(img.exposure) // 1
  console.log(img.gamma)    // 1
  console.log(img.data[1])  // 1.427, 1.066666, ...
})
```

## License

MIT, see [LICENSE.md](LICENSE.md) for details.
