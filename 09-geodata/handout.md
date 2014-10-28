
#Geodatenformate

von Simon Schulte und Tobias Tasse

##Häufige Schnittstellen:

- WMS
- WFS
- SWE Common


##Geodatenformate die,...
 


**...XML basiert sind,**

- O&M
- tagged data
- GML
- KML
- RSS
- Atom

**...Daten zu Geometrien enthalten,**

- Shapefiles
- Simple Features
- GeoPackages
- NetCDF

**...Bilddaten enthalten,**

- GeoTIFF

… **unter Sonstiges einzuordnen sind.**

- GeoJSON
- LinkedGeoData



------------------------------
------------------------------

##Häufige Schnittstellen:

###WMS

- OpenGIS Web Map Service (WMS)
- definiert vom Open Geospatial Consortium (OGC)
- Spezialfall eines Web Services
- Exkurs Web Service:
	- ist eine Softwareanwendung, die über ein Netzwerk für die direkte Maschine-zu-Maschine-Interaktion bereitgestellt wird
	- jeder Webservice besitzt einen Uniform Resource Identifier (URI), über den er eindeutig identifizierbar ist
	- besitzt Schnittstellenbeschreibung in maschinenlesbarem Format (XML-Artefakt, meist WSDL), wodurch definiert wird wie mit Webservice zu interagieren ist
	- Anfragen an ein WMS werden in Form einer HTTP Abfrage ausgeführt und die Antwort wird in Form von einer XML gegeben
- Visualisierung von Geodaten in Browser
	- HTTP-Schnittstelle zum Abrufen von Auszügen aus Landkarten, die von einer oder mehreren geo-räumlichen Datenbanken bereitgestellt werden
	- die WMS Anfrage definiert den gewünschten Bereich und die geographischen Layer die verarbeitet werden sollen
	- die Anfrage liefert Kartenmaterial, dass, meist wiedergegeben in Dateiformaten wie JPG, PNG, etc., in einer Browser-Anwendung dargestellt wird

- Geodatenformate:
  -
  - zur Darstellung → JPG, PNG, etc.
  

**_Alleinstellungsmerkmal:_**
Visualisierung von Geodaten in Browser via Web Service
→ Zurückgegebenes Format: JPG, PNG, etc.


Quellen und hilfreiche Links:

