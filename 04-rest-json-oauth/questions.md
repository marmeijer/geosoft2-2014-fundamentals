# Fragen #
## Fragen zu REST ##
### Warum REST? ###
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

### Gibt es noch weitere HTTP-Request-Methoden? ###

Ja, folgende Methoden werden auch noch genutzt:

| Request-Methode | Funktion |
| --------------- | -------- |
|      HEAD       | Anfrage nach Server-Header wie bei GET aber ohne den Body zu schicken |
|     TRACE       | Anfrage die an den Server gestellt wurde wird unverändert zurückgegeben (zu Troubleshoot-Zwecken) |
|    OPTIONS      | Liefert eine Liste der vom Server unterstützten Mathoden und Features |
|    CONNECT      | Wird bei Proxyservern zum Aufbau von SSL-Tunneln zur Verfügung gestellt |

## Fragen zu JSON ##

### Gibt es noch weitere Parser für JSON ###

Ja, man findet eine vollständige Liste auf der Haupt-Projekt-Webseite von JSON

## Fragen zu OAuth ##

### Wie sicher ist OAuth? ###



- OAuth 2.0 (angeblich) sicherer als 1.0:
  - Token mit Gültigkeitsdauer
  - Verwendung von SSL
- Laut Eran Hammer (ehem. Entwickler für 2.0): OAuth 2.0 “ … vor allem weniger sicher” als 1.0, da die Komplexität des Protokolls viele Möglichkeiten für Sicherheitsprobleme bei der Implementierung birgt.
Er erklärte OAuth für gescheitert und zog sich deshalb  vom Projekt zurück. 