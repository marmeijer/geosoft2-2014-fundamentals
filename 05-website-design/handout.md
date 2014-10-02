### Geosoftware II WiSe 2014/15

# Modern Website Design - Handout

Reqiurements to modern day websites.

## Responsive Design

Responsive Webdesign ist ein gestalterisches und technisches Paradigma bei der Erstellung von Websites.
Der Inhalt reagiert dabei auf die jeweils genutzten Endgeräte. 
Dies betrifft sowohl die Auflösung, den Inhalt, als auch Eingabemethoden.
Die Grundlage bilden die aktuellen Webstandards HTML5, CSS3 und JavaScript (siehe: jeweilige Handouts)

#### Technik:

* wesentliche Vorraussetzungen sog. "Media Queries", ein CCS3-Konzept
* Design richtet sich nach abgefragten Eigenschaften (Größe des Geräts, Bildschirmauflösung, etc.)
* in folgendem Beispiel wird die Breite eines Inhaltes auf 600px verkleinert sobald die breite des Browserfensters 1025px unterschreitet


`#inhalt {`

   `width: 800px;`
   
`}`

`@media screen and (max-width: 1024px) {`

   `#inhalt {`
   
      `width: 600px;`
      
   `}`
   
`}`


#### Vorteile:

* Website passt sich der Bildschirmauflösung des mobilen Endgerätes an
* das Webdesign folgt also dem Nutzer - nicht umgekehrt (function follows form)
* starker Marktanteil von Smartphones und Tablets - Trend zur Nutzung haupts. mobiler Endgeräte


#### Nachteile:

* Gestaltung einer Website oder Web-App deutlich zeitaufwändiger
* bei der Ausarbeitung der Inhalte muss auf ggf. begrenzte Bandbreite geachtet werde
* aufgrund der begrenzten Bildschirmgröße bestimmter Geräte müsste evtl. gezielt auf Inhalte verzichtet werden (graceful degredation)
* große Anzahl von Endgeräten muss mit Emulatoren, etc. getestet werden

#### Aber:

* deutlich geringerer Pflegeaufwand da Inhalte nur einmal angelegt werden müssen - kosteneffizient

#### Beispielseite:

* https://www.tuj.ac.jp/

#### Mobile First:

Hier wird der gewohnte Ansatz einfach umgedreht, man arbeitet sich von der kleinsten Layout-Version zur größten (progressive enhancement).
Wenn eine schlanke, übersichtliche Designlösung für den kleisten Bildschirm gefunden ist, ist ein Portierung auf größere Endgeräte kein Problem mehr.
Man wird also gezwungen, bewusst von vornherein zu Priorisieren und sich auf die wichtigen Dinge zu konzentrieren (content first).
Erst nach und nach werden (falls überhaupt nötig) weitere Scripte, Slideshows und Grafiken eingebaut.
In der direkten Umsetzung programmiert man also nach dem min-width Prinzip, also fügt dann erst Weiteres hinzu wenn eine bestimmte Bildschirmbreite **über**schritten wird.

#### Quellen:

* http://de.wikipedia.org/wiki/Responsive_Webdesign
* http://www.responsive-webdesign.mobi/
* http://www.elmastudio.de/webdesign/webdesign-goes-mobile-first-eine-kleine-einfuhrung-zum-neuen-webdesign-trend/
* http://t3n.de/news/responsive-webdesign-einstieg-524171/

## Bootstrap

placeholder
* http://getbootstrap.com/
* http://de.wikipedia.org/wiki/Bootstrap_%28Framework%29

## Foundation

placeholder
* http://foundation.zurb.com/
* http://de.wikipedia.org/wiki/Foundation_%28Framework%29

## LESS

placeholder
* http://lesscss.org/
* http://www.lesscss.de/
* http://de.wikipedia.org/wiki/LESS_%28Stylesheet-Sprache%29

## SASS


__S__yntactically __A__wesome __S__tyle__s__heets

####Allgemein 
 

Stylesheet-Sprache, die CSS um ein paar nützlichen Eigenschaften erweitert. Sie wird von Natalie Weizenbaum und Chris Eppstein entwickelt.

* ursprünglich von Auszeichnungssprache [YAML]
* basiert auf [Ruby]
* minimalistischste Schreibweise

####Kompilierung
* wird in SCSS-Datei erstellt und dann in eine CSS-Datei umgewandelt

####Eigenschaften
* [Mixin]s
* Paramterübergabe 
* Code-Blöcke fexileke einzusetzen

####SASS Syntax Beispiele    
  
* __Variablen__ definieren, um zum Beispiel Farben und Schriftarten schneller aufrufen zu können
    
        
        $font-stack:    Helvetica, sans-serif
        $primary-color: #333

          body
             font: 100% $font-stack
             color: $primary-color



__CSS:__

          
    body {
      font: 100% Helvetica, sans-serif;
      color: #333;
      }      
 
* __[Mixin]s__, um Gruppen von CSS-Deklarationen zu erstellen, 

    
       =border-radius ( $radius ) 
       -webkit-border-radius :  $radius 
       -moz-border-radius :     $radius 
        ms-border-radius :      $radius 
       border-radius :          $radius      
       
      .box 
         +border-radius ( 10px )

__CSS:__ 

          
    .box {
        -webkit-border-radius: 10px;
        -moz-border-radius: 10px;
        -ms-border-radius: 10px;
         border-radius: 10px;
        }


####Vorteile

* Nutzung von Variablen zum Beispiel um mathmatisch Operationen zu definieren
* Verschachtelungen von Klassen 
* bessere Übersicht 
* Vererbung 
* Vermeidung von Redunanzen 

####Nachteile

* erschwertes Debugging 
* Erweiterung potenzieller Fehlerquellen
* Stylesheets werden nur per Ruby generiert


---
placeholder
* http://sass-lang.com/
* http://webkrauts.de/artikel/2012/css-modularisierung-mit-sass
* http://de.wikipedia.org/wiki/Sass_%28Stylesheet-Sprache%29

## HTML5 Boilerplate

placeholder
* http://html5boilerplate.com/
* http://webkrauts.de/artikel/2011/bauen-wie-die-ameisen

## 960 Grid System

placeholder
* http://960.gs/
* http://t3n.de/magazin/css-frameworks-schnelle-neue-stylesheet-welt-230278/

## Additional Stuff

* HMTL5?
* CSS3 (Media Queries)?
* JavaScript?

