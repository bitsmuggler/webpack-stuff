# webpack-stuff
Motivation und Beispiel für die Nutzung von Webpack

## Motivation
* Es wird immer mehr Javascript Code in Webanwendungen (insb. SPA) eingesetzt.
* Moderne Browser bieten neue bzw. moderne Möglichkeiten um Javascript-Code zu laden.
* Aufgrund von Single-Page Anwendungen gibt es Weniger Reloads der einer gesamter Webanwendungen, d.h. es muss initial mehr Javascript-Code geladen werden.

Aufgrund dieser Situation gibt es clientseitig immer mehr Javascript-Code. Diese Code-Basis muss organisiert werden. Die Organisation erfolgt mittels Modulen.

## Module-Formate
Es gibt verschiedene Möglichkeiten um Javascript-Module (= eine Javascript Datei) zu laden.

### Script-Tag (kein Module System)
Exportiert ins globale window Objekt. Die Abhängigkeiten werden über das globale window Objekt bezogen.

`<script src="module1.js"></script><script src="module2.js"></script><script src="libraryA.js"></script><script src="module3.js"></script>`

Potentielle Probleme:
- Konflikte im globalen Objekt
- Die Reihenfolge wie die einzelnen Module geladen werden ist relevant, d.h. der Entwickler muss die Reihenfolge entsprechend wissen und pflegen.
- In grossen Projekten eine riesige Liste von Abhängigkeiten. Die Wartbarkeit ist schwierig.

### [CommonJS](http://requirejs.org/docs/commonjs.html)
CommonJS nutzt die synchrone require-Methode um eine Abhängigkeit zu laden und gibt entpsrechend ein exportiertes Modul zurück. Module werden über das exports Objekt gegen aussen propagiert.

Vorteile
* Serverseitige Module können u.U. wiederverwendet werden.
* Es gibt viele Module, welche dieser Spezifikation entsprechend und via NPM angeboten werden.
* Die Module sind einfach zu verwenden
   
Nachteile
* Die Aufrufe sind blockierend. Netzwerk Requests sind asynchron.
* D.h. kein paralleles Requiren von mehreren Modulen.

Implementierungen von CommonJS:
* nodejs (serverseitig)
* browserify
* modules-webmake (kompliert in ein Bundle)
* wreq

### [AMD](http://requirejs.org/docs/whyamd.html) (Asynchronous Module Definition; asynchronous require)
Verschiedene Modul-Systeme (für den Browser) hatten probleme mit dem synchronen require (von CommonJS) und haben eine asynchrone Version angeboten.

Vorteile
* Passt zu den Netzwerk Requests (asynchron)
* Paralleles Laden von mehreren Modulen
      
Nachteile
* Coding Overhead, aufwändig zu lesen und schreiben
  
Implementierungen
* require.js - clientseitig
* curlJS - clientseitig

### [ES2015 Module](http://exploringjs.com/es6/ch_modules.html)
ECMAScript 2015 hat in der Spezifikation spezifische Sprachkonstrukte, welche für ein Modul System gedacht sind.

Vorteile
* Standard, Zukunft
      
Nachteile
* Vollständige Unterstützung in den Browsern noch ausstehen
* In diesem Format gibt es noch nicht viele Module

### Alternativen zu Webpack
* SystemJS mit JSPM
* Browserify