[http://de.wikipedia.org/wiki/Web\_Map\_Service](http://de.wikipedia.org/wiki/Web_Map_Service) (letzter Aufruf am 01.10.2014)

[http://www.opengeospatial.org/standards/wms](http://www.opengeospatial.org/standards/wms) (letzter Aufruf am 01.10.2014)

[http://de.wikipedia.org/wiki/Webservice](http://de.wikipedia.org/wiki/Webservice) (letzter Aufruf am 01.10.2014)

[http://de.wikipedia.org/wiki/Open\_Geospatial\_Consortium](http://de.wikipedia.org/wiki/Open_Geospatial_Consortium) (letzter Aufruf am 01.10.2014)

###WFS

- OpenGIS Web Feature Service (WFS)
- definiert vom Open Geospatial Consortium (OGC)
- internetgestützter Zugriff auf Geodaten innerhalb eines verteilten GIS
- beschränkt sich ausschließlich auf Vektordaten, wie sie in Datenbanken abgelegt werden können
- im Rahmen der Spezifikationen des OGC ermöglicht ein WFS den Zugriff auf geographische Features in Datenbanken und gibt Ergebnis mindestens als unabhängiges Dateiformat Geography Markup Language (GML) zurück
- Hier:
  - Feature – allgemeine Abstraktion eines realen Faktums
  - Feature Type – ist Darstellung mithilfe eines Namens, weiteren Attributen
  - geographische Feature Types - + Geometrie
    - Beispiel: Feature Type „Fluss", Instanz eines Features ist ein konkreter Fluss

- Technischer Hintergrund:
	- HTTP-Anfrage vom Client an WFS gesendet
	- es gibt sechs Operationen, die von einem Benutzer angefragt werden können;
  	- **_für uns interessant:_**
		 - GetCapabilities – liefert XML-Dokument mit allgemeinen Angaben zum Anbieter des WFS, abgefragte Feature Types und mögliche Operationen

		- GetGmlObject – liefert einzelne Elemente aus der GML-Datei per Xlink

- Geodatenformate:
  - GML
  - XML

**_Alleinstellungsmerkmal:_**
Visualisierung von Features von Geodaten in Browser via Web Service
→ Zurückgegebenes Format: GML(XML)

Quellen und hilfreiche Links:

[http://de.wikipedia.org/wiki/Web\_Feature\_Service](http://de.wikipedia.org/wiki/Web_Feature_Service) (letzter Aufruf am 01.10.2014)

[http://www.opengeospatial.org/standards/wfs](http://www.opengeospatial.org/standards/wfs) (letzter Aufruf am 01.10.2014)

[http://www.weichand.de/2011/11/30/grundlagen-web-feature-service-wfs-2-0/](http://www.weichand.de/2011/11/30/grundlagen-web-feature-service-wfs-2-0/) (letzter Aufruf am 01.10.2014)

###SWE Common

- Definiert vom Open Geospatial Consortium (OGC)
- Zum Austausch von Sensoren Daten zwischen Knoten des OGC® Sensor Web Enablement (SWE)
- Definiert niedriege Datenstrukturen wodurch Sensoren-Daten in einer selbst definierenden Art und mit einer semantischen Beziehung verschlüsselt und übertragen werden können
- SWE Common 1.0 ist definiert im OGC SensorML1.0 Standard 
- Viele verschiedene Standards : OGC Sensor Model Language (SensorML), Encoding Standard, Sensor Observation Service (SOS) Interface Standard, Sensor Planning Service (SPS) Interface Standard

**_Alleinstellungsmerkmal:_**
OGC Standard um Daten von Sensoren untereinander auszutauschen mit vielen anderen Möglichkeiten

Quellen und hilfreiche Links:

[http://www.opengeospatial.org/standards/swecommon](http://www.opengeospatial.org/standards/swecommon) (letzter Aufruf am 01.10.2014)

[http://www.opengeospatial.org/standards/sensorml](http://www.opengeospatial.org/standards/sensorml). (letzter Aufruf am 01.10.2014)

[http://www.knmi.nl/~wauben/HIM/Implementation\_and\_documentation\_of\_Sensor\_Web\_Enablement\_at\_KNMI.pdf](http://www.knmi.nl/~wauben/HIM/Implementation_and_documentation_of_Sensor_Web_Enablement_at_KNMI.pdf) (letzter Aufruf am 01.10.2014)







#Geodatenformate, die...

##...XML basiert sind:

###Observations and Measurements (O&M)

- OGC und ISO Standard
- spezifiziert eine XML-Implementation für das OGC und ISO O&M conceptual model (OGC Observations and Measurements v2.0 und ISO/DIS 19156), inklusive einem Schema für Sampling Features
- es ist ein Standard zur Modellierung von Observationen und zur Beschreibung des Zusammenhangs zwischen dem räumlichen Zielobjekt das observiert wird, der gemessenen „properties & measurement procedure" und den erfassten Daten, die aus der Observation resultieren
- basiert auf Geography Markup Language (GML)
- wichtig für Sensor Web Enablement (SWE Framework), SensorML und Sensor Observation Service (SOS)

**_Alleinstellungsmerkmal:_**
Standard zur Modellierung von Observationen inklusive Beschreibung des allgemeinen Zusammenhangs
→ GML-basiert

Quellen und hilfreiche Links:

[http://www.opengeospatial.org/standards/om](http://www.opengeospatial.org/standards/om) (letzter Aufruf am 01.10.2014)

[http://www.ogcnetwork.net/om](http://www.ogcnetwork.net/om) (letzter Aufruf am 01.10.2014)

[http://www.spatineo.com/2012/02/what-is-an-om-observation-and-why-should-you-care/](http://www.spatineo.com/2012/02/what-is-an-om-observation-and-why-should-you-care/) (letzter Aufruf am 01.10.2014)

###Tagged data

- Auszeichnung eines Datenbestandes mit zusätzlichen Informationen
- Zu finden in Auszeichnungssprachen wie SGML, HTML oder auch XML
- Dateiformate
  - Ein Tag bezeichnet in der Speicherung von Daten in Dateien eine Meta- oder Zusatzinformation, die der Datei angefügt wird
  - Beispiele:
    - ID3-Tag bietet in Musikdateien Informationen über Titel, Genre, etc.
    - TIFF, wo spezielle Daten zur Georeferenz zusätzlich zu den sichtbaren Rasterdaten in die Bilddatei eingebettet werden
    - Zur zusätzlichen Auszeichnung von beliebigen Daten, meist Fotos, gibt es Exif

Beispiel:

Aus XML-Beispiel
```
<Points Of Interest
    <Locations>
      <Address>Reiten</Address>
      <Address>Golfen</Address>
      <Address>Lesen</Address>
    </Locations>
</Points Of Interest>
```
Tags sind hier zum Beispiel 
```
<Locations></Locations> und <Address></Address>.
```
**_Alleinstellungsmerkmal:_**
Speicherung von Zusatz-/Metainformationen in XML, HTML oder SGML

Quellen und hilfreiche Links:

[http://en.wikipedia.org/wiki/Tag\_%28metadata%29](http://en.wikipedia.org/wiki/Tag_%28metadata%29) (letzter Aufruf am 01.10.2014)

###GML

- Geography Markup Language (GML)
- OGC(Entwickler) und ISO Standard
- basierend auf XML
- ist eine XML Grammatik, d.h. Text, um geographische Objekte zu beschreiben und auszutauschen
- Softwareunabhängiger Austausch von geographischen Informationen (Geometrie und Eigenschaften des Features) zwischen Computersystemen
- dient sowohl als Modellierungssprache für Geographische Systeme wie auch als offenes Austauschformat für räumliche Transaktionen über das Internet
- generisches Objektmodell, das nicht nur konventionelle Vektordaten oder einfache Objekte beinhaltet, sondern auch multidimensionale Rasterdaten und einige Elemente von Sensordaten
- nützlich, weil Fähigkeit, alle Arten von räumlichen Informationen zu integrieren

- Warum GML und kein anderer Encoding Standard für geographische Objekte wie etwa COGIF, SAIF, oder Sonstige?

- 
  - Ist ein einfaches textbasiertes Encoding von geographischen Features
  - Ist ein OGC und ISO Standard, der weltweit anerkannt ist
  - basiert auf XML
    - wichtig weil:

1. XML bietet Methode zum Überprüfen von Datenvollständigkeit/Datenrichtigkeit

2. XML Dokumente können schon von einem einfach Text Editor gelesen und bearbeitet werden

3. XML ist einfach zu transformieren (via XSLT, Java, C++, etc.)

Beispiel:

Schulgebäude

```
	<Feature   fid="142" featureType="school" > 
  	 <Description>Balmoral Middle School</Description>> 
  	 <Property Name="NumFloors" type="Integer" value="3"/> 
 	  <Property Name="NumStudents" type="Integer" value="987"/> 
  	     <Polygon  name="extent" srsName="epsg:27354"> 
    	        <LineString  name="extent" srsName="epsg:27354"> 
    	            <CData> 
      	            491888.999999459,5458045.99963358 491904.999999458,5458044.99963358 
      	            491908.999999462,5458064.99963358 491924.999999461,5458064.99963358 
      	            491925.999999462,5458079.99963359 491977.999999466,5458120.9996336 
      	            491953.999999466,5458017.99963357 </CData> 
     	   </LineString> 
  	  </Polygon> 
	</Feature>
```    
**_Alleinstellungsmerkmal:_**
Beschreibung von räumlichen Objekten in XML Grammatik


Quellen und hilfreiche Links:

[http://www.w3.org/Mobile/posdep/GMLIntroduction.html](http://www.w3.org/Mobile/posdep/GMLIntroduction.html)(Punkt 3.0, letzter Aufruf am 01.10.2014)

[http://live.osgeo.org/de/standards/gml\_overview.html](http://live.osgeo.org/de/standards/gml_overview.html) (letzter Aufruf am 01.10.2014)


###KML

- Keyhole Markup Language (KML)
- .kml, .kmz
- Entwickelt von Google Inc. und bekannt geworden durch Google Earth
- Erweiterung von XML
- Heute OGC Standard 
- Auszeichnungssprache zur Beschreibung von Geodaten
- Steht für die Visualisierung geographischer Informationen und kann verwendet werden um GML-Inhalte darzustellen
- KML-Dokumente können Geodaten sowohl in Vektor- wie auch in Rasterform enthalten
- Vektorobjekte (Punkt, Linie, etc.) werden als Placemark-Elemente modelliert
  - Placemark-Elemente können enthalten: Geometrie, Name, Beschreibung, vordefinierten Stil, Zeitstempel etc.

- Luft- und Satellitenbilder werden als GroundOverlay-Elemente modelliert
  - GroundOverlay-Elemente können ähnliches enthalten, nur anstelle der Geometrie muss ein Koordinatenausschnitt zur Georeferenzierung der Rasterdaten definiert werden

Beispiel:

KML-Code für ein einfaches Placemark:
```
	<?xml version="1.0" encoding="UTF-8"?>
	<kml xmlns="http://www.opengis.net/kml/2.2">
	<Placemark>
	<name>Simple placemark</name>
	<description>Attached to the ground. Intelligently places itself 
	at the height of the underlying terrain.</description>
	<Point>
	<coordinates>-122.0822035425683,37.42228990140251,0</coordinates>
	</Point>
	</Placemark>
	</kml>
```

**_Alleinstellungsmerkmal:_**
Ähnlich wie GML, aber speziell für Google-Dienste entwickelt (Placemark-Elemente)


Quellen und hilfreiche Links:

[http://de.wikipedia.org/wiki/Geography\_Markup\_Language](http://de.wikipedia.org/wiki/Geography_Markup_Language)(letzter Aufruf am 01.10.2014)

[http://de.wikipedia.org/wiki/Keyhole\_Markup\_Language](http://de.wikipedia.org/wiki/Keyhole_Markup_Language)(letzter Aufruf am 01.10.2014)

[https://developers.google.com/kml/documentation/kml\_tut?hl=de](https://developers.google.com/kml/documentation/kml_tut?hl=de) (Tutorial)(letzter Aufruf am 01.10.2014)

[http://www.opengeospatial.org/standards/kml](http://www.opengeospatial.org/standards/kml) (letzter Aufruf am 01.10.2014)
###Really Simple Syndication

####RSS 

- ermöglicht es die Inhalte einer Seite leicht zu teilen
- Daten können automatisch aktualisiert werden
- Dienste werden in Form von sogenannten RSS-Channels angeboten
- Feeds können durch Dienste nach Quellen oder Stichworten gefiltert und zu einem neuen RSS-Feed zusammengesetzt werden.
- zählt zu den ersten Anwendungsgebieten des semantischen Webs.
- Nur Formate wie „escaped", HTML und reinen Text

####GeoRSS

- ist ein neuer Standard der es ermöglicht Georeferenzierungen durch Web Feeds zu teilen
- Zwei Standards: GeoRSS-Simple und GeoRSS-GML
- GeoRSS-simple ist ein Format was nur für einfache Geometrien wie point, line, box, polygon unterstützt.
- GeoRSS-GML unterstützt mehr Geometrien als Geo-RSS-Simple und dazu noch andere Koordinatensysteme als WGS1984. Dabei basiert es auf dem OGC Standard GML.


Beispiel RSS-Datei
```
	<?xml version="1.0" encoding="UTF-8" ?>
	<rss version="2.0">

	<channel>
	  <title>W3Schools Home Page</title>
	  <link>http://www.w3schools.com</link>
	  <description>Free web building tutorials</description>
	  <item>
	    <title>RSS Tutorial</title>
	    <link>http://www.w3schools.com/rss</link>
	    <description>New RSS tutorial on W3Schools</description>
	  </item>
	  <item>
	    <title>XML Tutorial</title>
	    <link>http://www.w3schools.com/xml</link>
	    <description>New XML tutorial on W3Schools</description>
	  </item>
	</channel>
	</rss>
```
GeoRSS-Simple:
```
		<georss:point>40.533203 -105.0712</georss:point>
```



GeoRSS-GML
```
<GeoRSS:where>
        <gml:Point>
           <gml:pos>40.533203 -105.0712</gml:pos>
        </gml:Point>
      <GeoRSS:where>
```
**_Alleinstellungsmerkmal:_**
-> Große Mengen an Inhalt können per RSS Feed, in einem einheitlichen Format, zugänglich gemacht werden
-> GeoRSS dient dazu Geo-Inhalte über RSS Feeds zu teilen
 

Quellen und hilfreiche Links:_de.wikipedia.org/wiki/RSS (letzter Aufruf am 01.10.2014)_

[http://www.opengeospatial.org/pressroom/pressreleases/580](http://www.opengeospatial.org/pressroom/pressreleases/580) (letzter Aufruf am 01.10.2014)

Tutorial: [http://www.w3schools.com/rss/](http://www.w3schools.com/rss/) (letzter Aufruf am 01.10.2014)





###Atom

- Basiert auf XML
- Atom Syndication Format(ASF) ermöglicht den plattformunabhängigen Austausch von Informationen
- Atom Publishing Protocol(APP) zum Bearbeiten und Erstellen von HTML und XML basierten Webressourcen
- Unterstützt mehr Formate als RSS
- Feeds sind sehr modular, sie erlauben zusätzliche Attribute (beheben Darstellungsprobleme vom RSS-Standard)
- INSPIRE Atom Feeds erlauben das automatisierte Downloaden von Geodaten die in dem Feed bereitgestellt werden


Beispiel Atom

``` 
	<?xml version="1.0" encoding="utf-8"?>
	<feed xmlns="http://www.w3.org/2005/Atom">
  	<author>
    <name>Autor des Weblogs</name>
  </author>
  <title>Titel des Weblogs</title>
  <id>urn:uuid:60a76c80-d399-11d9-b93C-0003939e0af6</id>
  <updated>2003-12-14T10:20:09Z</updated>
 
  <entry>
 <title>Titel des Weblog-Eintrags</title>
    <link href="http://example.org/2003/12/13/atom-beispiel"/>
    <id>urn:uuid:1225c695-cfb8-4ebb-aaaa-80da344efa6a</id>
    <updated>2003-12-13T18:30:02Z</updated>
    <summary>Zusammenfassung des Weblog-Eintrags</summary>
    <content>Volltext des Weblog-Eintrags</content>
  </entry>
</feed>
```
**_Alleinstellungsmerkmal:_**
-> Atom bietet ähnliche Funktionen wie RSS, es behebt jedoch Darstellungsprobleme und ist modularer als RSS

Quellen und hilfreiche Links:

[http://software-design.de/it-blog/show/website-feeds-rss-oder-atom-feed](http://software-design.de/it-blog/show/website-feeds-rss-oder-atom-feed) (letzter Aufruf am 01.10.2014)

[http://www.intertwingly.net/wiki/pie/FrontPage](http://www.intertwingly.net/wiki/pie/FrontPage) (letzter Aufruf am 01.10.2014)

[http://www.weichand.de/2012/06/20/inspire-pre-defined-atom-download-service-client-for-qgis/](http://www.weichand.de/2012/06/20/inspire-pre-defined-atom-download-service-client-for-qgis/)(letzter Aufruf am 20.10.2014)

[http://fmepedia.safe.com/articles/Samples_and_Demos/Read-INSPIRE-ATOM-Download-Services-with-FME](http://fmepedia.safe.com/articles/Samples_and_Demos/Read-INSPIRE-ATOM-Download-Services-with-FME) (letzter Aufruf am 20.10.2014)



##...Daten zu Geometrien enthalten:



###Shapefiles

- Dateiformat für Geodaten, dass ursprünglich für die Software ArcView der Firma ESRI entwickelt wurde
- heute im Desktop-GIS-Umfeld verbreitet
- Support von freien sowie kommerziellen Programmen ist nirgends so gut wie beim Shapefile
- Shapefile besteht aus mindestens drei Dateien:
  - .shp – zur Speicherung der Geometriedaten
  - .dbf – Sachdaten im dBASE-Format
  - .shx – Index der Geometrie zur Verknüpfung der Sachdaten (auch Attributdaten)
  - weitere Dateien: siehe http://de.wikipedia.org/wiki/Shapefile /Aufbau/Optionale Dateien

- in einer Shapefile können jeweils nur Elemente eines Typs enthalten sein (Punkt, Linie, Fläche(Polygone) oder Multi-Punkte
- es können sowohl 2D als auch 3D Geometrien erfasst werden
- Optional kann das Design eines Shapefiles in einer Legendendatei .avl oder .lyr(neuer) gespeichert werden und nach dem Einladen einer Shapefile als Themeneigenschaft hinzugefügt werden
- Größe der Shp- und DBF-Dateien darf 2 GB nicht überschreiten

**_Alleinstellungsmerkmal:_**
„Container“ der Geometriedaten, Sachdaten und einen Index zur Verknüpfung beider enthält
→ für Desktop-GIS 


Beispiele zu Shapefiles:

[http://www.geofabrik.de/de/data/shapefiles.html](http://www.geofabrik.de/de/data/shapefiles.html) (letzter Aufruf am 01.10.2014)

(Beispiele enthalten verschiedene Layer mit Punkten, Linien, Flächen und Multi-Punkten)

Quellen und hilfreiche Links:

[http://de.wikipedia.org/wiki/Shapefile](http://de.wikipedia.org/wiki/Shapefile) (letzter Aufruf am 01.10.2014)

###Simple Features

- ein Standard des Open Geospatial Consortium und der International Organization for Standardization (ISO 19125) 
- definiert eine gültige Architektur für geografische Daten und deren Geometrien.

Folgende instanzierbare Klassen beinhaltet das Modell:

- Punkte (Point) 
- Linien (LineString) 
- Polygone (Polygon) 
- Mehrere Punkte (MultiPoint) 
- Mehrere Linien (MultiLineString) 
- Mehrere Polygone (MultiPolygon) 
- Sammlung dieser Geometrien (GeometryCollection) 

Sämtliche Geometrien leiten sich von der abstrakten Klasse Geometry ab.

1. Grundlegende Abfragen: 
   - Geometrietyp (GeometryType),
   - die Abfrage der Ausdehnung (Envelope),
   - die Rückgabe der Geometrie als Text (AsText).

2. räumliche Beziehungen: 
   - ob Objekte gleich sind (Equals),
   - sich schneiden (Intersects) ,
   - berühren (Touches).

3. räumlichen Analyse:
   - Pufferzone (Buffer),
   - Verschneidung (Intersection),
   - Differenz (Difference)


Verwendung:

- weite Verbreitung in der Geoinformatik,in Open Source und in proprietären Programmen
- Zwei sehr bekannte LGPL(Lesser General Public License) lizenzierte Programmbiblotheken sind die JTS Topology Suite und GEOS
- JTS stellt eine API für JAVA
- GEOS eine API für C++
- GEOS in PostGIS kann WellKnownText direkt in der Datenbank von PostgreSQL verwendet werden

**_Alleinstellungsmerkmal:_**
-> Definiert grundlegende Geometrien, die in einer "GeometryCollection" gespeichert sind
-> Haben wir bereits in Geosoftware 2 benutzt.


Quellen und hilfreiche Links:

[http://de.wikipedia.org/wiki/Simple\_Feature\_Access](http://de.wikipedia.org/wiki/Simple_Feature_Access) (letzter Aufruf am 01.10.2014)

[http://www.opengeospatial.org/standards/sfa](http://www.opengeospatial.org/standards/sfa) (letzter Aufruf am 01.10.2014)

###GeoPackages

- OGC® Encoding Standard definiert GeoPackages
- Ein Offenes Format für Informationen mit Raumbezug
- SQLite-basiertes Format dass Vector features und Bild Kacheln effizient speichert und überträgt
- Direkter Zugriff, das bedeutet ohne ein zwischen Format wie z.B mit einer API


**_Alleinstellungsmerkmal:_**
-> Alternative zu Shapefiles, wurde entwickelt sodass man es auch noch erweitern kann.
-> Ist für Kommerzielle und open-source Software gedacht

Quellen und hilfreiche Links:

[http://www.geopackage.org/](http://www.geopackage.org/) (letzter Aufruf am 01.10.2014)

[http://www.opengeospatial.org/standards/geopackage](http://www.opengeospatial.org/standards/geopackage) (letzter Aufruf am 01.10.2014)

[https://bitbucket.org/luciad/libgpkg](https://bitbucket.org/luciad/libgpkg) (letzter Aufruf am 01.10.2014)

###NetCDF
- steht für Network Common Data Form
- Dateiformat für den Austausch wissenschaftlicher Daten
- binäres Dateiformat und damit durch Angabe der Byte-Reihenfolge im Header maschinenunabhängig ist
- offener Standard
- basiert auf dem Common Data Format (CDF), ist jedoch nicht mehr kompatibel und deutlich weiter entwickelt
- Biblothek ist in C geschrieben mit Schnittstellen zu C++,R, Python, Ruby, Matlab und weitere. Außerdem gibt es noch eine Implementierung in Java

**_Alleinstellungsmerkmal:_**
 -> wird hauptsächlich in der Klimatologie und in Geoinformationssystemen verwendet
 -> schneller Zugriff auf Daten


Quellen und hilfreiche Links:
[http://de.wikipedia.org/wiki/NetCDF](http://de.wikipedia.org/wiki/NetCDF) (letzter Aufruf am 01.10.2014)
[http://www.nodc.noaa.gov/data/formats/netcdf/v1.1/](http://www.nodc.noaa.gov/data/formats/netcdf/v1.1/) (letzter Aufruf am 01.10.2014)
[http://www.unidata.ucar.edu/downloads/netcdf/index.jsp](http://www.unidata.ucar.edu/downloads/netcdf/index.jsp) (letzter Aufruf am 01.10.2014)



##...Bilddaten enthalten:

###GeoTIFF

- .geotiff oder auch nur .tif
- Spezialform eines TIFF-Bildes
- Open Standard
- Entwickelt von Aldus Corporation
- Datenformat zur Speicherung und zum Austausch von Bilddaten
- Durch verlustfreie Speicherung, eignet sich das TIF-Format gut zur Verarbeitung von geographischen Daten, da es bei Satelliten- und Luftbildern bzw. anderen Rasterdaten oft auf hohe Abbildungsgenauigkeit ankommt
  - Sinnvoll für Bilder bzw. Rasterdaten mit hoher Abbildungsgenauigkeit

- Unterschied zu normalen TIF-Format ist, dass spezielle Daten zur Georeferenz zusätzlich zu den sichtbaren Rasterdaten in die Bilddatei eingebettet werden
  - Datei enthält spezifische Angaben über das Koordinatenreferenzsystem

- Informationen werden im Vergleich zu GeoJPEG nicht in externer World File Datei gespeichert, sondern direkt in den Metatags des Bildes
  - GeoJPEG:
    - Ist ein georeferenziertes JPEG

Beispiel:

Es erlaubt, etwa bei Kartenbildern, Luftbildern und ähnlicen Informationen, anzugeben, wo auf der Erde die im Bild dargestellte Situation exakt koordinatenbezogen liegt.

Katalog von Beispiel GeoTIFF Bildern:

[http://www.landesvermessung.sachsen.de/inhalt/produkte/lika/alk/alk\_download.html](http://www.landesvermessung.sachsen.de/inhalt/produkte/lika/alk/alk_download.html)(letzter Aufruf am 01.10.2014)

**_Alleinstellungsmerkmal:_**
Bilddaten mit geographischen Zusatzinformationen und verlustfreie Speicherung
→ mehr Informationen als GeoJPEG durch höheren Detailierungsgrad

Quellen und hilfreiche Links:

[http://de.wikipedia.org/wiki/GeoTIFF](http://de.wikipedia.org/wiki/GeoTIFF)(letzter Aufruf am 01.10.2014)

[http://de.wikipedia.org/wiki/Tagged\_Image\_File\_Format](http://de.wikipedia.org/wiki/Tagged_Image_File_Format)(letzter Aufruf am 01.10.2014)



##Sonstiges:

###GeoJSON

- pen standard (für jeden kostenlos zugänglich und nutzbar)
- GIS File Format
- .json, .geojson
  - größter Unterschied zu anderen GIS Standards ist, dass es kein formaler Standard einer Organisation ist, sondern von einer Gruppe von Entwicklern geschrieben wurde

- zum Kodieren von einfachen geographischen Featuren oder auch von Feature Collections
- GeoJSON besteht immer aus einem Objekt
  - dieses repräsentiert:
    - Geometrie – Punkt, Linie, Polygon, MultiPunkt, MultiLinie oder MultiPolygon
    - Feature – enthält Geometrie + Properties
    - Feature Collection Objects – enthält mehrere Features

Beispiel:

Feature Collection
```
{
  "type": "FeatureCollection",
  "features": [
    {
      "type": "Feature",
      "geometry": {
        "type": "Point",
        "coordinates": [102.0, 0.6]
      },
      "properties": {
        "prop0": "value0"
      }
    },
    {
      "type": "Feature",
      "geometry": {
        "type": "LineString",
        "coordinates": [
          [102.0, 0.0], [103.0, 1.0], [104.0, 0.0], [105.0, 1.0]
        ]
      },
      "properties": {
        "prop1": 0.0,
        "prop0": "value0"
      }
    },
    {
      "type": "Feature",
      "geometry": {
        "type": "Polygon",
        "coordinates": [
          [
            [100.0, 0.0], [101.0, 0.0], [101.0, 1.0], [100.0, 1.0],
            [100.0, 0.0]
          ]
        ]
      },
      "properties": {
        "prop1": {
          "this": "that"
        },
        "prop0": "value0"
      }
    }
  ]
}
```

- nutzt JavaScript Object Notation (JSON); ist eine Erweiterung dessen

- 
  - JSON ist ein kompaktes Datenformat in einer einfach lesbaren Textform zum Zweck des Datenaustausches zwischen Anwendungen
  - Programmiersprachen unabhängig
  - Ersatz für XML in Bereichen, wo Ressourcen (Speicherplatz, CPU-Leistung) sparsam eingesetzt werden sollen
    - Beispiel: Bei der Entwicklung von desktopähnlichen Webanwendungen

- Unterschied zu XML:

- Syntax von JSON ist einfacher gestaltet und erscheint daher oft lesbarer + leichter schreibbar
- XML ist eine Auszeichnungssprache (Gliederung und Formatierung von Texten und anderen Daten) und somit vielseitiger einsetztbar als JSON, das ein Datenaustauschformat ist



JSON-Code:

```
{
  "Herausgeber": "Xema",
  "Nummer": "1234-5678-9012-3456",
  "Deckung": 2e+6,
  "Waehrung": "EURO",
  "Inhaber": {
    "Name": "Mustermann",
    "Vorname": "Max",
    "maennlich": true,
    "Hobbys": [ "Reiten", "Golfen", "Lesen" ],
    "Alter": 42,
    "Kinder": [],
    "Partner": null
  }
}
```

XML-Code:
 
```
<Kreditkarte
  Herausgeber="Xema"
  Nummer="1234-5678-9012-3456"
  Deckung="2e+6"
  Waehrung="EURO">
  <Inhaber
    Name="Mustermann"
    Vorname="Max"
    maennlich="true"
    Alter="42"
    Partner="null">
    <Hobbys>
      <Hobby>Reiten</Hobby>
      <Hobby>Golfen</Hobby>
      <Hobby>Lesen</Hobby>
    </Hobbys>
    <Kinder />
  </Inhaber>
</Kreditkarte>
```

**_Alleinstellungsmerkmal:_**
Ähnlich wie GML, aber einfacher gehalten (nur Datenaustauschformat) und weniger technischer Support


Quellen und hilfreiche Links:

[http://en.wikipedia.org/wiki/GeoJSON](http://en.wikipedia.org/wiki/GeoJSON) (letzter Aufruf am 01.10.2014)

[http://geojson.org/geojson-spec.html](http://geojson.org/geojson-spec.html) (letzter Aufruf am 01.10.2014)

[http://de.wikipedia.org/wiki/JavaScript\_Object\_Notation](http://de.wikipedia.org/wiki/JavaScript_Object_Notation) (letzter Aufruf am 01.10.2014)

[http://de.wikipedia.org/wiki/Auszeichnungssprache](http://de.wikipedia.org/wiki/Auszeichnungssprache) (letzter Aufruf am 01.10.2014)

###LinkedData



- im World Wide Web frei verfügbare Daten, die per URI identifiziert sind, per HTTP abgerufen werden können und ebenfalls per URI auf andere Daten verweisen



- Entstehung von Web of Data/ Semantic Web



- Grundprinzipien:


	- Verwende URIs als Namen für Dinge
	- Verwende HTTP URIs, damit Leute diese Namen nachschlagen können
	- Wenn jemand einen Namen nachschlägt, biete nützliche Informationen und verwende dabei die Standards (RDF, SPARQL)
	- Biete von dort auch Links auf andere URIs, damit wir mehr Dinge entdecken können


- bekanntes Modell aus Spatial Information Infrastructures


	- http://de.wikipedia.org/wiki/Linked_Open_Data#mediaviewer/File:LOD_Cloud_Diagram_as_of_September_2011.png

Quellen und hilfreiche Links:
[http://de.wikipedia.org/wiki/Linked_Open_Data](http://de.wikipedia.org/wiki/Linked_Open_Data) (letzter Aufruf am 21.10.2014)
[https://www.innoq.com/de/linked-data/](https://www.innoq.com/de/linked-data/) (letzter Aufruf am 21.10.2014)

###LinkedGeoData



- Wissensbasis


- fügt dem Web of Data/ Semantic Web eine räumliche Dimension hinzu


	- d.h.:


		- OpenStreetMap sammelt Informationen


		- diese Informationen werden im LinkedData-Prinzip als RDF zur Verfügung gestellt


		- diese RDF-basierten Informationen werden dem Web of Data hinzugefügt


		- so werden räumliche Informationen zu Suchbegriffen hinzugefügt


			- Bsp.: Suchbegriff „Berlin“ erhält auch räumliche Informationen zu Berlin wie die Koordinaten oder die Fläche


- OpenStreetMap, weil:


	- große Kollektion von räumlichen Daten (mehr als 1 Milliarde Punkte und 100 Millionen Wege)


	- durch öffentlichen Standard frei nutzbar (erweiterbar)


	- Daten stehen nach Linked Data Prinzipien zur Verfügung und sind verkettet mit Dbpedia und Geo-Namen

Quellen und hilfreiche Links:

[http://linkedgeodata.org/About)](http://linkedgeodata.org/About)) (letzter Aufruf am 21.10.2014)
[http://wiki.openstreetmap.org/wiki/LinkedGeoData](http://wiki.openstreetmap.org/wiki/LinkedGeoData) (letzter Aufrug am 21.10.2014)

