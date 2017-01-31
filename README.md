ui.leaflet.layers.webpack
=====================

UI Leaflet Layers (https://github.com/elesdoar/ui-leaflet-layers) structured with webpack.

### Install

Install with npm: `npm install --save ui.leaflet.layers.webpack`

### Usage

```javascript
require('ui.leaflet.layers.webpack');

angular.module('YourModule', ['ui-leaflet']);
```

### Notes
This module already requires Leaflet, Ui-Leaflet and Leaflet MarkerCluster plugin, so don't require them again. 

Also, the Leaflet global object 'L' is exposed through an angular value 'L':

```javascript
angular.module('example', ['ui-leaflet'])
        .service('MyService', function(L){
            // L is the Leaflet global object. (Not global anymore :)
        });
```

### Build Notes
This module was written with ES6, so you need a babel loader to build.

Install the babel-loader
```bash
npm install babel-loader babel-core babel-preset-es2015 webpack --save-dev
```

Add this loader into your webpack.config file
```javascript
{
    test: /\.js$/,
    exclude: /(node_modules(?!\/(ui.leaflet.layers.webpack|ui.leaflet.webpack))|bower_components)/,
    loader: 'babel-loader?presets[]=es2015'
},
```