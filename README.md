# media-play-enabler

[![License][]](https://opensource.org/licenses/Apache-2.0)
[![Build Status]](https://github.com/gunta/media-play-enabler/actions/workflows/ci.yml)
[![NPM Package]](https://npmjs.org/package/media-play-enabler)
[![Code Coverage]](https://codecov.io/gh/gunta/media-play-enabler)
[![semantic-release]](https://github.com/semantic-release/semantic-release)

[license]: https://img.shields.io/badge/License-Apache%202.0-blue.svg
[build status]: https://github.com/gunta/media-play-enabler/actions/workflows/ci.yml/badge.svg
[npm package]: https://img.shields.io/npm/v/media-play-enabler.svg
[code coverage]: https://codecov.io/gh/gunta/media-play-enabler/branch/master/graph/badge.svg
[semantic-release]: https://img.shields.io/badge/%20%20%F0%9F%93%A6%F0%9F%9A%80-semantic--release-e10079.svg

> Enables **video play programmatically** on modern browsers that _require user input events_

## Why

On most **mobile** device browsers, calling `video.play()` is only allowed from **inside** gesture events such as `onclick` or `touchend`.

> iOS Safari, iOS Chrome

---

On most **desktop** modern browsers, calling `video.play()` is only allowed after the user has done any **explicit** interaction with the DOM, such as `click` or `mousedown` somewhere at least once.
Events such as `mouseover` are not enough.

> Desktop Chrome >= 66, Android Chrome, Windows Edge

---

On **these browsers**, calling `video.play()` works without any interaction _only_ if the video is either **muted** or the video **does not have an audio track**.

> iOS Safari, iOS Chrome

---

On **the rest**, it doesn't work even without audio.

> Desktop Chrome, Android Chrome, Windows Edge

## How it works

1. It creates a video element (or reuses a provided one)
2. Its instance will be reused for all videos played _(this is required for mobile since the )_
3. It attaches a mobile `touchstart` or a desktop `mousedown` event to `document` in order to enable the first `video.play()` of a blank video.
4. It sends events to know when we can play videos
5. Changing videos is done by changing the `video source`, not the `video element`.

## Usage

1. Create a MediaPlayEnabler instance as early as possible (in order to have more chances to intercept any user gesture).
2. Call MediaPlayEnabler `.canPlay()` to know if a video can be played.
3. Listen to `videocanplay` event to know when a video can be played.
4. Change source of the MediaPlayEnabler `.source` instance to change videos.

## Install

```shell
npm install media-play-enabler
```

## Use

```typescript
import { MediaPlayEnabler } from 'media-play-enabler'
```
