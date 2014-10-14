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

### Sind jetzt alle Anwendungen RESTful oder gibt es noch andere ###

Sehr viele SOAP-Anwendungen
Einige XML-RPCs