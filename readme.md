# react-recorder ([demo](https://transitive-bullshit.github.io/react-recorder/))

> Simple microphone recorder for React that captures mp3 audio.

[![NPM](https://img.shields.io/npm/v/react-recorder.svg)](https://www.npmjs.com/package/react-recorder) [![JavaScript Style Guide](https://img.shields.io/badge/code_style-standard-brightgreen.svg)](https://standardjs.com)

[![Demo](https://raw.githubusercontent.com/transitive-bullshit/react-recorder/master/media/demo.gif)](https://transitive-bullshit.github.io/react-recorder/)

## Intro

This module exports a simple recording button for React which uses the [wasm-optimized](https://hackernoon.com/creating-webassembly-powered-library-for-modern-web-846da334f8fc) [vmsg](https://github.com/Kagami/vmsg) library under the hood to record and encode an MP3 directly from the microphone.

Capturing MP3 audio is much more efficient and practical than using the [MediaStream](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream_Recording_API) recording API directly.

## Install

```bash
npm install --save react-recorder
# or
yarn add react-recorder
```

## Usage

```jsx
import React, { Component } from 'react'

import Recorder from 'react-recorder'

export default class App extends Component {
  render () {
    return (
      <Recorder
        onRecordingComplete={this._onRecordingComplete}
        onRecordingError={this._onRecordingError}
      />
    )
  }

  _onRecordingComplete = (blob) => {
    console.log('recording', blob)
  }

  _onRecordingError = (err) => {
    console.log('recording error', err)
  }
}
```
