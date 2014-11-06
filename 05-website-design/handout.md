### Geosoftware II WiSe 2014/15

# Modern Website Design - Handout

---

## Inhalt


1. [Einführung](https://github.com/Ehrecke/geosoft2-2014-fundamentals/blob/master/05-website-design/handout.md#einführung)
2. [Stylesheets](https://github.com/Ehrecke/geosoft2-2014-fundamentals/blob/master/05-website-design/handout.md#css3)
  1. [CSS(3)](https://github.com/Ehrecke/geosoft2-2014-fundamentals/blob/master/05-website-design/handout.md#css3)
  2. [SASS](https://github.com/Ehrecke/geosoft2-2014-fundamentals/blob/master/05-website-design/handout.md#sass)
  3. [LESS](https://github.com/Ehrecke/geosoft2-2014-fundamentals/blob/master/05-website-design/handout.md#less)
  4. [Vergleich LESS/SASS & Tools](https://github.com/Ehrecke/geosoft2-2014-fundamentals/blob/master/05-website-design/handout.md#vergleich-lesssass--tools)
3. [Frameworks & Tools](https://github.com/Ehrecke/geosoft2-2014-fundamentals/blob/master/05-website-design/handout.md#foundation-5)
  1. [Foundation 5](https://github.com/Ehrecke/geosoft2-2014-fundamentals/blob/master/05-website-design/handout.md#foundation-5)
  2. [Bootstrap](https://github.com/Ehrecke/geosoft2-2014-fundamentals/blob/master/05-website-design/handout.md#bootstrap)
  3. [960 Grid System](https://github.com/Ehrecke/geosoft2-2014-fundamentals/blob/master/05-website-design/handout.md#960-grid-system)
  4. [HTML 5 Boilerplate](https://github.com/Ehrecke/geosoft2-2014-fundamentals/blob/master/05-website-design/handout.md#html-5-boilerplate)
  5. [Additional Stuff](https://github.com/Ehrecke/geosoft2-2014-fundamentals/blob/master/05-website-design/handout.md#additional-stuff)
4. [Einschätzung](https://github.com/Ehrecke/geosoft2-2014-fundamentals/blob/master/05-website-design/handout.md#einschätzung)

---

## Einführung


Grundsätzlich lässt sich sagen, dass die Thematik der Anforderungen an modernes Webdesign ein sehr weites Feld ist. Zum einen gibt es eine Vielzahl von Meinungen, sowie ein unüberschaubares Angebot an Umsetzungsmöglichkeiten, zum anderen hängen die Anforderungen auch zu einem Stück weit immer von persönlichem Geschmack und der aktuellen Mode ab. Abgesehen von diesen Vorraussetzungen, lässt sich ein Umstand jedoch nicht ignorieren; Die rasant gestiegene Anzahl mobiler Endgeräte und die Erwartungshaltung der Endnutzer, immer und überall, auf die entsprechenden Webangebote zugreifen zu können. Um diese Herausforderungen angemessen zu lösen ist einem Grundsatz in jüngster Vergagenheit eine enorme Gewichtung zugekommen; Dem "Responsive (Web)Design".

### Responsive Design

Responsive Webdesign ist ein gestalterisches und technisches Paradigma bei der Erstellung von Websites.
Der Inhalt reagiert dabei auf die jeweils genutzten Endgeräte. 
Dies betrifft sowohl die Auflösung, den Inhalt, als auch Eingabemethoden.
Die Grundlage bilden die aktuellen Webstandards [HTML5](https://github.com/JanVan01/geosoft2-2014-fundamentals/blob/master/03-html5-and-websockets/handout.md), [CSS3](https://github.com/JanVan01/geosoft2-2014-fundamentals/blob/master/03-html5-and-websockets/handout.md) und [JavaScript](https://github.com/m-mohr08/geosoft2-2014-fundamentals/blob/m-mohr08/11-javascript-frameworks/handout.md) (siehe: jeweilige Handouts)

#### Technik:

* wesentliche Vorraussetzungen sog. "Media Queries", ein CCS3-Konzept
* Design richtet sich nach abgefragten Eigenschaften (Größe des Geräts, Bildschirmauflösung, etc.)
* in folgendem Beispiel wird die Breite eines Inhaltes auf 600px verkleinert sobald die breite des Browserfensters 1025px unterschreitet

```css
#inhalt {
	width: 800px;
}

@media screen and (max-width: 1024px) {
	#inhalt {
		width: 600px;
	}
}
```

#### Vorteile:

* Website passt sich der Bildschirmauflösung des mobilen Endgerätes an
* das Webdesign folgt also dem Nutzer - nicht umgekehrt (function follows form)
* starker Marktanteil von Smartphones und Tablets - Trend zur Nutzung haupts. mobiler Endgeräte


#### Nachteile:

* Gestaltung einer Website oder Web-App deutlich zeitaufwändiger
* bei der Ausarbeitung der Inhalte muss auf ggf. begrenzte Bandbreite geachtet werde
* aufgrund der begrenzten Bildschirmgröße bestimmter Geräte müsste evtl. gezielt auf Inhalte verzichtet werden (deswegen: graceful degradation)
* große Anzahl von Endgeräten muss mit Emulatoren, etc. getestet werden

#### Aber:

* deutlich geringerer Pflegeaufwand da Inhalte nur einmal angelegt werden müssen - kosteneffizient

#### Beispielseite:

* https://www.tuj.ac.jp/

<img src="http://img5.fotos-hochladen.net/uploads/responsivedesigex0rscti4m.jpg" alt="MaxWidth 1060px" width="650px"> <img src="http://img5.fotos-hochladen.net/uploads/responsivedesigi5qdsr02b6.jpg" alt="MaxWidth 480px" width="155px">

#### Mobile First:

Hier wird der gewohnte Ansatz einfach umgedreht, man arbeitet sich von der kleinsten Layout-Version zur größten (progressive enhancement).
Wenn eine schlanke, übersichtliche Designlösung für den kleisten Bildschirm gefunden ist, ist ein Portierung auf größere Endgeräte kein Problem mehr.
Man wird also gezwungen, bewusst von vornherein zu Priorisieren und sich auf die wichtigen Dinge zu konzentrieren (content first).
Erst nach und nach werden (falls überhaupt nötig) weitere Scripte, Slideshows und Grafiken eingebaut.
In der direkten Umsetzung programmiert man also nach dem min-width Prinzip, also fügt dann erst Weiteres hinzu wenn eine bestimmte Bildschirmbreite überschritten wird.

#### Beispielseite

* http://myrainbownursery.co.uk/

#### Quellen:

* http://de.wikipedia.org/wiki/Responsive_Webdesign
* http://www.responsive-webdesign.mobi/
* http://www.elmastudio.de/webdesign/webdesign-goes-mobile-first-eine-kleine-einfuhrung-zum-neuen-webdesign-trend/
* http://t3n.de/news/responsive-webdesign-einstieg-524171/

---

## CSS(3)


Cascading Style Sheets , kurz CSS, ist eine Gestaltungssprache zum Formatieren von HTML/XHTML-Elementen. Es erweitert die HTML-Formatierung um Schriftgestaltung, Rahmen, Abstände, Listen, Hintergründe, etc.

####Code-Beispiel

```html
<head>
	<style="text/css">
		p {
			corlor: red;
			font-family: verdana;
		}
	</style>
</head>
<body>
	Normaler Text
	<p> veränderter Text </p>
</body>
```

Also ab:

```html
<style="text/css">
```

handelt es sich um CSS. Danach sollte die optische Veränderung folgen:

```css
p {
	color:red;
	font-family:verdana;
}
```

Wie hier im Beispiel, die Schriftfarbe und -art. Weitere Informationen und Tutorials finden sich in den Quellen.

####Quellen:

* http://www.csstutorial.net/
* http://panjutorials.de/html-css-tutorial-fur-anfanger-10-einfuhrung-in-css/
* http://www.w3schools.com/css/default.asp
* http://www.w3schools.com/css/css3_intro.asp

---

## SASS


* Syntactically Awesome Stylesheets

Ist eine Stylesheet-Sprache, die CSS um ein paar nützlichen Eigenschaften erweitert. Sie wird von Natalie Weizenbaum und Chris Eppstein entwickelt. SASS wird in einer SCSS-Datei erstellt und dann in eine CSS-Datei umgewandelt.

* ursprünglich von der Auszeichnungssprache YAML beeinflusst
* basiert auf [Ruby](http://www.ruby.org)
* minimalistischste Schreibweise

####Eigenschaften

* verwendet Mixins
* Paramterübergabe
* Code-Blöcke fexibel einsetzbar

####SASS Syntax Beispiele

* __Variablen__ definieren, um zum Beispiel Farben und Schriftarten schneller aufrufen zu können

```javascript
$font-stack:    Helvetica, sans-serif
$primary-color: #333

body
	font: 100% $font-stack
	color: $primary-color
```

* wird in CSS zu:

```css
body {
	font: 100% Helvetica, sans-serif;
	color: #333;
}
```


* __[Mixin]s__, um Gruppen von CSS-Deklarationen zu erstellen

```javascript
=border-radius($radius)
	-webkit-border-radius : $radius
	-moz-border-radius : $radius
	ms-border-radius : $radius
	border-radius : $radius

.box
	+border-radius(10px)
```

* wird in CSS zu:

```css
.box {
	-webkit-border-radius: 10px;
	-moz-border-radius: 10px;
	-ms-border-radius: 10px;
	border-radius: 10px;
}
```

####Vorteile

* Nutzung von Variablen zum Beispiel um mathematisch Operationen zu definieren
* Verschachtelungen von "Klassen"
* bessere Übersicht
* Vererbung
* Vermeidung von Redunanzen

####Nachteile

* erschwertes Debugging 
* Erweiterung potenzieller Fehlerquellen
* Stylesheets werden nur per Ruby generiert

####Quellen

* http://sass-lang.com/
* http://webkrauts.de/artikel/2012/css-modularisierung-mit-sass
* http://de.wikipedia.org/wiki/Sass_%28Stylesheet-Sprache%29

---

## LESS


LESS ist eine Stylesheet-Sprache, die CSS effektiver machen soll durch Erweiterung von Variablen, Mixins, Berechnungen von Funktionen. Entwickelt wird sie von Alexis Sellier.

####Eigenschaften

* Vermeidungen von Code-Wiederholungen durch Regeln
* Einer Klasse von Elementen können Regeln zugewiesen werden
* Variablen können ebenfalls wie bei SASS festgelegt und an anderer Stelle wiederbenutzt werden
* LESS unterstützt ebenfalls Mixins, wodurch Regeln unter Namen zusammengefasst werden können

####LESS Kompilierung

* Server-seitig (Node.js)
* Client-seitig (moderne Browser)
* Änderungen mit Watch Mode automatisch im Webrowser
* wird in CSS kompiliert

####Codebeispiele

####Variablen

* spezielle Farbe als Variable definieren
* jederzeit wieder aufrufbar

```javascript
@mycolor: #4D926F;  

#header {   
 	color: @mycolor;   
}   
h2 {   
	color: @mycolor;   
}  
```
 	
* wird in CSS zu :

```css
#header {   
	background-color: #4D926F;   
}    

h2 {   
	color: #4D926F;   
}
```

Mehr Beispiele: [Los geht's!](http://www.lesscss.de/)

####Quellen

* http://lesscss.org/
* http://www.lesscss.de/
* http://de.wikipedia.org/wiki/LESS_%28Stylesheet-Sprache%29
* http://less2css.org/

---

## Vergleich [LESS/SASS](http://www.hongkiat.com/blog/sass-vs-less/) & Tools


* SASS benötigt mehr Einarbeitungszeit, LESS ist einfacher zu lernen
* beide in Ruby entwickelt, aber LESS ist um eine JavaScript-Bibliothek erweitert
* LESS lässt sich zustätzlich in ein HTML-Dokument einbinden
* beide in CSS-Syntax, aber SASS verzichtet auf Klammern und Semikolons (minimalistischste Schreibweise)
* SASS hat den größten Funktionsumgang, LESS ist nur bedingt erweiterbar
* Unterschied in der Benennung der Variablen

```javascript
@ LESS
$- SASS
```

* weitere Vergleiche unter [LESS/SASS](http://www.hongkiat.com/blog/sass-vs-less/)

### Stylus

Eine weitere Syslesheet-Sprache, die in Javascript geschriebenen und für die Plattform Node.js entwickelt wurde

####Code Beispiel

```javascript
meineFarbe = #0033ff
header
background-color meineFarbe
h1
color meineFarbe
a
color meineFarbe
```

* wird in CSS zu:

```css
header {
	background-color: #0033ff;
}
h1 {
	color: #0033ff;
}
a {
	color: #0033ff;
}
```

####Im Vergleich zu SASS/LESS

* in JavaScript geschrieben und für Node.js entwickelt
* minimale CSS-Syntax (Klammern, Doppelpunkte und Semikolons nicht notwenig)

####Ausführlicher Vergleich der 3 Stylesheets unter :

[SASS/LESS/STYLUS](http://www.heise.de/developer/artikel/CSS-Praeprozessoren-im-Vergleich-2288284.html?artikelseite=2)

###Grunt

Grunt ist ein Tool, um Arbeitsschritte beim Bau einer Web-Anwendung zu automatisieren und zu vereinfachen.
Es läuft mit node.js

Grunt vereinfacht durch Plugins (LESS, SASS, Stylus, CoffeeScript) das Kompilieren. Als Beispiel könnte etwa ein SASS File automatisch als CSS kompiliert und eine JavaScript File automatisch getetest werden. All das übernimmt Grunt. Es gibt viele solche Task Runner (Cake, Gulp etc.), aber Grunt überzeugt mit seiner große Anzahl an Plugins.

[Grunt-Homepage](http://gruntjs.com/)     
[Grunt-Installation](http://gruntjs.com/getting-started)     
[Grunt-Plugins](http://gruntjs.com/plugins)    
[Grunt-Tutorial](http://culttt.com/2013/11/11/getting-started-grunt/)    
[Grunt-Sass Installation](http://culttt.com/2013/11/18/setting-sass-grunt/)    
[Vergleich mit anderen Task-Runnern](http://blog.cozycloud.cc/technic/2014/06/18/task-runners-comparison/)    

Hier auf GitHub
https://github.com/gruntjs/grunt-contrib-sass

###Bower

Bower ist ein Package Management für das Web. Es läuft mit node.js und dem Node Package Manager (npm), sowie auf Git.

```javascript
npm install -g bower
```

npm aktiviert den Node Package Manager. Install –g bower installiert dann global den Bower Package Manager. Außerdem wird Git benötigt, da die meisten Packages über Github bezogen werden.

Weitere Informationen zu [Bower](http://bower.io/)     
[Tutorial/Installation](http://webkrauts.de/artikel/2013/workflow-mit-dem-bower-package-manager)

Vor allem im Zusammenhang mit Grunt lässt sich durch Bower viel Zeit sparen.

[Tutorial Getting Start with Grunt and Bower](http://www.nitinh.com/2013/05/getting-started-with-grunt-bower/)     
[Auf Github](https://github.com/sapegin/grunt-bower-concat)

####Quellen

* http://lesscss.org/
* http://www.lesscss.de/
* http://de.wikipedia.org/wiki/LESS_%28Stylesheet-Sprache%29
* http://less2css.org/
* http://culttt.com/2013/11/18/setting-sass-grunt/
* http://gruntjs.com/
* http://blog.cozycloud.cc/technic/2014/06/18/task-runners-comparison/
* http://bower.io/
* https://github.com/sapegin/grunt-bower-concat
* http://webkrauts.de/artikel/2013/workflow-mit-dem-bower-package-manager

---

## Foundation 5


####Allgemein

Foundation ist ein häufig verwendetes User-Interface-Framework, also ein komponentenbasiertes Konstrukt, dass die Entwicklung u.a. von Webanwendungen erleichtern soll.

* Aus einem Stylequide, des Unternehmens [Zurb](http://zurb.com/) entstanden
* CSS (SASS)-Framework
* Primär für User-Interface-Gestaltung
* Foundation enthält Designvorlagen für HTML, CSS sowie optionale JavaScript-Erweiterungen
* Open-Source-Responsive-Frontend Framework
* Erstes semantisches Framework nach dem Mobile First Prinzip

> "Heute bezeichnet sich Foundation selbst als das "Most advanced responsive front-end
> framework in the world" und das - wie wir meinen - völlig zu Recht." [iq2](http://www.iq2.at/blog-details/zurb-foundation-frontend-framework-einfuehrung.html)

* Das Grid wird in Foundation an die Auflösung des jeweiligen Gerätes angepasst

[Beispielcode für ein Grid](http://foundation.zurb.com/docs/components/grid.html)

####Vorteile

* Auf jedem Geräte-Typ nutzbar

> "Laut Zurbs „Chief-Instigator“ und Gründer Bryan Zmijewski ist Foundation 5 unter
> mehreren Aspekten das schnellste Framework" [t3n]

* Schnell lernbar, codierbar, laufbar
* Schneller für Einsteiger (gute Dokumentation und Tutorials)

####Nachteile und Probleme

* Mitgeliefertes CSS-Styling kann störend sein
* Möglichkeiten an [Kursen](http://zurb.com/university/foundation-intro?utm_source=Foundation%20Docs&utm_medium=Large%20Banner&utm_campaign=Intro%20to%20Foundation) teilzunehmen, sind vorhanden aber teuer

Neue Features für Foundation 5 sind unter anderem ein Editor, um das Framework vor dem Download anzupassen, Code ist lesbarer und semantisch, Einsatz von SASS, UI-Pattern und ein Mobile-First-Ansatz. Außerdem gibt es ein sehr große Anzahl an [Templates](http://foundation.zurb.com/templates.html)

[Beispiel Webseiten die Foundation benutzen](http://zurb.com/responsive?framework_id=1)

<img src="http://zurb.com/responsive/system/upload/desktop_screenshots/images/000/000/741/regular/express.com-wide.jpg?1410306028" alt="Example1" width="582px"> <img src="http://zurb.com/responsive/system/upload/mobile_screenshots/images/000/000/742/regular/express.com-narrow.jpg?1410306032" alt="Example2" width="270px">

####Quellen

* http://foundation.zurb.com/
* [iq2](http://www.iq2.at/blog-details/zurb-foundation-frontend-framework-einfuehrung.html)
* http://de.wikipedia.org/wiki/Foundation_%28Framework%29

---

## Bootstrap


Bootstrap ist ein sehr häufig verwendetes und auf GitHub gehostetes Open Source CSS-Framework mit Gestaltungsvorlagen für Schriften, Formulare, Buttons, Tabellen, etc. Die Idee ist dabei Designer und Entwickler zusammenzubringen, um nicht nur Entwicklungszeiten zu verkürzen sondern auch, ohne langwierige Designprozesse für ein einheitliches Look-and-Feel der Anwendungen zu sorgen.   
Es unterstützt auch den dynamischen Aufbau von Websites im Sinne des Responsive Webdesigns, sowie die Unterstützung älterer Browser durch die implementierung alternativer Stylesheets.

#### Aufbau

* enthält eine Reihe von Stylesheets die grundlegende Stildefinition vorgeben 
* modular aus LESS-Stylesheets aufgebaut, Einzelkomponenten werden von einer zentralen bootstrap-Datei zusammengeführt
* standardmäßig: 940px breites, zwölfspaltiges Grid-Layout
* vier Variationen (für Smartphones, Tablets, PC's mit geringer und hoher Auflösung) stehen zur Verfügung
* zusätzlich sind weitere, häufig verwendete Buttons, Drop-Down-Menues, etc. enthalten
* JavaScript Komponenten basieren auf jQuery

#### Anwendung

* vor der Einbindung in ein HTML-Dokument muss eine CSS-Datei aus den LESS-Stylesheets kompiliert werden
* alternativ lassen sich natürlich auch direkt kompilierte Dateien einbinden
* bei der Verwendung von JavaScript muss außerdem zunächst die jQuery Bibliothek eingebunden werden

```html
<head>
	<title>Beispiel</title>
	
	<!-- Einbinden des Bootstrap-Stylesheets -->
	<link rel="stylesheet" href="css/bootstrap.min.css">

	<!-- optional: Einbinden der jQuery-Bibliothek -->
	<script src="http://ajax.googleapis.com/ajax/libs/jquery/1.5/jquery.min.js"></script>

	<!-- optional: Einbinden der Bootstrap-JavaScript-Plugins -->
	<script src="js/bootstrap.min.js"></script>
</head>
```

#### Vorteile

* teils erhebliche Verkürzung der Entwicklungszeit    
* einheitliches Look-and-Feel   
* zahlreiche Icons und Buttons integriert    
* viele Templates und Erweiterungen frei verfügbar    
* bei optischen Veränderungen muss nur die CSS-Datei angepasst werden    

#### Nachteile

* einheitliches Look-and-Feel (will man wirklich, dass jede Site gleich aussieht?)
* für strukturelle Veränderungen müssen die LESS-Stylesheets und JavaScript-Code geändert werden (mühsam)

[Beispiel Webseiten die Bootstrap benutzen](http://lovebootstrap.com/)

![alt text](http://lovebootstrap.com/sites/default/files/styles/screenshot_browser/public/screenshot-www.tryvertty.com_.jpeg?itok=t7B8p1mO "Example")

#### Quellen

* http://getbootstrap.com/
* http://de.wikipedia.org/wiki/Bootstrap_%28Framework%29

---

## 960 Grid System


#### Allgemein

960 Grid System ist ein CSS-Grid-Framework entwickelt von Nathan Smith mit folgenden Eigenschaften und Features:

* lässt Layouts, die auf Gestaltungsrastern basieren, schnell und leicht durch vordefinierte CSS-Klasen in Webseiten umwandeln
* Darstellungsbreich auf 960 Pixel Breite festgelegt
* funktioniert in allen gängigen Browsern

####Optionen im Darstellungsbereich

* Aufteilung in 12 Spalten mit Breite von je 60 Pixel
* Aufteilung in 16 Spalten mit Breite von je 40 Pixel
* Abstand zwischen Spalten jeweils bei 20 Pixeln
* erste und letzte Spalte haben je 10 Pixel zu den Außenkanten

Beispiel Website: [Sony](http://www.sonymusic.de/) Music basiert auf solch einem Gestaltungsraster

<img src="http://img5.fotos-hochladen.net/uploads/960gswideqjwbidvt3u.jpg" alt="Example1" width="650px"> <img src="http://img5.fotos-hochladen.net/uploads/960gssmallhijkwcnyvl.jpg" alt="Example2" width="170px">

Mit einem auf das Framework abgestimmten CSS-Generator können auch eigene Raster festgelegt werden
Auf [960.gs](http://www.960.gs) gibt es passende Stylesheets.

####Vorteile

* effizient
* einfach zu erlernen, da Aufbau leicht verständlich

####Nachteile
* nicht besonders flexibel
* schlechte Darstellungen auf mobilen Endgeräte

###Alternativen zu 960 Grid System

###Fluid 960 Grid System

* basiert auf dem 960 Grid System
* ist um __flexibles Layouts__, erweitert
* automatische Anpassung an das Endgerät

####Aufbau

* 12- oder 16-Spalten-Grid-Framework (statisch/flexibel)
* Style-Vorlagen für HTML-Elemente wie zum Beispiel Überschriften
* bereits implementierbares CSS-Dropdown-Menü

###1140 CSS Grid

* ebenfalls flexible Layouts
* 12-spaltig & 1140 Pixel breites Grid
* optimal bei Auflösung von 1280 Pixeln
* passend für Darstellung auf mobilen Endgeräten

####Quellen

* http://960.gs/
* http://t3n.de/magazin/css-frameworks-schnelle-neue-stylesheet-welt-230278/
* http://www.designinfluences.com/fluid960gs/
* http://andytaylor.me/2013/04/09/1140px-css-grid-retired/

---

## HTML5 Boilerplate


HTML5 Boilerplate ist ein Build-Skript welches Vorlagen zur zeitgemäßen und schnellen Web-Entwicklung liefert.

#### Zusammenfassung

* Vorgaben für HTML und CSS sowie JavaScript Bibliotheken und .htaccess-Voreinstellungen (Konfigurationsdatei, z.B. für Passwortschutz)
* weitere nützliche Vorlagen und Skripte z.B. zum Testen
* kein klassischen Framework
* bündelt und dokumentiert sinnvolle Vorlagen und Vorgaben zentral
* eine Art umfangreiche Universalvorlage

#### Leistungen

* optimiert zum Projekt gehörende HTML-, CSS- und JavaScript-Dateien
* d.h. fügt die CSS- und JS-Dateien zusammen, entfernt dabei Unnötiges, und strukturiert sinnvoll neu
* kann auch überflüssige Metadaten aus Bilddateien des Projektes entfernen
* prüft den Code auf Fehler und unperformante Konstrukte

#### Quellen

* http://html5boilerplate.com/
* http://webkrauts.de/artikel/2011/bauen-wie-die-ameisen
* http://www.sitepoint.com/introduction-html5-boilerplate/

---

## Additional Stuff


###Less Framework

* CSS-Grid System mit 4 Layouts (Default Layout, Tablet Layout, Mobile Layout und Wide mobile Layout)
* basieren alle auf einem Grid mit 68px Spalten und 24px Zeilen
* zuerst wird ein Default Layout (922px) erstellt
* daraus können Child Layouts erstellt werden (768, 480 und 320px)
* Child Layouts werden mit CSS3 Media Queries erstellt

#####Quellen

* http://lessframework.com/
* http://lesscss.org/
* http://www.lesscss.de/

---

## Einschätzung


Unter Berücksichtigung aller von uns erarbeiten Quellen, Meinungen, usw. lässt sich folgende Einschätzung und Empfehlung geben:

* Die Berücksichtigung mobiler Endgeräte ist im modernen Webdesign alternativlos
* Die entsprechenden Frameworks sind dabei unverzichtbar, und haben, trotz der hohen Vielfalt, im Funktionsumfang meist nur marginale Unterschiede

Letztendlich überwiegen bei Foundation 5 dann doch die Vorteile:

* Verwendet das syntaktisch etwas einfachere SASS welches leichter zu lernen ist und somit leichter strukturell zu verändern ist, wenn man mehr vorhat, als nur kleine optische Veränderungen (Vorteil gegenüber Bootstrap)
* Der Funktionsumfang ist im Vergleich insgesamt sehr hoch (viele Templates, Interchange, Off-Canvas-Navigation, etc.)
* Andere, wie das 960 Grid System sind in ihrer ursprünglichen Struktur zu unflexibel
* Sehr gute Dokumentation und Tutorials

Außerdem ist es zu empfehlen, die sinnvollen Hilfen von Build-Skripten und Task-Runnern (Grunt, Bower, HTML 5 Boilerplate) auch zu nutzen. Sie erleichtern und verkürzen die Arbeit häufig enorm und sorgen unter Einhaltung gängiger Standards für ein schlankes und performantes Gesamtkonstrukt.

---
---
---
