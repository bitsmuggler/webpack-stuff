## Konzept hinter Webpack
webpack ist ein module bundlern für moderne Javascript Appliationen. Das Ziel ist es Module mit Abhängigkeiten in statische Assets zu bundeln. In Webpack 2 gibt es vier Kernkonzepte:

* Entry
* Output
* Loaders
* Plugins

### Entry
Webpack erstellt einen Graph mit allen Abhängigkeiten. Der Startpunkt vom Graph ist der sogn. Entry-Point. Durch die Angabe des Startpunktes kennt Webpack sämtliche Abhängigkeiten im Kontext des Entry-Points.
Der Entry-Point gibt man in der Webpack-Konfiguration an (i.d.R. webpack.config.js).

```javascript
 module.exports = {
   entry: './path/to/my/entry/file.js'
 };
```

### Output
Sobald alle Assets zusammengebundlet wurden, muss webpack wissen, wo die Bundles hinkopiert werden. Dazu dient das sogn. webpack output property.

```javascript
var path = require('path');

module.exports = {
  entry: './path/to/my/entry/file.js',
  output: {
    path: path.resolve(__dirname, 'dist'),
    filename: 'my-first-webpack.bundle.js'
  }
};
```

### Loaders
Mit den sogn. Loaders transformiert Webpack Datien in sogn. Module. Die Transformierung erfolgt in zwei Schritten:

1. Identifizieren welche Dateien von einem bestimmten Loader transformiert werden sollen. (Test-Property)
2. Die entsprechenden Dateien entsprechend transformieren (use property).


```javascript
var path = require('path');

const config = {
  entry: './path/to/my/entry/file.js',
  output: {
    path: path.resolve(__dirname, 'dist'),
    filename: 'my-first-webpack.bundle.js'
  },
  module: {
    rules: [
      {test: /\.(js|jsx)$/, use: 'babel-loader'}
    ]
  }
};
```



module.exports = config;


