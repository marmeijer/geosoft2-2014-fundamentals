#### *Geosoftware 2* ####
#### *Daniel Ummelmann, Michael Rieping* ####

# RESTful Web Services, JSON und OAuth #


## Gliederung: ##

1. RESTful Websevices
1. JSON
1. OAuth

## RESTful Webservices ##

[[Quellen]](#restful-webservices-quellen)

### Was ist REST? [[Q1/Q2/Q3]](#restful-webservices-quellen)###
**REST** steht für: **RE** presentational **S** tate **T** ransfer <br>

Es handelt sich dabei um ein von Roy Fielding 1994 entworfenes Programmierparadigma für Webapplikationen, welches davon ausgeht, dass auf einen Aufruf einer **URI** (**U** niform **R** esource **I** dentifier) immer mit der gleichen Antwort geantwortet wird. <br>

Die Prinzipien nach dem REST funktioniert sind dabei: [[Q1]](#restful-webservices-quellen)<br>

- **Adressierbarkeit:** <br>
  Jede Ressource besitzt eine eindeutige Adresse (URI)
- **Zustandslosigkeit:** <br>
  Jede REST-Nachricht enthält alle benötigten Informationen, somit muss keine offene Verbindung gehalten werden.
- **Einheitliche Schnittstelle** <br>
- **Entkopplung von Ressourcen und Repräsentation:** <br>
  Die gleiche Ressource kann in verschiedenen Repräsentationen dargestellt werden

### Was ist RESTful? [[Q1]](#restful-webservices-quellen)###
Unter RESTful versteht man die Umsetzung des REST-Paradigmas in einer Webanwendung. Dafür muss ein zustandsloses Client-/Server-Protokoll verwendet werden (meistens HTTP/HTTPS). Die wichtigsten (HTTP-) Operationen, die dabei verwendet werden sind dabei: <br>
    
- ```GET```
- ```POST```
- ```PUT```
- ```DELETE```

#### Beispiel: ####

Als Beispiel sehen wir uns einen Aufruf an, der in der HP Gloe-API alle Objekte für die WGS84-Koordinaten 37.234,-122.234 zurückgeben.

Dazu verwenden wir folgenden Header:

```
GET /json/getrec/?lat=37.234&lon=-122.234
Host: http://www.hpgloe.com
Accept: application/json
```


Der Response darauf sieht dann folgendermaßen aus (im JSON-Format):

```JSON
[
  [305.0, "http://www.hp.com", "", null, null, "hp", 37.234052809673, -122.233976388235, 1, 0.0038707032904373973], [27.0, "", "", null, null, "", 37.234, -122.234, 0, 0.0], 
  [13.0, "http://en.wikipedia.org/wiki/KFJC", "", null, null, "wikipedia_city", 37.3205986, -122.14099884, 1, 7.864991161742064],
  [4.0, "http://www.hp.c", "", null, null, "", 37.234, -122.234, 0, 0.0],
  [3.0, "http://en.wikipedia.org/wiki/Middleton_Tract%2C_California", "", null, null, "wikipedia", 37.26683426, -122.20866648, 0, 2.6654883246520082],
  [3.0, "http://en.wikipedia.org/wiki/National_Register_of_Historic_Places_listings_in_Santa_Clara_County%2C_California", "", null, null, "wikipedia", 37.264633176667, -122.074666343333, 0, 9.159602799996797],
  [2.0, "http://en.wikipedia.org/wiki/Los_Trancos_Woods%2C_California", "", null, null, "wikipedia_landmark", 37.34939957, -122.19866435, 1, 8.200834466364913],
  [2.0, "http://en.wikipedia.org/wiki/National_Register_of_Historic_Places_listings_in_San_Mateo_County%2C_California", "", null, null, "wikipedia", 37.126800535, -122.308498385, 0, 8.46873826798457],
  [2.0, "http://en.wikipedia.org/wiki/Boulder_Creek%2C_California", "", null, null, "settlements", 37.12820053, -122.124500275, 0, 9.469549354050134],
  [2.0, "http://www.panoramio.com/photo/4489152", "Silicon%20Valley%20View%20From%20Mountain%20Winery", null, null, "photos", 37.2580986, -122.06300354, 0, 9.54463050551031]
]
```

Ihr könnt das Beispiel und viele weitere zu dieser API auf dieser Seite finden -> [HP-Gloe Rest-Examples](http://wiki.hpgloe.com/restexamples "HP-Gloe Rest-Examples").

### Warum REST? [[Q1]](#restful-webservices-quellen)<br> ###
Da das bis dato vorherschende SOAP (**S**imple **O**bject **A**ccess **P**rotocol) sehr kompliziert war, herrschte ein großes Verlangen nach Vereinfachung (viele APIs basieren bis heute auf SOAP). <br>

*Tabelle 1: Stärken und Schwächen von SOAP:*

|                    Stärken                    |            Schwächen         |
| --------------------------------------------- | ---------------------------  |
|     große Mächtigkeit der SOAP-Envelopes      | komplizierte XML-Nachrichten |
| Programmiersprachen- und Plattform-unabhängig |         großer Overhead      |
|                        -                      |         rechenintensiv       |    

#### Beispiel: ####

In diesem Beispiel sehen wir uns eine Webanwendung an, die das Telefonbuch des IFGIs verwaltet und wir möchten mit einem Aufruf den Benutzer mit der UserID 0815 aufrufen. <br>

Als SOAP-Envelope sieht das ganze dann so aus: <br>

```xml
<?xml version="1.0"?>
<soap:Envelope
xmlns:soap="http://www.w3.org/2001/12/soap-envelope"
soap:encodingStyle="http://www.w3.org/2001/12/soap-encoding">
 <soap:body pb="http://ifgi.uni-muenster.de/phonebook">
  <pb:GetUserInfo>
   <pb:UserID>0815</pb:UserID>
  </pb:GetUserInfo>
 </soap:Body>
</soap:Envelope>
```

Ist unsere Anwendung hingegen nun RESTful reicht uns diese kurze URL, die wir als HTTP-GET-Request senden, um die gleiche Ressource anzufragen: <br>

	http://ifgi.uni-muenster.de/phonebook/UserInfo/0815

### Sind jetzt alle Anwendungen RESTful oder gibt es noch andere? ###

Sehr viele SOAP-Anwendungen
Einige XML-RPCs

### Weitere HTTP-Request-Methoden? ###

Ja, folgende Methoden werden auch noch genutzt:


| Request-Methode | Funktion |
| --------------- | -------- |
|      HEAD       | Anfrage nach Server-Header wie bei GET aber ohne den Body zu schicken |
|     TRACE       | Anfrage die an den Server gestellt wurde wird unverändert zurückgegeben (zu Troubleshoot-Zwecken) |
|    OPTIONS      | Liefert eine Liste der vom Server unterstützten Mathoden und Features |
|    CONNECT      | Wird bei Proxyservern zum Aufbau von SSL-Tunneln zur Verfügung gestellt |

[Quelle](http://de.wikipedia.org/wiki/Representational_State_Transfer#Umsetzung "Quelle")

## JSON ##

[[Quellen]](#json-quellen)

### Was ist JSON? [[Q4/Q5]](#json-quellen)###
**JSON** steht für: **J** ava **S** cript **O** bject **N** otation [[Q4]](#json-quellen) <br>

Es handelt sich um ein Datenaustauschformat, welches einen
Datenaustausch zwischen Anwendungen ermöglicht. <br>

**Ursprung:** Douglas Crockford (JavaScript); spezifizierte JSON-Standards [[Q6]](#json-quellen)<br>

- Unabhängig von der Programmiersprache

**Einsatzgebiete:**

- Datenübertragung zwischen Client und Server
- Ersatz für XML, um Ressourcen einzusparen
        
### Datenstruktur [[Q4/Q5]](#json-quellen)###
Als Zeichenkodierung verwendet JSON Standardmäßig UTF-8 (es sind aber auch UTF-16 und UTF-32 möglich).<br>

**Folgende Datentypen werden von JSON unterstützt:** <br>

- **Nullwert** (durch Schlüsselwort *null* dargestellt)
- **Boolescher Wert** (durch Schlüsselwörter *true* und *false* dargestellt)
- **Zahl** (Folge von Ziffern *0-9* die Vorzeichen *-* haben kann, Dezimalpunkt besitze und ein Exponentenzeichen *e* oder *E*  haben kann (mit *-* oder *+* Vorzeichen))
- **Zeichenkette** (beginnt und endet mit *"* und enthält Unicodezeichen)
- **Array** (Geordnete Liste von Werten gleichen oder unterschiedlichen Datentyps - Anfang durch *[* und Ende durch *]* markiert)
- **Objekt** (Ungeordnete Liste von Eigenschaften - Beginn der Liste mit *{* und Ende mit *}* markiert - Objekte ohne Eigenschaft sind zulässig 
  - Eigenschaft besteht aus Schlüssel und Eigenschaftswert in der Form *{Schlüssel:Wert}*
  - Schlüssel als Zeichenkette
  - Wert mit beliebigen Datentyp
    
### Beispiel und Unterschied zum XML ###

#### Ein JSON-Objekt der Stadt San Francisco kann zum Beispiel so aussehen: ####
```json
{
 "precision": "zip",
 "Latitude":  37.7668,
 "Longitude": -122.3959,
 "Address":   "",
 "City":  {
   "Name" : "San Francisco",
   "Sightseeing" : ["Golden Gate Bridge", "Pier 39", "Cable Cars", "Musem of Modern Art"],
   "State": "CA",
   "Zip":   "94107",
   "Country":   "US"
 }
```

#### Zum Vergelich das selbe Objekt in XML-Repräsentation: ####
```xml
<Location
   Latitude="37.7668"
   Longitude="-122.3959"
   Address=""
   precision="zip">
   <City 
 Name="San Francisco"
 State="CA"
 Zip="94107"
 Country="US"
   >
 <Sightseeing>
   <Sight>"Golden Gate Bridge"</Sight>
   <Sight>"Pier 39"</Sight>
   <Sight>"Cable Cars"</Sight>
   <Sight>"Museum of Modern Art"</Sight>
 </Sightseeing>
</Location>
```
Wie man schnell erkennt ist JSON nicht nur übersichtlicher, sondern hat auch einen geringeren Speicherbedarf,
was besonders in Umgebungen mit begrenzten Ressourcen (z.B. Embedded-Systeme) vom Vorteil ist. Sehr praktisch für Webanwendungen ist auch, dass JSON-Objekte valides JavaScript sind, was somit die Verwendung der übertragenen Daten in einer JavaScript-Anwendung vereifacht.<br>

Die Nachteile von JSON sind das es keinen eigenen Datentyp für ein Datum besitzt und das es keine Kommentare besitzt. <br>

Es gibt zur Zeit der Dokumenterstellung Parser für JSON in den meisten beliebten Programmiersprachen.
Eine Liste der verfügbaren Parser findet sich auf [JSON.org](http://json.org "JSON.org")

    
Hier ein Beispiel einer Methode in JavaScript, um JSON-Dokumete zu parsen:

```javascript
JSON.parse()
```

### JSON Schema [[Q7]](#json-quellen)###
Ein (eigenes) JSON Schema beschreibt ein (eigenes) Datenformat. <br>

Der grundlegende Aufbau ist durch ```JSON Schema Core``` definiert. (Siehe [hier](http://json-schema.org/latest/json-schema-core.html "hier")) <br>

```JSON Schema Validation``` definiert zudem die gültigen Schlüsselwörter eines JSON Schema. (Siehe [hier](http://json-schema.org/latest/json-schema-validation.html "hier")): <br> 

Beispiel:
```json
{
    "$schema": "http://json-schema.org/draft-04/schema#",
    "title": "Product",
    "description": "A product from Acme's catalog",
    "type": "object",
    "properties": {
        "id": {
            "description": "The unique identifier for a product",
            "type": "integer"
        },
        "name": {
            "description": "Name of the product",
            "type": "string"
        },
        "price": {
            "type": "number",
            "minimum": 0,
            "exclusiveMinimum": true
        }
    },
    "required": ["id", "name", "price"]
}
```

- In diesem Beispiel befinden sich sechs ```Keywords```: $schema, title, description (drei mal), type (vier mal), properties und required.
- required beschreibt, welche Eigenschaften eines JSON-Objektes des JSON Schema nicht null/leer sein dürfen
- $schema legt in diesem Falle fest, dass das Schema gemäß der draft v4 Spezifikation entworfen ist 
- Weitere Erklärungen zu dem Beispiel findet man [hier](http://json-schema.org/example1.html).

### GeoJSON [[Q8]](#json-quellen)###

GeoJSON ist ein ```GIS-Datenformat``` (in JSON) und ein offener Standard. <br>
Im Grunde ist es ein JSON Schema, entworfen als offenes Format. <br>

Unterstützt werden folgende geometrischen Typen:

- Point
- LineString
- Polygon
- MultiPoint
- MultiLinestring
- MultiPolygon

Listen von diesen Typen heißen ```GeometryCollection```. <br>
Typen mit weiteren Eigenschaften werden ```Features``` genannt. <br>
Und eine Liste aus Features ist eine ```FeatureCollection```. <br>

Hier mal ein Beispiel für eine sog. FeatureCollection:

```json
{ "type": "FeatureCollection",
    "features": [
      { "type": "Feature",
        "geometry": {"type": "Point", "coordinates": [102.0, 0.5]},
        "properties": {"prop0": "value0"}
        },
      { "type": "Feature",
        "geometry": {
          "type": "LineString",
          "coordinates": [
            [102.0, 0.0], [103.0, 1.0], [104.0, 0.0], [105.0, 1.0]
            ]
          },
        "properties": {
          "prop0": "value0",
          "prop1": 0.0
          }
        },
      { "type": "Feature",
         "geometry": {
           "type": "Polygon",
           "coordinates": [
             [ [100.0, 0.0], [101.0, 0.0], [101.0, 1.0],
               [100.0, 1.0], [100.0, 0.0] ]
             ]
         },
         "properties": {
           "prop0": "value0",
           "prop1": {"this": "that"}
           }
         }
       ]
     }
```

Die komplette Spezifikation mit Erklärungen u.a. zu den geometrischen Typen findet man bei geojson.org [hier](http://geojson.org/geojson-spec.html). <br>

Wichtig zu erwähnen ist aber, dass das CRS eines GeoJSON standardmäßig WGS84  (wie im Beispiel auch zu sehen) verwendet.

Ein nettes Tool zum ausprobieren eines GeoJSON findet man unter [geojson.io](http://geojson.io/#map=7/0.511/102.497). Fügt man dort das obige Beispiel ein, sieht zum einen den Point, den LineString und das Polygon. Außerdem kann man selber Geometrien erstellen und bekommt dazu das passende Geo JSON ausgegeben.

            
## OAuth ##

[[Quellen]](#oauth-quellen)

### Was ist OAuth?  [[Q9]](#oauth-quellen)###
OAuth steht für **O** pen **Auth** entication <br>
Es handelt sich um ein Protokoll, das standardisierte API-Autorisierung für Desktop-, Web und Mobil-Applications erlaubt. <br>
Ziel: Übermittlung von Authorisierungsdaten an Dritte vermeiden.

### Begriffe [[Q9]](#oauth-quellen)###

- **Service Provider:** <br>
  Damit ist eine Webseite oder ein Dienst gemeint, bei dem die Informationen liegen
- **User:** <br>
  Der Eigentümer der Information
- **Consumer:** <br>
  Eine Webseite/Anwendung, die auf die Informationen zugreifen möchte
- **Protected Resources:** <br>
  Die Informationen des Users die durch OAuth geschützt werden
- **Token:** <br>
  Authentifikations-Token ersetzen die Authorisierungsdaten und geben Zugang entweder für Abfragen oder Zugang zu bestimmten Bereichen (Es handelt sich um eine Kryptografisch erzeugte lange Zeichenfolge, die schwer zu erraten ist)

### Ablauf [[Q10]](#oauth-quellen)###

Diese 6 Schritte stellen eine abstrakte Beschreibung des Ablauf einer API-Autorisierung durch OAuth dar:

- **Schritt 1:**
  - User erlaubt Consumer Zugriff auf seine Daten
- **Schritt 2:**
  - Consumer erhält Genehmigung vom Provider
  - erhält ein (Abfrage-)Token
- **Schritt 3:**
  - User wird vom Consumer an Provider geleitetet
  - User bekommt Token mit
- **Schritt 4:**
  - User autorisiert das Token beim Provider
- **Schritt 5:**
  - Consumer erhält vom Provider (Zugangs-)Token
- **Schritt 6:**
  - Consumer kann auf Daten des User zugreifen


### Sicherheit [[Q9]](#oauth-quellen)###

In der aktuellen Version OAuth 2.0 ist das Protokoll erheblich komplexer geworden, was aber bis heute zu Diskussionen führt. Hier die markantesten Sicherheitsfeatures des Protokolls:

- OAuth 2.0 (angeblich) sicherer als 1.0
- Token mit Güligkeitsdauer
- Verwendung von SSL zur Verschlüsselung

> Zitat Eran Hammer (ehemaliger Redakteur des Spezifikationsdokuments von OAuth 2.0): OAuth 2.0 sei "... vor allem weniger sicher" als 1.0, da die Komplexität des Protokolls viele Möglichkeiten für Sicherheitsprobleme bei der Implementierung birgt.
Er erklärte OAuth für gescheitert und zog sich deshalb  vom Projekt zurück.  [[Q12]](#oauth-quellen)

    
### OAuth 2.0 Playground ###

Im "OAuth 2.0 Playground" von Google kann man eine OAuth 2.0 Authentifikation anschaulich, in einzelnen Schritten  selbst ausprobieren. Man findet dieses
(Entwickler-) Tool unter -> [OAuth 2.0 Playground](https://developers.google.com/oauthplayground/ "OAuth 2.0 Playground von Google")

### OAuth-Bibliotheken für eigene Projekte ###
Eine Liste mit Server- und Client-Frameworks, um OAuth in eigene Projekte zu integrieren, findet man unter [http://oauth.net/2/](http://oauth.net/2/ "oauth.net/2/").

### Tutorial für OAuth ###

Mit den hier aufgeführten Tutorial für JavaScript und HTML5 könnt ihr OAuth selber in einem Programmierprojekt ausprobieren: [How to Implement Safe Sign-In via OAuth](http://devcenter.kinvey.com/html5/tutorials/how-to-implement-safe-signin-via-oauth# "How to Implement Safe Sign-In via OAuth").

    
## Quellen ##

### RESTful-Webservices-Quellen ###

[Q1 - Restful Webservices - was ist das überhaubt](https://blog.mittwald.de/webentwicklung/restful-webservices-1-was-ist-das-uberhaupt/ "RESTful") <br>
[Q2 - RFC 6749 (REST)](http://tools.ietf.org/html/rfc6749 "REST RFC bei der IETF") <br>
[Q3 - Fielding - Dissertation - Chapter 5](http://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm "Disertation about REST by Fielding") <br>
        
### JSON-Quellen ###

[Q4 - JSON-Projekt Homepage](http://json.org/ "JSON Projekt-Homepage") <br>
[Q5 - RFC 4627 (JSON)](http://tools.ietf.org/html/rfc4627 "JSON RFC bei der IETF") <br>
[Q6 - Wikipedia-Seite über Douglas Crockford](http://en.wikipedia.org/wiki/Douglas_Crockford) <br>
[Q7 - JSON Schema](http://json-schema.org/) <br>
[Q8 - Geo JSON](http://geojson.org/) <br>


### OAuth-Quellen###
[Q9 - Beginners Guide to OAuth](http://hueniverse.com/2007/10/04/beginners-guide-to-oauth-part-i-overview/ "Beginners Guide to OAuth 1.0") <br>
[Q10 - Introduction to OAuth](http://blog.varonis.com/introduction-to-oauth/ ) <br>
[Q11 - Google OAuth 2.0 Playground](https://developers.google.com/oauthplayground/) <br>
[Q12 - Kritik von Eran Hammer an OAuth 2.0](http://hueniverse.com/2012/07/26/oauth-2-0-and-the-road-to-hell/ "OAuth 2.0 and the Road to Hell") <br>

    
