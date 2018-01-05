Video.js Sneakpeek
===================
A VideoJS plugin that enables showing a sneakpeek image on above the scrubber.

Using the Plugin
----------------
The plugin automatically registers itself when you include video.thumbnails.js in your page:

```html
<script src="dist/videojs-sneakpeek.min.js"></script>
```

You probably want to include the default stylesheet, too. It handles showing and hiding thumbnails while hovering over the progress bar and a quick animation during the transition:

```html
<link href="dist/sneakpeek.min.css" rel="stylesheet">
```

To activate the plugin, add it to your videojs settings object:

```javascript
var video = videojs('#video', {
  plugins: {
      sneakpeek: {
        width: 180,
        height: 100,
        basePath: 'http://your-image-host.com/'
      }
    }
  });
```

The thumbnails need to be added with a VTT file. For this file, the [specification used by JW Player](http://support.jwplayer.com/customer/portal/articles/1407439-adding-preview-thumbnails) applies.
The VTT file is added as a metadata track to the video object, for example:

```html
<track kind="metadata" src="oceans.vtt"></track>
```

Full object example:

```html
<video id="video"
       class="video-js vjs-default-skin"
       controls>
  <source src="video.mp4" type="video/mp4" />
  <track kind="metadata" src="oceans.vtt"></track>
</video>
```

Contributing
----------------

Edit any file in `/src`. Once done run `yarn build` to build the latest files to our `/dist` folder.
