# Application Cache plugin for Webpack3

## Usage

```javascript

var AppCachePlugin = require('appcache-webpack-plugin-client');

module.exports = {
  plugins: [
      new AppCachePlugin({
      cache: ['../dist'],
      network: null, // No network access allowed!
      fallback: ['index.html', 'error.html'],
      settings: ['prefer-online'],
      exclude: [/.*$/], // Exclude file.txt and all .js files
      output: '../cache/manifest.appcache',
      outpath:'../', // Relative path
      excludePath:''  // Remove matching file url
    })
  ]
}
```

```
CACHE MANIFEST
# a385df8c0b9e88367403

CACHE:
../dist/0.js
../dist/0.min.js
../dist/1.js
../dist/img/culb_bg.png
../dist/index.css
../dist/index.js
../dist/index.min.js
../dist/vendor.js
../dist/vendor.min.js
../assets/img/culb_bg.jpg
../assets/img/culb_bg.png
../assets/img/culb_del.png
../assets/img/culb_dot.png
../assets/img/culb_member.png
../assets/img/culb_nav_active.png
../assets/img/culb_product.png
../assets/img/culb_tab.png
../assets/img/load.gif
../assets/img/loading.gif
../assets/img/svg/culb_dot.png

FALLBACK:
index.html
error.html

SETTINGS:
prefer-online






```

Arguments:

* `cache`: An array of additional assets to cache.
* `network`: An array of assets that may be accessed via the network.
  Defaults to `['*']`.
* `fallback`: An array of fallback assets.
* `settings`: An array of settings.
* `exclude`: An array of strings or regex patterns. Assets in the compilation
that match any of these patterns will be excluded from the manifest.
* `output`: The filename to write the appcache to
* `outpath`: Relative path 
* `excludePath`: Remove file path
## License

## Update
* `fixed` Fixed some bug errors about empty files
[MIT](http://www.opensource.org/licenses/mit-license.php)
