# Anime4K (for JS)
Millisecond anime upscaling with fantastic quality using GLSL shaders.

Read more about how it works here: [https://github.com/bloc97/Anime4K](https://github.com/bloc97/Anime4K)

## How do i install it?
### In vanilla JS
Just load index.js from this repo.
### Using Webpack, Parcel, Etc.
Install it using `npm i --save anime4k`
and include it using `const Anime4K = require('anime4k')`

## How do i use it?
To create a new scaler, run `Anime4K.Scaler(gl)` where `gl` is a WebGL canvas context.
### Example
```js
// [For webpack, parcel, etc] Require Anime4K
const Anime4K = require('anime4k')

// Create a canvas
const canvas = document.createElement('canvas')
document.body.appendChild(canvas)

// Create the scaler
const scaler = Anime4K.Scaler(canvas.getContext('webgl'))

// Create an image to scale
const inputImg = new Image()

// When the image has loaded, scale it.
inputImg.onLoad = function() {
  scaler.inputImage(inputImg)
  scaler.resize(2.0, {}) // 2x scale
}

// Load the image
inputImg.src = 'some_image.png'
```
