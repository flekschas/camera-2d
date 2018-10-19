# 2D Camera

[![npm version](https://img.shields.io/npm/v/camera-2d-simple.svg)](https://www.npmjs.com/package/camera-2d-simple)
[![stability experimental](https://img.shields.io/badge/stability-experimental-orange.svg)](https://nodejs.org/api/documentation.html#documentation_stability_index)
[![build status](https://travis-ci.org/flekschas/camera-2d.svg?branch=master)](https://travis-ci.org/flekschas/camera-2d)
[![gzipped size](https://img.shields.io/badge/gzipped%20size-0.9%20KB-6ae3c7.svg)](https://unpkg.com/camera-2d-simple)
[![code style prettier](https://img.shields.io/badge/code_style-prettier-ff69b4.svg)](https://github.com/prettier/prettier)
[![demo](https://img.shields.io/badge/demo-online-6ae3c7.svg)](https://flekschas.github.io/regl-scatterplot/)

> Simple camera built on top of gl-matrix for 2D scenes. Heavily inspired by [Mikola's Orbit Camera](https://github.com/mikolalysenko/orbit-camera).

Also see:

- [canvas-camera-2d](https://github.com/flekschas/canvas-camera-2d) for attaching the camera to a canvas object
- [webgl-scatterplot](https://github.com/flekschas/webgl-scatterplot) for an application

## Install

```
npm install camera-2d-simple
```

## API

```javascript
import createCamera from "camera-2d-simple";
```

### `const camera = createCamera(target = [0, 0], distance = 1)`

Creates a 2d camera looking at `target` from a certain `distance`.

- `target` is the 2d vector the camera is looking at.
- `distance` is the distance between the target and the camera.

**Returns** A new 2d camera object

### `camera.lookAt(target = [0, 0], distance = 1)`

Move the camera to look at the new position.

### `camera.pan(translation)`

Moves the center of the camera by `translation`. Note that translation must be an array of length 2.

### `camera.zoom(delta)`

Zooms in or out by some amount. I.e., the new distance is defined as `distance * delta`.

### `camera.view([out])`

Returns the current view matrix associated to the camera.

### `camera.position`

Is an array of length 3 comprised of the target (x, y) and distance (z) of the camera.

### `camera.transformation`

Is the current transformation `mat3` associated to the camera.
