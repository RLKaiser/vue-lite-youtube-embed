# vue-lite-youtube-embed

[![npm version](https://badge.fury.io/js/vue-lite-youtube-embed.svg)](https://badge.fury.io/js/vue-lite-youtube-embed)
[![bundle size](https://badgen.net/bundlephobia/minzip/vue-lite-youtube-embed)](https://bundlephobia.com/result?p=vue-lite-youtube-embed)

A private by default, faster and cleaner YouTube embed component for Vue applications.

Port of [React Lite YouTube Embed](https://github.com/ibrahimcesar/react-lite-youtube-embed) to a Vue Component. Provide videos with a supercharged focus on visual performance. An ["Adaptive Loading"](https://www.youtube.com/watch?v=puUPpVrIRkc) way to handle iframes for YouTube.

## Installation

Vue 3:

```bash
yarn add vue-lite-youtube-embed
```

Vue 2:

```bash
yarn add vue-lite-youtube-embed @vue/composition-api
```

## Usage

```html
<template>
  <LiteYouTubeEmbed 
    id="dQw4w9WgXcQ"
    title="Rick Astley - Never Gonna Give You Up (Official Music Video)"
  />
</template>

<script>
import { defineComponent } from 'vue'
import LiteYouTubeEmbed from 'vue-lite-youtube-embed'
import 'vue-lite-youtube-embed/dist/style.css'

export default defineComponent({
    components: { LiteYouTubeEmbed }
})
</script>
```

## Props

Only two props are required to work: `id` from the YouTube you want to render and `title`

| Prop   |      Type      |  Description |
|----------|:--------:|------------|
| **id** |  string | Id of the video or playlist |
| **title** |    string   | Video title. Always provide a title for iFrames: https://dequeuniversity.com/tips/provide-iframe-titles Help the web be accessible ;) #a11y |
| announce |    string   | Default: `Watch`. This will be passed to the button in order to be announced to the final user as in `Clickable Watch, ${title}, button` , customize to match your own language #a11y #i18n |
| activeClass | string | Pass the string class for the active state |
| adNetwork | boolean | Default: `false`  To preconnect or not to doubleclick addresses called by YouTube iframe (the adnetwork from Google) |
| cookie | boolean |    Default: `false` Connect to YouTube via the Privacy-Enhanced Mode using https://www.youtube-nocookie.com You should opt-in to allow cookies|
| iframeClass | string |    Pass the string class for the own iFrame |
| muted | boolean |    If the video has sound or not. Required autoplay `true` to work |
| params | string |    any params you want to pass to the URL in the iFrame. Two important things to notice: You can assume you just need to add the params, we already setup for you, so you should write `start=1150` and not `?start=1150` or `&start=1150`. You can place more params but it will need to fully form: `start=1150&other=value&another=value`. First, when you share a YouTube url the param of time is just `t`, but the embed needs `start`.|
| playerClass | string | Pass the string class for the player, once you can customize it |
| playlist | boolean |    Use `true` when your id be from a playlist |
| playlistCoverId | string | The ids for playlists did not bring the cover in a pattern to render so you'll need pick up a video from the playlist (or in fact, whatever id) and use to render the cover. There's a programmatic way to get the cover from YouTube API v3 but the aim of this component is do not make any another call and reduce requests and bandwidth usage as much as possibe  |
| poster | string. One of `default` `mqdefault`  `hqdefault` `sddefault` `maxresdefault` |   Defines the image size to call on first render as poster image. See: https://stackoverflow.com/questions/2068344/how-do-i-get-a-youtube-video-thumbnail-from-the-youtube-api |
| wrapperClass | string |   Pass the string class that wraps the iFrame |

## Events

- **iframeAdded** - Fired when iframe is added.

## Credits

- [react-lite-youtube-embed](https://github.com/ibrahimcesar/react-lite-youtube-embed) - A private by default, faster and cleaner YouTube embed component for React applications.
- [vue-demi](https://github.com/vueuse/vue-demi/) - Creates Universal Library for Vue 2 & 3.
- [lite-youtube-embed](https://github.com/paulirish/lite-youtube-embed) - A faster youtube embed.
- [lite-youtube-embed](https://github.com/wobsoriano/vue-lite-youtube-embed) - A private by default, faster and cleaner YouTube embed component for React applications.

## License

MIT License © 2021 [Robert Soriano](https://github.com/wobsoriano)