# JavaScript-Frameworks

verfasst von Boris Stöcker und Matthias Mohr 

## Allgemeines

JavaScript (JS) Frameworks gibt es in großer Zahl und sie haben ganz unterschiedliche Anwendungsgebiete.  
Vor- und Nachteile bei der Verwendung von JS-Frameworks sind divers und hängen von den verwendeten Frameworks ab. Folgend sind Gründe genannt, die zutreffen können, aber nicht immer zutreffen, da jedes Framework anders ist. Es handelt sich jedoch um Beispiele, die häufig anzutreffen sind. 

Mögliche Vorteile:

*   Häufig benutzte Funktionalität ist vorhanden und getestet
*   Cross-Browser-Kompatibilität
*   Große Anzahl an Erweiterungen / Widgets / ...
*   Nutzung eines CDN (s.u.) möglich um Ladezeit zu verkürzen

Mögliche Nachteile: 

*   Inkompatibilität der Frameworks untereinander
*   Hohe Komplexität durch ggf. ungenutzte Funktionalität
*   Lange Ladezeit durch ungenutzten Overhead
*   Einarbeitung nötig
*   Anpassung kompliziert

Eine große Übersicht über JavaScript-Frameworks kann bei Wikipedia gefunden werden: 

*   [Comparison of JavaScript frameworks](http://en.wikipedia.org/wiki/Comparison_of_JavaScript_frameworks)
*   [List of JavaScript libraries](http://en.wikipedia.org/wiki/List_of_JavaScript_libraries)

## Hinweise zu Ladezeiten und CDN

JavaScript-Frameworks tendieren dazu sehr umfangreich zu sein und damit eine hohe Dateigröße zu erreichen. Beispielsweise ist das Framework AngularJS im “normalen” Zustand 766kb groß. Dies ist für die allgemeine Ladezeit einer Seite nicht von Vorteil, insbesondere wenn man z.B. über ein GPRS oder langsame DSL-Verbindungen auf das Internet zugreift. Um die Ladezeiten zu verkürzen werden im allgemeinen drei Techniken verwendet. 

### 1. Minification

Im ersten Schritt wird die JavaScript-Datei im ursprünglichen Zustand um alle Leerzeichen, Kommentare und sonstige Überflüssigen Zeichen reduziert. Häufig werden auch die Namen von Variablen und internen Funktionen gekürzt. Im Falle von AngularJS ist die Dateigröße nach diesem Verfahren bereits von 766kb auf 105kb verkleinert. Die verkleinerte Datei nennt man häufig “minified” und der Dateiname endet auf “.min”. Mögliche Tools zur Minification sind z.B. der [YUI Compressor](http://yui.github.io/yuicompressor/) (offline) oder [jscompress.com](http://jscompress.com/) (online).

### 2. Komprimierung

Zusätzlich kann die Übertragung von Webseiten zwischen Server und Client (Browser), je nach verwendeter Client- und Serversoftware noch komprimiert werden. Häufig wird die GZip-Komprimierung verwendet. Die Kompressionsmethode ist jedoch vom Server abhängig, ggf. kann aber auch vorkomprimiert werden. Im Falle von AngularJS wird die Datei dadurch auf bis zu 40kb verkleinert. 

Nähere Erklärungen:
* [Serverseitige Komprimierung aktivieren](http://betterexplained.com/articles/how-to-optimize-your-site-with-gzip-compression/)
* [Webseiten-Inhalte vorkomprimieren](http://playground.ebiene.de/wordpress-css-vorkomprimiert/)

### 3. Nutzung eines CDN

CDN steht für Content Delivery Network und beschreibt im Grunde einen zentralen Server, der z.B. JavaScript-Dateien der Frameworks zur Verfügung stellt. Als Entwickler von JS-Anwendungen kann man diese JS-Dateien nutzen anstatt sie auf den eigenen Server zu legen. Der Vorteil dabei ist, dass bei häufiger Nutzung eines CDN die Datei nur einmal in den Cache eines Browsers geladen werden muss, da ein Browser JS-Dateien zur Verkürzung der Ladezeit auf dem Client für die spätere erneute Nutzung zwischenspeichert. Im Idealfall liegt die JS-Datei der eigenen Anwendung, also beim Benutzer, bereits im Cache und muss nicht erneut geladen werden, was effektiv Ladezeit spart. 
CDN wird von verschiedenen Organisationen kostenfrei angeboten, z.B. [Google](https://developers.google.com/speed/libraries) oder [cdnjs](https://cdnjs.com/). 

## Universal-Frameworks (Kommunikation, DOM, UI, ...)

Universal-Frameworks nennen wir Frameworks, die die allgemeine Arbeit mit JavaScript im Web-Bereich erleichtern, da sie häufig genutzte Funktionen zur Verfügung stellen, z.B. Elementselektion im DOM (Document Object Model), DOM-Manipulation, Event-Handling, AJAX und weitere nützliche Hilfsfunktionen. Zudem wir die Browser-übergreifende Implementierung von Webanwendungen erleichtert. 

### [jQuery](http://jquery.com/) (Version 2.1.1 vom 01.05.2014)

Lizenz: MIT- und GPL-Lizenz  
Dateigröße (minified): 252kb (84kb)  
Abhängigkeit: Keine

#### Hinweise

*   Inkompatibel mit prototype
*   jQuery ist vermutlich das einsteigerfreundlichste Universal-Framework
*   Sehr hohe Verbreitung, dadurch viele Erweiterungen und umfangreiche Hilfestellungen
*   Version 2.x unterstützt keinen Internet Explorer 8 und ältere Browser, unabhängige Version 1.x unterstützt zusätzlich Internet Explorer 8 und wird noch weiter aktualisiert

### [mooTools](http://mootools.net/) (Version 1.5.1 vom 29.08.2014)

Lizenz: MIT-Lizenz  
Dateigröße (minified): 152kb (89kb)  
Abhängigkeit: keine  

#### Hinweise

*   Starke Nutzung der Objektorientierung, sodass hohe Erweiterbarkeit und Flexibilität durch hohe Modularität gewährleistet sind.
*   Browserübergreifend kompatibler Code
*   I.d.R. relativ wenig eigener Code benötigt
*   Erweiterung der nativen JS-Objekte um neue Funktionalität

### Alternativen

*   [prototype](http://prototypejs.org/) &amp; [script.aculo.us](https://script.aculo.us/)
*   [Dojo Toolkit](http://dojotoolkit.org/)
*   [YUI Library](http://yuilibrary.com/)
*   [ExtJS](http://www.sencha.com/products/extjs/)

## Frameworks zur Visualisierung von Daten

### [D3.js](http://d3js.org/) (Version 3.4.11 vom 2014-07-18)

Lizenz: BSD-Lizenz  
Dateigröße (minified): 319kb (144kb)  
Abhängigkeit: Keine  

#### Hinweise

*   D3 = Data Driven Documents
*   Ermöglicht mit relativ wenig Aufwand teils aufwändige Visualisierungen
*   Interaktive Visualisierungen möglich
*   Neben Visualisierungen sind verschiedenste Funktionalitäten um Daten zu selektieren, zu verändern, abzufragen, darzustellen, etc. vorhanden

### Alternativen

*   [Raphaël](http://raphaeljs.com/)
*   [ExtJS](http://www.sencha.com/products/extjs/)
*   [Dojo GFX](http://dojotoolkit.org/)

## MVC-Frameworks für Single-Page-Webanwendungen, Routing, ...

Single-Page-Webanwendungen (SPA) brechen mit der üblichen Art von Internetseiten, die aus mehreren verlinkten Seiten bestehen und wo bei jeder Interaktion eine neue Seite geladen werden muss. SPA bestehen nur aus einer einzigen Seite, die die benötigten Inhalte dynamisch nachlädt.  
Das übliche MVC-Entwurfsmuster (Model View Controller) wird in der Webentwicklung häufig aufgeweicht. Die hier genannten Frameworks sind nicht zwingend alle MVC-Frameworks, sondern können auch anderen Entwurfsmustern folgen, z.B. MVVM (Mode View ViewModel). 
Eine interessante Hilfe zur MVC-Framework-Wahl ist [TodoMVC](http://todomvc.com/), die es sich zum Ziel gesetzt hat, eine ToDo-Listen-Anwendung in vielen verschiedenen Frameworks umzusetzen. Der interessierte Entwickler kann sich anhand dieser Beispiele für ein entsprechendes Framework entscheiden. 

### [AngularJS](https://angularjs.org/) (Version 1.2.26 vom 01.10.2014)

Lizenz: MIT-Lizenz  
Dateigröße (minified): 766kb (105kb)  
Abhängigkeit: jQuery Light  

#### Hinweise

*   Template-Engine fest integriert
*   Two-way data binding (automatische Benachrichtigung von Model und View gegenseitig bei Änderungen) möglich
*   Teilweise komplizierte API / Konzepte

### [Backbone.js](http://backbonejs.org/) (Version 1.1.2 vom 20.02.2014)

Lizenz: MIT-Lizenz  
Dateigröße (minified): 60kb (20kb)  
Abhängigkeit: Underscore.js, jQuery (empfohlen)

#### Hinweise

*   Template-Engine frei wählbar, Standard: Underscore.js
*   Nur grundlegende Funktionen vorhanden, daher sind darauf aufbauende Frameworks mit erweiterter Funktionalität entstanden, z.B. [Aura](http://aurajs.com/), [Backbone UI](http://perka.github.io/backbone-ui/), [LayoutManager](https://github.com/tbranyen/backbone.layoutmanager), und zusätzlich sind viele Erweiterungen vorhanden.

### Alternativen

*   [enber.js](http://emberjs.com/)
*   [ExtJS](http://www.sencha.com/products/extjs/)
*   [Cappuccino](http://www.cappuccino-project.org/)

## Frameworks für JSON/XML-Umwandlung

### [JSONIX](https://github.com/highsource/jsonix) (Version 2.0.0 vom 24.02.2014)

Lizenz: BSD-artige Lizenz  
Dateigröße (minified): 163kb (104kb)  
Abhängigkeit: keine 

#### Hinweise / Funktionen

*   Umwandlung XML =&gt; JSON (“Unmarshalling”)
*   Umwandlung JSON =&gt; XML (“Marshalling”)
*   Optionale Benutzung eines XML-Schemas
*   Fest strukturiert und typsicher

## Frameworks zum Templating (Vorlagen)

Templating erlaubt die Trennung von Programmlogik und Oberfläche. Zudem können häufig genutzte Oberflächenelemente wiederverwendet werden. 

### [Mustache](http://mustache.github.io/) (Version 0.8.2 vom 17.03.2014)
Lizenz: MIT-Lizenz  
Dateigröße (minified): 17kb (-)  
Abhängigkeit: Keine

### Alternativen

*   [Underscore.js](http://underscorejs.org/)
*   [Handlebars.js](http://handlebarsjs.com/)

## Frameworks zur Oberflächengestaltung (GUI/Widgets)

Basierend auf bereits vorgestellten Frameworks gibt es Frameworks, die sich mit der Oberflächengestaltung von (Web-)Anwendungen beschäftigen. Je nach bereits gewählten Frameworks bietet es sich an, das dazu passende GUI-Framework zu nutzen. 

### [jQuery UI](http://jqueryui.com/) (Version 1.11.1 vom 01.05.2014)

Lizenz: MIT- und GPL-Lizenz  
Dateigröße (minified): 454kb (233kb)  
Abhängigkeit: jQuery  

#### Funktionen

*   Interaktionen (Drag &amp; Drop, Skalierung, Sortierung, ...)
*   Widgets (Autovervollständigung, Dialog, Menü, Fortschrittsbalken, Tabs, ...)
*   Effekte (Farbanimation, Toggle, Zeigen/Verstecken, ...)

### Alternativen

*   [Dojo Widgets](http://dojotoolkit.org/)
*   [Ext JS](http://www.sencha.com/products/extjs/)
*   [script.aculo.us](https://script.aculo.us/)
*   [YUI Library](http://yuilibrary.com/)

## Empfehlungen
jQuery ist das populärste JS-Framework und beseitzt daher große Community, die Erweiterungen, Tutorials und Hilfe bietet. Zudem ist jQuery häufig Basis anderer Frameworks oder Software, z.B. WordPress oder die vorgestellten MVC-Frameworks. Daher empfehlen wir die Verwendung von jQuery. Bei den MVC-Frameworks hängt die Wahl davon ab, was genau Anforderung ist. Eine gute Unterstützung bei der Wahl kann ToDoMVC bieten. Sollte Backbone.js gewählt werden, bietet es sich an Underscore.js als Template-Engine zu nutzen, ansonsten ist Mustache in vielen Sprachen weit verbreitet. Zur Oberflächengesteltung bietet sich, neben den aus anderen Vorstellungen bekannten Frameworks, wie Bootstrap, bietet es sich bei Nutzung von jQuery an, die Erweiterung jQuery UI zu nutzen, da hier eine gewisse Synergie entsteht und somit auch die Einarbeitung leichter fallen sollte.

Ansonsten haben wir einige weitere populäre Alternativen genannt, die sicherlich auch prinzipiell keine verkehrte Wahl darstellen. Die Alternativen sind jedoch möglicherweise nicht so populär, was die Verfügbarkeit von Hilfestellungen und Erweiterungen einschränken kann.

Tipp: Zu JavaScript und einigen der hier vorgestellten Frameworks gibt es bei [video2brain](https://www.video2brain.com) gute erklärende Videos zu verschiedenen Themen. Diese sind eigentlich kostenpflichtig, jedoch können wir das Angebot mit unserer Uni-Kennung (via [edu-Login](https://www.video2brain.com/de/edu-login)) kostenlos nutzen.

## Weitere Hilfsmittel zur JavaScript-Entwicklung
* [Bower](http://bower.io/): Paket-Manager für JavaScrpt, inkl. Verwaltung der Abhängigkeiten (ähnlich wie Maven [Repository] in Java)
* [Grunt](http://gruntjs.com/): Automatisierung von sich wiederholenden Aufgaben wie Minification, Testen etc.
* [Yeoman](http://yeoman.io/): Hilft bei der Einrichtung eines neuen Projekts, auch im Zusammenspiel mit z.B. Grunt und Bower.
* [Einführung in JS Build mit Node, Bower, Yeoman, Grunt und Co.](http://juristr.com/blog/2014/08/node-grunt-yeoman-bower/)
