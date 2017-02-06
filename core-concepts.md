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
