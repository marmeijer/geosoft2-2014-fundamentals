#### *Geosoftware 2* ####
#### *Daniel Ummelmann, Michael Rieping* ####

# RESTful Web Services, JSON und OAuth #


## Gliederung: ##

1. RESTful Websevices
1. JSON
1. OAuth

## RESTful Webservices ##

### Was ist REST? ###
**REST** steht für: **RE**presentational **S**tate **T**ransfer <br>

Es handelt sich dabei um ein von Roy Fielding 1994 entworfenes Programmierparadigma für Webapplikationen, welches davon ausgeht, dass auf einen Aufruf einer **URI** (**U**niform **R**esource **I**dentifier) immer mit der gleichen Antwort geantwortet wird. <br>

Die Prinzipien nach dem REST funktioniert sind dabei:<br>

- Adressierbarkeit: Jede Ressource besitzt eine eindeutige Adresse (URI)
- Zustandslosigkeit: Jede REST-Nachricht enthält alle benötigten Informationen, somit muss keine offene Verbindung gehalten werden.
- Einheitliche Schnittstelle
- Entkopplung von Ressourcen und Repräsentation: Die gleiche Ressource kann in verschiedenen Repräsentationen dargestellt werden

### Was ist RESTful? ###
Unter RESTful versteht man die Umsetzung des REST-Paradigmas in einer Webanwendung. Dafür muss ein zustandsloses Client-/Server-Protokoll verwendet werden (meistens HTTP/HTTPS). Die wichtigsten (HTTP-)Operationen, die dabei verwendet werden sind dabei: <br>
    
- ```GET```
- ```POST```
- ```PUT```
- ```DELETE```

#### Beispiel: ####

In diesem Beispiel sehen wir uns eine Webanwendung an, die das Telefonbuch des IFGIs verwaltet und wir möchten mit einem Aufruf den Benutzer mit der UserID 0815 aufrufen. <br>

Als SOAP-Envelope sieht das ganze dann so aus: <br>

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

Ist unsere Anwendung hingegen nun RESTful reicht uns diese kurze URL, die wir als HTTP-GET-Request senden, um die gleiche Ressource anzufragen: <br>

	http://ifgi.uni-muenster.de/phonebook/UserInfo/0815
    
### Warum REST? ###
Da das bis dato vorherschende SOAP (**S**imple **O**bject **A**ccess **P**rotocol) paradoxerweise sehr kompliziert war, herrschte ein großes Verlangen nach Vereinfachung. <br>

*Tabelle 1: Stärken und Schwächen von SOAP:*

|                    Stärken                    |            Schwächen         |
| --------------------------------------------- | ---------------------------  |
|     große Mächtigkeit der SOAP-Envelopes      | komplizierte XML-Nachrichten |
| Programmiersprachen- und Plattform-unabhängig |         großer Overhead      |
|                        -                      |         rechenintensiv       |

    


## JSON ##

### Was ist JSON? ###
**JSON** steht für: **J**ava**S**cript **O**bject **N**otation <br>

Es handelt sich um ein Datenaustauschformat, welches einen
Datenaustausch zwischen Anwendungen ermöglicht. <br>

**Ursprung:** Douglas Crockford (JavaScript); spezifizierte JSON-Standards <br>

- Unabhängig von der Programmiersprache

**Einsatzgebiete:**

- Datenübertragung zwischen Client und Server
- Ersatz für XML, um Ressourcen einzusparen
        
### Datenstruktur ###
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

Die Nachteile von JSON sind das es auf der einen Seite (noch) wenig verbreitet ist und dadurch nicht so vielseitig einsetzbar ist, wie das XML-Format. <br>
    
Methoden in JavaScript, um JSON-Dokumete zu parsen (es gibt Parser in fast jeder Programmiersprache):

```javascript
JSON.parse()
JSON.stringify()
```
            
## OAuth ##

