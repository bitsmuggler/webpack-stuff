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

   Potentielle Probleme:
   - Konflikte im globalen Objekt
   - Die Reihenfolge wie die einzelnen Module geladen werden ist relevant, d.h. der Entwickler muss die Reihenfolge entsprechend wissen und pflegen.
   - In grossen Projekten eine riesige Liste von Abhängigkeiten. Die Wartbarkeit ist schwierig.

* [CommonJS](http://requirejs.org/docs/commonjs.html)
CommonJS nutzt die synchrone require-Methode um eine Abhängigkeit zu laden und gibt entpsrechend ein exportiertes Modul zurück. Module werden über das exports Objekt gegen aussen propagiert.

   Vorteile
     * Serverseitige Module können u.U. wiederverwendet werden.
     * Es gibt viele Module, welche dieser Spezifikation entsprechend und via NPM angeboten werden.
     * Die Module sind einfach zu verwenden
   Nachteile
     * Die Aufrufe sind blockierend. Netzwerk Requests sind asynchron.
     * D.h. kein paralleles Requiren von mehreren Modulen.

   Implementierungen:
    * nodejs (serverseitig)
    * browserify
    * modules-webmake (kompliert in ein Bundle)
    * wreq



* AMD
* ES2015 Module


## Alternativen zu Webpack
* SystemJS mit JSPM
* Browserify



