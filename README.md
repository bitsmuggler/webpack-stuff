# webpack-stuff
Motivation und Beispiel für die Nutzung von Webpack

## Motivation
* Es wird immer mehr Javascript Code in Webanwendungen (insb. SPA) eingesetzt.
* Moderne Browser bieten neue bzw. morderne Möglichkeiten um Javascript-Code zu laden.
* Aufgrund von Single-Page Anwendungen gibt es Weniger Reloads der einer gesamter Webanwendungen, d.h. es muss initial mehr Javascript-Code geladen werden.

Aufgrund dieser Situation gibt es clientseitig immer mehr Javascript-Code. Diese Code-Basis muss organisiert werden. Die Organisation erfolgt mittels Modulen.

## Module-Formate
Es gibt verschiedene Möglichkeiten um Javascript-Module (= eine Javascript Datei) zu laden. Z.B.:
* Script-Tag (kein Module System
   Exportiert ins globale window Objekt. Die Abhängigkeiten werden über das globale window Objekt bezogen.

   Probleme:
   - Konflikte im globalen Objekt
   - Die Reihenfolge wie die einzelnen Module geladen werden ist relevant, d.h. der Entwickler muss die Reihenfolge entsprechend wissen und pflegen.
   - In grossen Projekten eine riesige Liste von Abhängigkeiten. Die Wartbarkeit ist schwierig.

* [CommonJS](http://requirejs.org/docs/commonjs.html)
* AMD
* ES2015 Module


## Alternativen zu Webpack
* SystemJS mit JSPM
* Browserify