### Was ist OAuth? ###
OAuth steht für **O**pen **Auth**entication <br>
Es handelt sich um ein Protokoll, das standardisierte API-Autorisierung für Desktop-, Web und Mobil-Applications erlaubt. <br>
Ziel: Übermittlung von Authorisierungsdaten an Dritte vermeiden.

### Begriffe ###

- Service Provider: Damit ist eine Webseite oder ein Dienst gemeint, bei dem die Informationen liegen
- User: Der Eigentümer der Information
- Consumer: Eine Webseite/Anwendung, die auf die Informationen zugreifen möchte
- Protected Resources: Die Informationen des Users die durch OAuth geschützt werden
- Token: Authentifikations-Token ersetzen die Authorisierungsdaten und geben Zugang entweder für Abfragen oder Zugang zu bestimmten Bereichen (Es handelt sich um eine Kryptografisch erzeugte lange Zeichenfolge, die schwer zu erraten ist)

### Ablauf ###

- Schritt 1:
  - User erlaubt Consumer Zugriff auf seine Daten
- Schritt 2:
  - Consumer erhält Genehmigung vom Provider
  - erhält ein (Abfrage-)Token
- Schritt 3:
  - User wird vom Consumer an Provider geleitetet
  - User bekommt Token mit
- Schritt 4:
  - User autorisiert das Token beim Provider
- Schritt 5:
  - Consumer erhält vom Provider (Zugangs-)Token
- Schritt 6:
  - Consumer kann auf Daten des User zugreifen


### Sicherheit ###

Ind er aktuellen Version OAuth 2.0 ist das Protokoll erheblich komplexer geworden, was aber bis heute zu Diskussionen führt. Hier die markantesten Sicherheitsfeatures des Protokolls:

- OAuth 2.0 (angeblich) sicherer als 1.0
- Token mit Güligkeitsdauer
- Verwendung von SSL zur Verschlüsselung

> Zitat Eran Hammer (ehemaliger Redakteur des Spezifikationsdokuments von OAuth 2.0): OAuth 2.0 sei "... vor allem weniger sicher" als 1.0
    
### OAuth 2.0 Playground ###

Im "OAuth 2.0 Playground" von Google kann man eine OAuth 2.0 Authentifikation anschaulich, in einzelnen Schritten  selbst ausprobieren. Man findet das
Tool hier -> [OAuth 2.0 Playground](https://developers.google.com/oauthplayground/ "OAuth 2.0 Playground von Google")


    
## Quellen ##

### RESTful Web Services ###

[RFC 6749 (REST)](http://tools.ietf.org/html/rfc6749 "REST RFC bei der IETF") <br>
[Restful Webservices - was ist das überhaubt](https://blog.mittwald.de/webentwicklung/restful-webservices-1-was-ist-das-uberhaupt/ "RESTful") <br>
[Fielding - Dissertation - Chapter 5](http://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm "Disertation about REST by Fielding")
        
### JSON ###

[JSON-Projekt Homepage](http://json.org/ "JSON Projekt-Homepage") <br>
[RFC 4627 (JSON)](http://tools.ietf.org/html/rfc4627 "JSON RFC bei der IETF") <br>
[Wikipedia-Seite über Douglas Crockford](http://en.wikipedia.org/wiki/Douglas_Crockford)

### OAuth ###
[Kritik von Eran Hammer an OAuth 2.0](http://hueniverse.com/2012/07/26/oauth-2-0-and-the-road-to-hell/ "OAuth 2.0 and the Road to Hell") <br>
[Introduction to OAuth](http://blog.varonis.com/introduction-to-oauth/ ) <br>
[Beginners Guide to OAuth](http://hueniverse.com/2007/10/04/beginners-guide-to-oauth-part-i-overview/ "Beginners Guide to OAuth 1.0")
[Google OAuth 2.0 Playground](https://developers.google.com/oauthplayground/)

    
