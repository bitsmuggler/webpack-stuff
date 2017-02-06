## Transferring

Für den Transfer der Modulen auf den Client gibt es aktuell zwei Extreme:

* Einen Request pro Modul
* Alle Module werden mit einem Request geladen

Beide Varianten werden in der Praxis verwendet, aber es sind bei de Suboptimal.

* Einen Request pro Modul
  * + Es werden nur die benötigten Module transferiert
  * - Sehr viele Request generieren einen grossen Overhead
  * - Langsamer Applicationsstratup -> Request Latenz
* Alle Module in einem Request
  * + Weniger Request-Overhead
  * - Es werden u.U. zu viele Module geladen, welche gar nicht benötigt werden

Fazit: Beide Varianten sind nicht optimal.

### Chunked Transferring
Ein Kompromiss zwischen den beiden Varianten ist besser. Daher fasst man fachlich zusammengehörige Module in sogn. Chunks. Dies ermöglicht mehrere kleinere bzw. schnellere Requests. Chunks müssen auch nicht immer zu Beginn des Anwendung geladen werden. Dies ermöglicht ein schnellerer Bootstrap der Anwendung, und der Code wird erst dann geladen, wenn er auch benötigt wird.

