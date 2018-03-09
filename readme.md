# react-mp3-recorder ([demo](https://transitive-bullshit.github.io/react-mp3-recorder/))

> Simple microphone recorder for React that captures mp3 audio.

[![NPM](https://img.shields.io/npm/v/react-mp3-recorder.svg)](https://www.npmjs.com/package/react-mp3-recorder) [![JavaScript Style Guide](https://img.shields.io/badge/code_style-standard-brightgreen.svg)](https://standardjs.com)

[![Demo](https://raw.githubusercontent.com/transitive-bullshit/react-mp3-recorder/master/media/demo.gif)](https://transitive-bullshit.github.io/react-mp3-recorder/)

## Intro

This module exports a simple recording button for React which uses the [wasm-optimized](https://hackernoon.com/creating-webassembly-powered-library-for-modern-web-846da334f8fc) [vmsg](https://github.com/Kagami/vmsg) library under the hood to record and encode an MP3 directly from the microphone.

Capturing MP3 audio is much more efficient and practical than using the [MediaStream](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream_Recording_API) recording API directly.

## Install

```bash
npm install --save react-mp3-recorder
# or
yarn add react-mp3-recorder
```

## Usage

```jsx
import React, { Component } from 'react'

import Recorder from 'react-mp3-recorder'

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

## License

- [react-mp3-recorder](https://github.com/transitive-bullshit/react-mp3-recorder) is licensed under [MIT](https://opensource.org/licenses/MIT) © [transitive-bullshit](https://github.com/transitive-bullshit).
- [vmsg](https://github.com/Kagami/vmsg) is licensed under [CC0](https://github.com/Kagami/vmsg/blob/master/COPYING).
- LAME is licensed under [LGPL](https://github.com/Kagami/lame-svn/blob/master/lame/COPYING).
- MP3 patents seem to have [expired since April 23, 2017](https://en.wikipedia.org/wiki/LAME#Patents_and_legal_issues).

This module was bootstrapped with [create-react-library](https://github.com/transitive-bullshit/create-react-library).
