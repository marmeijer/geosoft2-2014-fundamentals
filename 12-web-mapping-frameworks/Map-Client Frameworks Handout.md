#Map-Client Frameworks


  1. **Definition**
  2. **Web-Maps, how do they work? Slippy what??**
  3. **Aktuelle Map-Client Frameworks. Proprietär und Open-Source**
  4. **Map-Client Frameworks im Vergleich**
  5. **Ausblick**
  6. **Quellen**
  

##1. Definition


>"Web mapping clients are pieces of software (applications, viewers, libraries and frameworks, among others) that either provide or extend a Web-based mapping component to view and interact with maps from remote sources on the Internet. Some of the projects that provide such a mapping component use pure client-side technology whereas the vast majority rely on server-side features allowing advanced tasks to be performed, such as security, user and group administration, advanced printing capabilities, spatial analysis support and customization of graphic user interface controls and functionalities, among others."
[Quelle ](http://geotux.tuxfamily.org/index.php/en/geo-blogs/item/291-comparacion-clientes-web-v6)

Als Map-Client Frameworks bezeichnet man also alle Software und Softwarekomponenten, die es ermöglichen webbasiert mit Karten und Geodaten zu Arbeiten. Hierbei kommen verschiedenste Technologien zum Einsatz und die Auswahl an Ansätzen ist dem entsprechend groß. Während einige Ansätze nur clientseitige Technologien nutzen ist es häufiger der Fall, dass eine Kombination aus client- und serverseitiger Technologie zum Einsatz kommt um so auch fortgeschrittene GIS Anwendungen über das Web realisieren zu können.



##2. Web-Maps, how do they work? Slippy what??

Während man bei klassischen Papierkarten recht schnell an Grenzen stößt, bieten moderne webbasierte Karten eine komplett andere Erfahrung. Im Web erscheinen Karten wie ein einziges durchgehendes Bild auf dem man nach belieben hin und her, sowie raus und rein "zoomen" kann. Ohne dabei scheinbar auf Grenzen zu stoßen.

Diese Art von Webkarten nennt man auch "[Slippy Map](http://wiki.openstreetmap.org/wiki/Slippy_Map)", aufgrund ihrer "pan" und "zoom" Funktionalitäten.

Doch obwohl Webkarten die Illusion liefern, sie würden aus einem durchgehenden Kartenbild bestehen steckt in Wahrheit häufig ein anderer Ansatz dahinter. Ein durchgehendes Kartenbild der Erde mit dem Detailgrad von Straßenzügen wäre einfach viel, viel zu groß um es im Browser herunterzuladen und anzuzeigen.

Darum nutzen moderne webkarten so genannte "*Tiles*". "*Tiles*" sind typischerweise 256x256 pixel groß und sind eigentlich nichts anderes als Bildkacheln mit Raster- oder Vektordaten die nebeneinander angeordnet sind, um so ein durchgehendes Bild zu schaffen.

Ein etwas anderer älterer Ansatz ist es, anstelle von Kacheln Web-Maps mithilfe des [OGC WMS Standarts](http://www.opengeospatial.org/standards/wms) zu realisieren. Hier kommt wirklich jeweils pro Zoomstufe nur ein durchgehendes Bild zur Darstellung und keine einzelnen Kacheln.

####*Tiled Maps*
Wenn bei *Tiled Maps* die Zoomstufe erhöht wird, erhöht sich die Anzahl an dargestellten Kacheln und umgekehrt verringert sich die Anzahl der dargestellten Kacheln, wenn die Zoomstufe wieder verringert wird. Hierzu hat jede Kachel drei Koordinaten: *z*, *x*, *y*

Z bezeichnet die aktuelle Zoomstufe einer Kachel, während x und * die Position der Kachel auf der aktuellen Zoomstufe definieren. Zoomstufe 0 hat genau eine Kachel mit den Koordinaten 0/0/0 und stellt die gesamte Welt da.

![Zoomstufe 0/0/0](https://a.tiles.mapbox.com/v3/examples.map-i86l3621/0/0/0.png) **tile 0/0/0**

Auf der nächsten Zoomstufe wird diese Kachel durch vier Kacheln ersetzt, so dass die Kacheln 1/0/0 und 1/0/1 die nördliche Hemisphäre bilden, während die Kacheln 1/1/0 und 1/1/1 die südliche Hemisphäre bilden. Für jede weitere Zoomstufe wird nun die Anzahl an Kacheln vervierfacht. So wird ein hoher Detailgrad ermöglicht, allerdings steigt so auch der Bedarf an Speicher und Bandweite der benötigt wird um die Kacheln zu liefern exponentiell an. Auf Zoomstufe 15, auf der gebäude Sichtbar werden, werden schon 1,1 Milliarden Kacheln benötigt. Auf Zoomstufe 17 dann 17 Milliarden.

Die Vorteile solcher "*Tiled Maps*" sind:

* "*Tiled Maps*" lassen sich effizient vom Cache nutzen. (Kacheln vom Kreuzviertel können wiederverwendet werden, wenn man sich Münster Zentrum anschaut)
* "*Tiled Maps*" laden stufenweise. Die Kacheln werden nach und nach geladen, nicht alle gleichzeitig.
* "*Tiled Maps*" sind einfach! Dank dem Koordinatensystem was den Kacheln zugrunde liegt, ist es besonders einfach geografische Koordinaten einzelner Kacheln zu berechnen.

Um sich das Prinzip von *Tiled Maps* besser vorstellen zu können, [hier](http://www.maptiler.org/google-maps-coordinates-tile-bounds-projection/) ein Beispiel mit dem Google Maps *map-client*. 

####Wie aus *Tiles* Maps werden.

Map *Tiles* wie bisher beschrieben sind eigentlich nichts anderes als Bilder im Browser. Um aus ihnen eine echte Webkarte zu machen muss noch einiges an CSS, HTML und JavaScript (oder auch eine andere Programmiersprache) Anwendung finden.

Für eine Karte vom Domplatz in Münster müsste z. B. zunächst einmal herausgefunden werden auf welche Kachel mit welchen z/x/y Koordinaten der Dom von Münster auftaucht. Anschließend müssen genügend <img> tags in das HTML Dokument eingebunden werden, abhängig davon wie groß die Karte im Browser ist. Die <img> tags müssen dann durch CSS in einem ordentlichen Gitter angelegt werden. Zu letzt braucht die Webkarte noch weitere Funktionalitäten, wie z. B. einen "Zoombutton".

Um diesen ganzen Prozess zu vereinfachen und zu automatisieren werden Map-Client Frameworks genutzt. Typischerweise übergibt man dem Map-Client die gewünschten Koordinaten sowie den Zoomlevel und der Map-Client liefert dann automatisch die benötigten Kacheln um die Webkarte darzustellen.

Die theoretischen Grundlagen die bei diesem Prozess Anwendung finden sowie Codebeispiele sind [hier](http://wiki.openstreetmap.org/wiki/Slippy_map_tilenames) sehr gut nachzulesen.


##3. Aktuelle Map-Client Frameworks. Proprietär und Open-Source

####Open-Source
Die Anzahl an möglichen Map-Client Frameworks ist groß und wie bei Frameworks und Libraries üblich, kommen stets neue hinzu während andere nicht länger fortgesetzt werden. Als Beispiel für die Anzahl und Beziehungen verschiedener open source Map-Client's (Stand: 2012) kann folgende Darststellung dienen:

![Beziehungen zwischen map clients](http://downloads.tuxfamily.org/tuxgis/geoblogs/comparacion_clientes_v6/dependencia_clientes_english_20120102.png)
[Quelle ](http://geotux.tuxfamily.org/index.php/en/geo-blogs/item/291-comparacion-clientes-web-v6)

Es wird ersichtlich, dass sowohl eigenständige Map-Client's existieren (z. B. *Leaflet*) als auch Map-Client's die andere Map-Client's (z. B. *OpenLayers*) als Grundlage nehmen. Leaflet und OpenLayers werden im nächsten Abschnitt noch eingehener betrachtet und verglichen.

####Proprietär
Die Liste an populären proprietären Map-Client's ist deutlich übersichtlicher, aber die proprietären Map-Client's sind darum nicht weniger weit verbreitet oder werden weniger häufig genutzt. Die [Google Maps API](https://developers.google.com/maps/documentation/javascript/tutorial) kann hier als ein Beispiel für eine weit verbreitete proprietäre Lösung dienen. Aber auch [ESRI](https://developers.arcgis.com/en/) bietet mit eigenen API's und SDK's Map-Client Funktionalitäten.


##4. Map-Client Frameworks im Vergleich
Beispielhaft werden nun [OpenLayers](http://openlayers.org/) und [Leaflet](http://leafletjs.com/), als Open-Source Lösungen, in ihren modernsten Versionen miteinander verglichen.

Beide Map-Client Frameworks sind JavaScript Libraries. Leaflet aktuell in Version 0.7.3, vorraussichtlich im nächsten Monat jedoch mit der 1.0 Veröffentlichung. OpenLayers hingegen befindet sich seit 29.08.2014 in Version 3.0. Die erste Veröffentlichung der beiden Libraries war jeweils 2006 für OpenLayers und 2011 für Leaflet.

OpenLayers, seit 2007 als [OSGeo](http://www.osgeo.org/) Projekt fortgeführt, gilt als die vollständigste Web-Mapping Lösung für den GIS Einsatz. Dies erreicht OpenLayers durch die breite Unterstützung an verschiedensten Datenformaten aus unterschiedlichen Quellen, sowie durch die Unterstützung von OGC Standarts.

Diese Vollständigkeit führt aber auch zu einem großen Umfang und dem entsprechender Komplexität, so ist OpenLayers 3 als Library verpackt 3,3 MB groß. Vor allem aber die Komplexität von OpenLayers führte dann dazu, dass Vladimir Agafonkin damit begann seine eigene JavaScript mapping Library zu entwickeln. Statt wie viele andere Map Client's OpenLayers als Grundlage zu nehmen entwickelte er seine Library (Leaflet) von Grund auf neu.

>"Leaflet is designed with simplicity, performance and usability in mind. It works efficiently across all major desktop and mobile platforms out of the box, taking advantage of HTML5 and CSS3 on modern browsers while still being accessible on older ones. It can be extended with a huge amount of plugins, has a beautiful, easy to use and well-documented API and a simple, readable source code that is a joy to contribute to." [Quelle ](http://leafletjs.com/)

Während OpenLayers als vollständige Web-mapping Lösung für den GIS Einsatz gilt, verfolgt Leaflet den Ansatz der Einfachheit. Die Idee hier ist, dass auch ohne viel Hintergrundwissen im GIS-Bereich, es möglich sein soll schnell und einfach Web-Maps zu kreieren.

So unterstützt Leaflet von Haus aus weniger Datenformate als OpenLayers, allerdings gibt es um zusätzliche Funktionalitäten in Leaflet einzusetzen den Ansatz der Plug-ins.

Beispiele für OpenLayers im Einsatz:
* [Geoportal Mannheim](http://www.gis-mannheim.de/mapserver_mann/index.php) 
* [Schweizerische Eidgenossenschaft](http://map.geo.admin.ch/?X=156000.00&Y=581000.00&zoom=1&lang=en&topic=ech&bgLayer=ch.swisstopo.pixelkarte-farbe)
* [National Library of Scotland](http://maps.nls.uk/view/74400666)

Leaflet hat dank seiner Einfachheit schon in vielen Bereichen Anwendung gefunden, sowohl bei Endnutzern, als auch als technologische Grundlage für eigenständige Unternehmen:
* [Mapbox](https://www.mapbox.com/mapbox.js/api/v2.1.2/), ein Start-up Unternehmen mit einer  eigenen mapping Library auf Grundlage von Leaflet.
* [CartoDB](http://cartodb.com/), ein weiteres Start-up Unternehmen unter anderem auf der Basis von Leaflet.
* [Ethermap](http://giv-wilhelm.uni-muenster.de/), Kollaborativer Kartendienst entstanden im Zuge einer Masterarbeit.

Code Beispiele zum anzeigen einer einfachen Webmap

OpenLayers:
```javascript
<!doctype html>
<html lang="en">
  <head>
    <link rel="stylesheet" href="ol3/ol.css" type="text/css">
    <style>
      #map {
        height: 256px;
        width: 512px;
      }
    </style>
    <title>OpenLayers 3 example</title>
    <script src="ol3/ol.js" type="text/javascript"></script>
  </head>
  <body>
    <h1>My Map</h1>
    <div id="map"></div>
    <script type="text/javascript">
      var map = new ol.Map({
        target: 'map',
        layers: [
          new ol.layer.Tile({
            title: "Global Imagery",
            source: new ol.source.TileWMS({
              url: 'http://maps.opengeo.org/geowebcache/service/wms',
              params: {LAYERS: 'bluemarble', VERSION: '1.1.1'}
            })
          })
        ],
        view: new ol.View({
          projection: 'EPSG:4326',
          center: [0, 0],
          zoom: 0,
          maxResolution: 0.703125
        })
      });
    </script>
  </body>
</html>
```

Leaflet:
```javascript
<!DOCTYPE html>
<html>
<head>
<meta charset=utf-8 />
<title></title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no" />
  <script src="http://cdn.leafletjs.com/leaflet-0.7.3/leaflet.js"></script>
  <link rel="stylesheet" href="http://cdn.leafletjs.com/leaflet-0.7.3/leaflet.css" />
  <style type="text/css">
    body { margin:0; padding:0; }
    #map { position:absolute; top:0; bottom:0; width:100%; }
  </style>
</head>
<body>
  <div id="map"></div>
  <script>
    var map = L.map('map').setView([0, 0], 3);
    L.tileLayer('http://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
        maxZoom: 18,
        attribution: 'Map data © <a href="http://openstreetmap.org">OpenStreetMap</a> contributors'
    }).addTo(map);
    
  </script>
</body>
</html>
```


##5. Ausblick
Die Zukunft von Webmaps liegt sicherlich immer mehr im Einsatz von [WebGL](https://www.khronos.org/webgl/). Sowohl Google als auch OpenLayers besitzen bereits WebGL Unterstützung, aber auch Mapbox bietet seit wenigen Monaten bereits ein eigenes neues *map-client Framework* auf Grundlage von WebGL/OpenGL an, [Mapbox GL](https://github.com/mapbox/mapbox-gl-js). Webkarten auf Basis von *Tiles* und WebGL ermöglichen unter anderem stufenloses Zoomen,
da die Kacheln hier vollständig beim Client mithilfe der GPU gerendert werden.

![Stufenloser Zoom](https://www.mapbox.com/blog/assets/gl/zoom-levels.png)

Sowie sofortiges Umschalten zwischen verschiedenen Kartenstyles

![Sofortiges Umschalten](https://i.imgur.com/J3R0K9S.gif)

Und viele weitere Funktionalitäten, wie z. B. das einbinden von [Videos](https://www.mapbox.com/drone/video/) in der Kartenansicht. 

Dennoch, wie die große Popularität von Leaflet zeigt, ist der Bedarf an einer einfachen mapping Library sehr groß, so dass davon ausgegangen werden kann, dass auch für kleine und einfache Ansätze weiterhin Bedarf besteht.



##6. Quellen
Alle Quellen sowie nützliche und Interessante Links zum Thema "Map-Client Frameworks":

* [http://wiki.openstreetmap.org/wiki/Slippy_Map]
* [http://wiki.openstreetmap.org/wiki/Slippy_map_tilenames]
* [http://geotux.tuxfamily.org/index.php/en/geo-blogs/item/291-comparacion-clientes-web-v6] Stellenweise veraltete Informationen.
* [https://www.mapbox.com/foundations/how-web-maps-work/]
* [http://www.maptiler.org/google-maps-coordinates-tile-bounds-projection/]
* [http://leafletjs.com/]
* [https://github.com/Leaflet/Leaflet] Leaflet auf GitHub. 
* [http://openlayers.org/]
* [https://github.com/openlayers/ol3] OpenLayers auf GitHub.
* [http://www.macwright.org/2012/05/15/how-web-maps-work.html]
* [http://acuriousanimal.com/blog/2013/05/05/the-problem-with-openlayers/]
* [https://www.khronos.org/webgl/]
* [https://github.com/mapbox/mapbox-gl-js]
* [https://www.openhub.net/p/compare?project_0=OpenLayers&project_1=Leaflet] Stellenweise ungenaue/falsche Informationen.
* [http://www.youtube.com/watch?v=2H9g2DBIuLA] Aktueller Talk von Vladimir Agafonkin auf der JS.geo über die Zukunft von Leaflet und der baldigen 1.0 Veröffentlichung.
* [http://vimeo.com/107472767] Aktueller Talk von der foss4g von Justin Miller über Mapbox GL und möglichkeiten von Vectormaps.
* [http://vimeo.com/106227909] Aktueller Talk von der foss4g über OpenLayers 3
* [https://maptime.github.io/anatomy-of-a-web-map/#0] Herrvorragende Präsentation, die noch einmal alles zusammenfasst was man über moderne webmaps wissen muss.
* [http://www.opengeospatial.org/standards/wmts] OGC Web Map Tile Service Implementation Standard
* [http://mayor2.dia.fi.upm.es/oeg-upm/index.php/en/technologies/172-map4rdf] map4rdf als brücke zwischen mapping und RDF



