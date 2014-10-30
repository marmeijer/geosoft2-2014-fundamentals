Datenbanken
=========

---
Datenbanksystem
---

Ein Datenbanksystem ist ein System zur elektronischen Datenverwaltung. Es besteht aus einem Datenbankmanagementsystem (DBMS)
und einer Datenbank.

**Ziele eine Datenbanksystems**
- Bereitstellung einer abstrakten Sicht auf die Daten
- Verbergen von Details, z.B. wie Daten gespeichert werden
- Große Datenmengen effizient, widerspruchsfrei und dauerhaft speichern  

**Datenbankmanagementsystem** 
- eingesetzte Software, die für das Datenbanksystem installiert und konfiguriert wird
- legt das Datenbankmodell fest
- entscheidend für Funktionalität und Geschwindigkeit des Systems 
- hochkomplexe Softwaresysteme

**Datenbank** 
- logisch zusammenhängender Datenbestand 
- wird von DBMS verwaltet 
- wird für Anwendungssysteme und Benutzer unsichtbar auf nichtflüchtigen Speichermedien abgelegt

Relationale Datenbanken
---
**Allgemeines:**

Die relationale Datenbank ist die am weitesten verbreitete Form der Datenbanksysteme. 8 der 10 meistgenutzten Datenbanken basiert darauf. Dementsprechend gibt es eine intensive Weiterentwicklung und laufende Verbesserungen, auch dank großer Firmen wie Oracle und Microsoft. Die am häufigsten benutzten OpenSource Datenbanken sind [MySQL](http://www.mysql.de/)  und [PostgreSQL](http://www.postgresql.org/).

**Aufbau:**

Diese Datenbanken basieren auf *Tabellen* (Relationen). Die Spalten enthalten dabei die Attribute und sind fest definiert durch ein Relationschemata. Die Zeilen bestehen aus den einzelnen Datensätzen und können dynamisch verändert werden.

**Vorteile / Nachteile:**

Vor allem für viele *einfache* Operationen/Zugriffe eignet sich diese Form der Datenbanken. Datenintegrität und Datenkonsistenz sind immer gesichert. Allerdings gibt es bei sehr komplexen Zugriffen, wo mehrere Relationen auf einmal betrachtet werden müssen, aufgrund der Struktur Leistungsabfälle. Zudem *fehlt es an Dynamik*, da das Relationschemata einmal festgelegt wird und danach nur sehr bedingt flexibel geändert werden kann.




Geodatenbanken
---

Eine Geodatenbank ist eine Datenbank, die neben den Standard Datentypen wie Zeichen, Zahlen usw. 
auch Objekte mit Raumbezug zur Erde enthält. Der Zugriff auf die Daten der Datenbasis 
und die Verwaltung aller Daten der Datenbasis erfolgt über ein GeoDBMS.
Geodatenbanken sind häufig Datengrundlage für Geoinformationssysteme. 

**Geodatenbankmanagementsystem (GeoDBMS)**

Ein Geodatenbankmanagementsystem ist ein vollständiges DBMS mit zusätzlichen Möglichkeiten zur Repräsentation, Abfrage 
und Manipulation von Objekten mit Raumbezug zur Erde. Das GeoDBMS hat Aufgaben eine DBMS 
zu erfüllen. Darüber hinaus unterstützt es räumliche Datentypen und Operationen auf diesen Datentypen.

**Datenarten einer Geodatenbank**
- Rasterdaten
- Vektordaten
- Hybride Daten (Raster- und Vektordaten)

**Dimensionen**
- Zweidimensional:
    Geometriedaten; lediglich x-, y- Koordinaten (Planimetrie) ohne Höhenangaben // Planimetrie beschreibt metrische Problemstellungen der ebenen Geometrie
    
- Zwei-plus-eindimensional:
    Planimetrie + Digitales Geländemodell
    
- Zweieinhalbdimensional: 
    Speicherung der Höhe z als Attribut der Lagegeometrie 
    
- Dreidimensional: 
    Speicherung der x,y,z - Koordinaten in hinreichender Dichte. Weitere Unterscheidung in Linienmodell, 
    Flächenmodell und Volumenmodell 
    
- Vierdimensional: 
    Zusätzliche Speicherung des Zeitparameters t neben den x,y,z - Koordinaten
    Insbesondere wichtich für zeitliche Dokumentation geowissenschaftlicher Fragen 
    
**Objekte einer Geodatenbank** 

Einfache geometrische Objekte:
- Punkt
- Linie
- Polygon

Komplexe geometrische Objekte:
- 3D-Objekte
- lineare Netzwerke 
- unregelmäßiges Dreiecksnetz (TIN) // TIN beschreibt die Möglichkeit zur Modellierung von Oberflächen auf Grundlage einer 3D-Punktwolke
- Topologische Oberfläche
    
**Funktionalitäten einer Geodatenbank**
- geometries oder features genannt

Folgende Operationen werden standardmäßig bereitgestellt:
- Räumliche Messungen: Länge einer Linie berechnen, Distanz zwischen Punkten oder Geometrien...
- Räumliche Funktionen: bereits existierende features modifizieren, manipulieren und so neue features erzeugen
- Räumliche Eigenschaften/Relationen: Erlaubt true/false Abfragen über raümlichen Zusammenhang zwischen Geometrien. 
Bsp: Überlappen sich die beiden Polygone?
- Geometrische Konstruktoren: Erzeugen neuer Geometrien, z.B. durch Spezifikation/Modifikation der Eckpunkte, die die Geometrie definieren
Informationsfunktion: Abfragen, die spezifische Information über ein feature liefern
    


**Beispiel einer Geodatenbank**

[PostGIS] (postgis.net) ist eine Open Soruce Anwendung, die zusätzlichen Support für geographische Objekte 
für die objektrelationale PostgreSQL Datenbank liefert. Ein Standard-Datentyp 'geometry' wurde mit 
entsprechenden Funktionen implementiert. PostGIS richtet sich nach den [Simple Features for SQL specification] (http://www.opengeospatial.org/standards/sfo) des Open Geospatial Consortium (OGC).   

NoSQL
---
**Allgemeines:**

NoSQL bedeutet 'Not only SQL'. Es behandelt Datenbanken welche nicht auf eine herkömmliche Architektur basieren, sondern auf eine welche dynamisch und erweiterbar ist. D.h. es herrscht keine festes Schema. Die Entwicklung dieser Datenbanken ist meist auf den jeweiligen Anwendungsfall zugeschnitten. Daher gibt es viele sehr unterschiedliche NoSQL Datenbanktypen. Früher gab es lange nur SQL Datenbanken, aber seit ein paar Jahren werden diese immer beliebter. Firmen, wie zum Beispiel [Facebook](http://www.infoq.com/news/2014/06/facebook-apollo) entwickeln diese.

**Beispiel [CouchDB](http://couchdb.apache.org/):**

Diese Form ist eine *dokumentorientierte Datenbank*, was bedeutet, dass eine Speicherung unstrukturierter Daten mit flexibler Attributewahl Praxis ist. Dies ist vor allem positiv für die Skalierbarkeit und den Austausch zwischen Off-/Online Daten. Einsatzgebiet ist beispielsweise ist der Abgleich zwischen Dokumenten auf einem PC und Netzwerken. Mit der Erweiterung [“GeoCouch”](https://github.com/couchbase/geocouch) ist auch der Umgang mit GeoDaten möglich. Diese Erweiterung wird mittlerweile professionell weiterentwickelt.
Ein weiteres Beispiel für solch eine dokumentorientierte Datenbank ist [MongoDB] (http://www.mongodb.org/), welche wesentlich verbreiteter ist und auch entsprechende Erweiterungen für den räumlichen Einsatz unterstützt, z.Beispiel [GeoSpatial Indexes](http://docs.mongodb.org/manual/applications/geospatial-indexes/) .

**Beispiel [Neo4J](http://neo4j.com/):**

Diese *Graphen-Datenbanken* bestehen nur aus Knoten, Beziehungen und den dazugehörigen Attributen. Daher eignet sich diese Art der NoSQL Datenbanken besonders gut für die Umsetzung komplexer Beziehungen zwischen Relationen. Auch hier gibt es wieder eine große Flexibilität. Sie werden häufig für die Verknüpfung von Daten in sozialen Netzwerken verwendet. [“Neo4j Spatial”](https://github.com/neo4j-contrib/spatial) ist eine Bibliothek, welche die Verwendung von räumlichen Daten innerhalb von Neo4J erlaubt.

Array Datenbanken 
---

Array Datenbanken speichern Daten in einer fest gegebenen Anzahl (mind. 1) von Dimensionen ab. Daher eignen sie sich besonders für Bilder, aber auch für Verknüpfungen zwischen Koordinaten und einem weiteren Faktor (zum Beispiel Ozeankoordinaten (3-dim.) in Verbindung mit Temperatur, insgesamt 4 Dimensionen). Dadurch kommen sie vor allem in der Wissenschaft zum Einsatz. Die meisten der Implementierungen sind auf Geodaten ausgerichtet und benötigen keine weiteren Bibliotheken. Bekannte Umsetzungen sind hierbei [Rasdaman] (http://www.rasdaman.de/), [MonetDB] (https://www.monetdb.org/Home), [SciDB] (http://www.scidb.org/) oder die bereits erwähnte OpenSource Umsetzung [PostGIS](http://postgis.net/). 



Triple Store
---

- Triplestores dienen zur Speicherung von RDF in Datenbanken und Datenstrukturen
- bietet persistente Speicherung und Zugriff auf RDF-Graphen
- Zugriff erfolgt auch über Query-Language (SparQL)
- Standard hier: [GeoSPARQL] (http://www.geosparql.org)

**Vorteile**

+ schnelle Abfrage der benötigten Informationen
+ Triple Store repräsentiert die benötigte Information bereits in einem Format, das sich so extrahieren lässt 
+ komplexe Abfragen einfacher

**Nachteile**

- Kontext bzgl. natürlicher Sprache fehlt
- z.T. schwierig Informationen zu speichern, die sich nicht exakt in einem Triple Store bzw. in RDF 
  repräsentieren lassen
- nicht leicht Rückschlüsse zu ziehen  

**Beispiele (open source)**
- [OpenLink Virtuoso] (http://virtuoso.openlinksw.com/)
- [Garlik 4store] (http://4store.org/)
- [Bigdata(R)] (http://www.bigdata.com/blog/)
- [YARS2] (http://sw.deri.org/2004/06/yars/)
- [Jena TDB] (http://jena.apache.org/documentation/tdb/index.html) 
- [Jena SDB] (https://jena.apache.org/documentation/sdb/)
- [Mulgara] (http://www.mulgara.org/)
- [Jena with PostgreSQL] (http://jena.apache.org/) 
- [Kowari] (http://www.kowari.org/)
- [3store with MySQL 3] (http://threestore.sourceforge.net/) 
- [Sesame] (http://www.rdf4j.org)

**Ergänzungen**

Es gibt Tools, die es ermöglichen, in RDBMS gespeicherte Daten im RDF-Format darzustellen: 

- [R2RML] (http://www.w3.org/TR/r2rml)
- [morph-rdb] (http://mayor2.dia.fi.upm.es/oeg-upm/index.php/es/technologies/315-morph-rdb)
- [triplify] (http://triplify.org/Overview)
- [RDB2RDF] (http://www.w3.org/2001/sw/rdb2rdf/)

**Beispielhafte Abfragen**

*PostGIS(SQL)*:
```sh
SELECT attribute FROM table WHERE condition=true
```

*Triple Stores (GeoSPARQL)*:
```sh
SELECT ?what
WHERE {
  ?what geo:hasGeometry ?geometry .
  ?geometry geo:asWKT ?wkt .
 
  FILTER(geof:within(?wkt,
     "POLYGON((
-77.089005 38.913574,
-77.029953 38.913574,
-77.029953 38.886321,
-77.089005 38.886321,
-77.089005 38.913574
))"^^geo:wktLiteral))
}
```
Quoted from [wiki] (http://en.wikipedia.org/wiki/GeoSPARQL)



Fazit
---

Nach bisheriger Kenntnis stellt unser Projekt folgende Anforderungen an die Datenverwaltung: Datenkonsistenz, viele einfache Zugriffe, verschiedene Benutzer und das Speichern von Geodaten. Flexible und dynamische Relationschemata/Attribute werden nicht benötigt, da alle Felder fest vorgegeben sind.
Diese Anforderungen werden unserer Meinung nach am besten mit relationalen Datenbanken erfüllt. Eine passende und kostenlose Implementiertung wäre [MySQL] (http://www.mysql.de). Diese verfügt über alle genannten Kriterien und kann auch explizit Geodaten speichern ("Spatial Data Types").




Quellen
---

Datenbanksystem:

* http://de.wikipedia.org/wiki/Datenbank

Relationale Datenbank:

* http://de.wikipedia.org/wiki/Datei:Begriffe_relationaler_Datenbanken.svg

* http://db-engines.com/de/ranking

* http://www2.pmf.fh-goettingen.de/~jwitte/lehre/Medieninformatik/Datenbanken/Vorlesungskripte/Das%20Relationenmodell.pdf

Geodatenbank:

* http://wikis.gm.fh-koeln.de/wiki_db/Datenbanken/Geodatenbank

* http://www.imn.htwk-leipzig.de/~jwinkle3/scripts/OS_Moderne_DB_Handout.pdf

* http://en.wikipedia.org/wiki/Spatial_database

NoSQL:

* http://www.heise.de/open/artikel/NoSQL-im-Ueberblick-1012483.html?artikelseite=2

* http://de.wikipedia.org/wiki/NoSQL

* http://www.nosqldatabases.com/main/tag/neo4j

* http://www.nosqldatabases.com/main/2010/8/5/san-diego-nosql-meetup-slides.html

* http://www.rasdaman.de/

* http://www.paradigm4.com/why-an-array-database/

* http://en.wikipedia.org/wiki/Rasdaman

Triple Store:

* http://virtuoso.openlinksw.com/dataspace/doc/dav/wiki/Main/VOSRDFFAQ

* http://www.bioontology.org/wiki/images/6/6a/Triple_Stores.pdf

* http://www.w3.org/wiki/LargeTripleStores#Jena_with_PostgreSQL_.28200M.29

* http://en.wikipedia.org/wiki/Triplestore

* http://dna.fernuni-hagen.de/Tutorial-neu.pdf

