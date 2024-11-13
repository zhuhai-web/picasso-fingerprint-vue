# picasso-fingerprint-vue

picasso fingerprint for vue usage

## Installation

```bash
npm install picasso-fingerprint-vue
```

## Usage

1. Simple usage

```javascript
import {canvasNormalHash} from 'picasso-fingerprint-vue'

let hash = canvasNormalHash()
console.log(hash)
```

2. use configuration

```js
import {picassoCanvas} from 'picasso-fingerprint-vue'

const params = {
    area: {
        width: 300,
        height: 300,
    },
    offsetParameter: 2001000001,
    fontSizeFactor: 1.5,
    multiplier: 15000,
    maxShadowBlur: 50,
};

// Number of shapes to draw. The higher the more costly it is.
// Can be used as a way to adjust the aggressiveness of the proof of work (POW)
const numShapes = 5;
const initialSeed = Math.floor(100 * Math.random());

const canvasValue = picassoCanvas(
    numShapes, initialSeed, params
);

console.log(canvasValue)
// canvasValue is a hash representing the result of the Picasso challenge, e.g.
// c24b4a72badc95284b337aa304be1438
```

## More info

* modify from [picasso-canvas-fingerprinting](https://www.npmjs.com/package/picasso-canvas-fingerprinting) for vue use