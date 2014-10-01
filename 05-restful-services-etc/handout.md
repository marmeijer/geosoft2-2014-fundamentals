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

Es handelt sich dabei um ein von Roy Fielding 1994 entworfenes Programmierparadigma für Webapplikationen, welches davon ausgeht, dass auf einen Aufruf einer **URI** (**U**niform **R**esource **I**dentifier) mit der gleichen Antwort geantwortet wird. 
        REST-Architektur
            Kernpunkt
                Ressourcen
                    Anforderungen
                        Adressierbarkeit
                        Zustandslosigkeit
                        Einheitliche Schnittstelle
                        Entkopplung von Ressourcen und Repräsentation
### Was ist RESTful? ###
            Umsetzung der REST-Architektur
    
    REST und HTTP
        Wichtigste (HTTP-)Operationen
            GET
            POST
            PUT
            DELETE
        Beispiel
    
### Warum REST? ###
Da das bis dato vorherschende SOAP (Simple Object Access Protocol) sehr kompliziert war, herrschte ein großes Verlangen nach Vereinfachung. <br> 
*Tabelle der Stärken und Schwächen von SOAP:*
<table>
    <tr>
        <th>Stärken</th>
		<th>Schwächen</th>
    </tr>
	<tr>
		<td>Programmiersprachen- und Plattform-unabhängig</td>
		<td>komplizierte XML-Nachrichten</td>
	</tr>
	<tr>
		<td></td>
		<td>großer Overhead</td>
	</tr>
	<tr>
		<td></td>
		<td>rechenintensiv</td>
	</tr>
</table>
    


## JSON ##

### Was ist JSON? ###
**JSON** steht für: **J**ava**S**cript **O**bject **N**otation <br>
Es handelt sich um ein Datenaustauschformat, welches einen
Datenaustausch zwischen Anwendungen ermöglicht. <br>
        Ursprung
            Douglas Crockford (JavaScript); spezifizierte JSON-Standards
        Unabhängig von der Programmiersprache
        Einsatzgebiete
            Datenübertragung zwischen Client und Server
            Ersatz für XML, um Ressourcen einzusparen
        
### Datenstruktur ###
        Zeichenkodierung
            Standardmäßig UTF-8
        Verschachtelung
        Datentypen
            Nullwert
            Boolescher Wert
            Zahl
            Zeichenkette
            Array
                Elemente gleichen oder unterschiedlichen Datentyps
            Objekt
                Eigenschaft/Attribut
                    Schlüssel als Zeichenkette
                    Wert mit beliebigen Datentyp
    
### Beispiel und Unterschied zum XML ###
Beispiel
 Unteschiede zu XML
 Geringerer Speicherbedarf
 Einfachere Lesbarkeit
 Valides JavaScript
 Weniger vielseitig einsetzbar
 Weniger verbreitet
    
Methoden in JavaScript:

    JSON.parse()
    JSON.stringify()

            
## OAuth ##

### Was ist OAuth? ###
Protokoll, das standardisierte API-Autorisierung für Desktop-, Web und Mobil-Applications erlaubt. <br>
Ziel: Übermittlung von Passwörtern an Dritte vermeiden

### Sicherheit ###
- OAuth 2.0 (angeblich) sicherer als 1.0
- Token mit Güligkeitsdauer
- SSL
> Zitat Eran Hammer: OAuth 2.0 sei "... vor allem weniger sicher" als 1.0
    
### OAuth 2.0 Playground ###
Tool [OAuth 2.0 Playground](https://developers.google.com/oauthplayground/ "OAuth 2.0 Playground")
            Einzelne Schritte der OAuth 2.0 - Authentifizierung zu durchlaufen

    
## Quellen ##

### RESTful Web Services ###

[RFC 6749](http://tools.ietf.org/html/rfc6749 "RFC 6749") <br>
[Restful Webservices - was ist das überhaubt](https://blog.mittwald.de/webentwicklung/restful-webservices-1-was-ist-das-uberhaupt/ "RESTful") <br>
[Fielding - Dissertation - Chapter 5](http://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm "Disertation about REST by Fielding")
        
### JSON ###
http://wiki.selfhtml.org/wiki/JavaScript/JSON
http://de.wikipedia.org/wiki/JavaScript_Object_Notation
http://en.wikipedia.org/wiki/Douglas_Crockford

### OAuth ###
http://hueniverse.com/2012/07/26/oauth-2-0-and-the-road-to-hell/
http://blog.varonis.com/introduction-to-oauth/ <br>
http://de.wikipedia.org/wiki/OAuth <br>
http://www.admin-magazin.de/News/Google-oeffnet-Spielwiese-fuer-OAuth-2.0 <br>
https://developers.google.com/oauthplayground/

    
