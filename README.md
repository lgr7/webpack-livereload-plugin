# webpack-livereload-plugin

[![Build Status](https://travis-ci.org/statianzo/webpack-livereload-plugin.svg?branch=master)](https://travis-ci.org/statianzo/webpack-livereload-plugin)

LiveReload when running `webpack --watch`

<a target='_blank' rel='nofollow' href='https://app.codesponsor.io/link/AitzkUqcdsSnujfFtmVhTLXR/statianzo/webpack-livereload-plugin'>
  <img alt='Sponsor' width='888' height='68' src='https://app.codesponsor.io/embed/AitzkUqcdsSnujfFtmVhTLXR/statianzo/webpack-livereload-plugin.svg' />
</a>

## Installation

Install the package

```
npm install --save-dev webpack-livereload-plugin
```

Add the plugin to your webpack config

```js
// webpack.config.js

var LiveReloadPlugin = require('webpack-livereload-plugin');

module.exports = {
  plugins: [
    new LiveReloadPlugin(options)
  ]
}
```

Add a script tag to your page pointed at the livereload server

```html
<script src="http://localhost:35729/livereload.js"></script>
```


## Options

- `protocol` - (Default: protocol of the page, either `http` or `https`) Protocol for livereload `<script>` src attribute value
- `port` - (Default: 35729) The desired port for the livereload server
- `hostname` - (Default: hostname of the page, like `localhost` or `10.0.2.2`) The desired hostname for the appended
               `<script>` (if present) to point to
- `appendScriptTag` - (Default: false) Append livereload `<script>`
                   automatically to `<head>`.
- `ignore` - (Default: `null`) RegExp of files to ignore. Null value means
  ignore nothing.

## Why?

Yes, there's already `webpack-dev-server` that handles live reloading
and more complex scenarios. This project aims to solve the case where
you want assets served by your app server, but still want reloads
triggered from webpack's build pipeline.

## HTTPS

If you set `key`, `cert`, or `pfx` options, they'll get passed through to
[tiny-lr as options](https://github.com/mklabs/tiny-lr#options) and it will
serve over HTTPS. You'll also also set `protocol` to `https`.
