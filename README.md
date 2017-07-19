## Installation

```
npm i -D webpack-null-plugin
```

## Usage
This plugin uses the null object pattern to simplify webpack configs with conditional plugins.

For example, perhaps you only want to run the [`start-server-webpack-plugin`](https://www.npmjs.com/package/start-server-webpack-plugin) plugin when the environment variable WEBPACK_START_SERVER equals 1:

``` js
const StartServerPlugin = require('start-server-webpack-plugin');
const NullPlugin = require('webpack-null-plugin');
const shouldRunServer = process.env.WEBPACK_START_SERVER === '1';

module.exports = {
  /* ...rest of config... */
  plugins: [
    shouldRunServer ? new StartServerPlugin('index.js') : new NullPlugin(),
  ],
};

```
