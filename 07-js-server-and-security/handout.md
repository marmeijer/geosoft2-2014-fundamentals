#Server-Side JS und JS Security
==============================
**Inhaltsverzeichnis:**                       

1. [Einführung](https://github.com/MilanMilanMilan/geosoft2-2014-fundamentals/edit/master/07-js-server-and-security/handout.md#einführung)
2. [Clientseitige und serverseitige Skriptsprachen](https://github.com/MilanMilanMilan/geosoft2-2014-fundamentals/edit/master/07-js-server-and-security/handout.md#clientseitige-und-serverseitige-skriptsprachen)              
3. [Vorteile von ServerSide JS im Vergleich zu anderen serverseitigen Sprachen](https://github.com/MilanMilanMilan/geosoft2-2014-fundamentals/edit/master/07-js-server-and-security/handout.md#vorteile-von-serverside-js-im-vergleich-zu-anderen-serverseitigen-sprachen)            
4. [NodeJS](https://github.com/MilanMilanMilan/geosoft2-2014-fundamentals/edit/master/07-js-server-and-security/handout.md#nodejs)             
5. [JS Sicherheit](https://github.com/MilanMilanMilan/geosoft2-2014-fundamentals/edit/master/07-js-server-and-security/handout.md#js-sicherheit)             
6. [Same-origin-policy](https://github.com/MilanMilanMilan/geosoft2-2014-fundamentals/edit/master/07-js-server-and-security/handout.md#same-origin-policy)
7. [CORS or Cross Origin Resource Sharing ](https://github.com/MilanMilanMilan/geosoft2-2014-fundamentals/edit/master/07-js-server-and-security/handout.md#cors-or-cross-origin-resource-sharing)             

--------------------------
##Einführung
JavaScript ist nicht mehr wegzudenken in Zeiten von dynamischen Webseiten.   
Auch durch die neue Verwendung von serverseitigem JavaScript (z.B. mit Node.JS) werden neue Möglichkeiten eröffnet.
Trotzdem steht die Sicherheit dieser Scriptsprache immer wieder in der Kritik. Um vor unerwünschtem Zugriff zu schützen, wurden Konzepte wie die Same Origin Policy oder das Sandbox-Prinzip entwickelt. 
Das Handout soll einen Überblick über (serverseitiges) JavaScript und dessen Sicherheit geben und durch
weiterführende Links detailiert über das Thema informieren. 





##Clientseitige und serverseitige Skriptsprachen         

###Client-Side:

* Programmcode wird auf der Seite des Clients (im Webbrowser) ausgeführt.
* Clientseitige Skriptsprachen: 
JavaScript, ActionScript, Dart, Typescript	  
**positiv:**   
• Clientseitige Skriptsprachen sind ein wesentlicher Bestandteil von Dynamic HTML. Die ermöglichen es, interaktive Webseiten zu erstellen, die sofort auf einen Input vom Benutzer reagieren.  
• Schnell, da keine Interaktion mit dem Server.  
**negativ:**  
• Scripts abhängig von Webbrowser ausgeführt: Inhalte können unterschiedlich dargestellt werden.  
• Unsicher, weil:  
  - Source Code für alle sichtbar
  - Zustandsspeicherung via cookies

###Server-Side:

* Programmcode wird auf dem Webserver ausgeführt.
* Serverseitige Skriptsprachen: PHP, ASP.NET, Perl, Python, Server-Side JS.  
**positiv:**  
•	Sicherer, weil Sourcecode nicht sichtbar  
•	Ermöglicht Zugriff auf eine Datenbank,  ein Dateisystem  
•	Ermöglicht es, große Mengen von Daten auszutauschen  
**negativ:**  
• Langsamer  


##Vorteile von ServerSide JS im Vergleich zu anderen serverseitigen Sprachen 
●	ermöglicht das Verwenden von gemeinsamen Code auf Server und Client   
●	schnellere und performantere Ausführung  
●	(weniger Arbeitsspeicher-Nutzung)  

[Hier kann man Laufzeit verschiedener Skriptsprachen vergleichen](http://benchmarksgame.alioth.debian.org/)

##NodeJS  
●	Basiert auf Javascript-Umgebung „[V8](https://developers.google.com/v8/intro)“ von Google  
●	serverseitige Plattform zum Betrieb von Netzwerkanwendungen   
●	ressourcenschonend, da nicht Thread-, sondern Event-Basiert  
●	[asynchrones I/O](http://t3n.de/magazin/serverseitige-javascript-entwicklung-nodejs-einsatz-231152/3/) (wird ausgelagert und blockiert nicht)  
●	weitere Vorteile: einheitliche Entwicklungssprache, plattformunabhängige Software, durch Module erweiterbar,  
für Cloud Dienste geeignet

![Node.JS](http://dev-ops.net/wp-content/uploads/2014/07/threading_node.png)  
 
Bei Node.JS gibt es nur einen Thread, der Anfragen annimmt und sie direkt weitergibt. Er ist also im Gegensatz zu den mehreren Threads bei „normalen“ Webservern nie blockiert oder muss warten. Grund dafür ist auch das asynchrone Input/Output, welches zeitlich versetzt stattfindet, um Prozesse nicht zu blockieren.  

**Fazit:** Node.JS ist für einige Szenarien mehr, für andere weniger geeignet. Gut geeignet ist es für moderne Webanwendungen, wie zum Beispiel JSON-basierte REST-Dienste. Es kann jedoch bei sehr rechenintensiven Anwendungen auch Schwächen zeigen.

###Node.js Tutorials:            
1. [nodecode.de](http://nodecode.de)      
2. [Video-Tutorial](http://nodetuts.com)        
3. [blog.rapsli.ch](http://blog.rapsli.ch/posts/2013/2013-04-22-anfangerwissen-fur-node-js.html/)         
4. [nodeguide.com](http://nodeguide.com/beginner.html)
5. [nodeschool](http://nodeschool.io)

[Node.js Module mit Geobezug](https://nodejsmodules.org/tags/geos)

##JS Sicherheit
●	JS kann Sicherheitslücken hervorrufen  
●	 durch zu freizügige oder nicht funktionierende Sicherheitsmechanismen  
●	 Sandbox-Prinzip als Lösung:  strenger Rahmen für Script (nur Zugriff auf Browserfenster und Dokument, nicht Dateisystem)
  - Website/ -anwendung wird in Browser isoliert ausgeführt, um Datenaustausch zu unterbinden   
  - kann keine Daten lesen oder schreiben  
  - schützt vor z.B. [Cross-Site-Scripting](http://de.wikipedia.org/wiki/Cross-Site-Scripting) (Informationen aus nicht vertrauenswürdigen Kontext werden in anderen eingefügt, um als vertrauenswürdig eingestuft zu werden (Ziel: sensible Benutzerdaten in parallel geöffnetem Browserfenster auslesen/manipulieren))  

●  Es besteht die Gefahr, dass beim Login mit (clientseitigem) JavaScript Daten mithilfe von z.B. Cross-Site-Scripting ausgelesen oder manipuliert werden. Als Schutz können hierbei unerwünschte bzw. erwünschte Eingaben definiert und auf Listen gesetzt werden, welche serverseitig geprüft werden, um nur die gwollten zuzulassen  
●  Passwörter können durch beispielsweise eine [MD5-Hashfunktion](http://aktuell.de.selfhtml.org/artikel/javascript/md5/) verschlüsselt werden, um nicht als Klartext übertragen zu werden, oder die Übertragung selbst kann mit `https` verschlüsselt werden.
●	 Auch möglich: JavaScript deaktivieren   

[Demo](http://www.heise.de/security/artikel/Passwortklau-fuer-Dummies-270910.html#) zum Thema Cross-Site-Scripting  

##Same Origin Policy
ein Sicherheitskonzept, das clientseitigen Skriptsprachen aber auch Cascading Style Sheets untersagt, auf Objekte zuzugreifen, die von einer anderen Webseite stammen oder deren Speicherort nicht der Origin entspricht.

Den Hintergrund für die große Bedeutung der SOP bildet im Wesentlichen die Kombination aus zwei Tatsachen:

* Skriptsprachen im Browser haben über das Document Object Model (DOM) direkten Zugriff auf die gesamte Kommunikation zwischen Browser und Web-Server. Dies beinhaltet sowohl das Auslesen als auch die Manipulation von Daten und betrifft neben dem Empfangen auch das Senden von Daten.
* Das Vertrauensverhältnis zwischen Browser (bzw. Anwender) und verschiedenen Webseiten kann extrem unterschiedlich sein.

Daraus ergibt sich die Anforderung, dass keine Informationen aus einem Kontext (zum Beispiel der Verbindung des Browsers zu der Seite einer Bank) von einem Skript aus einem anderen Kontext zugreifbar oder manipulierbar sein darf. Um dies zu erreichen, wird beim Zugriff eines Skriptes auf ein Objekt einer Webseite die Herkunft (origin) von beiden verglichen.

Beispiel:     
Ein in der Datei http://www.example.com/dir/page.html eingebettetes Skript versucht, auf ein Element in den folgenden Seiten zuzugreifen:      

Angesprochene URL                        | Ergebnis | Grund
---------------------------------------- | -------- | ----------------------------------------------
http://www.example.com/dir/page2.htm     | Ja       | selbes Protokoll und Host
http://www.example.com:81/dir/other.html | Nein     | selbes Protokoll und Host, aber anderer Port
https://www.example.com/dir/other.html   | Nein     | anderes Protokoll
http://en.example.com/dir/other.html     | Nein     | anderer Host

Die Grenzen der Same-Origin-Policy sind in zweierlei Hinsicht von Bedeutung:

* Die SOP ist als Sicherheitsmechanismus nicht ausreichend wirksam. Viele aktuelle Angriffsmethoden wie DNS Rebinding und Cross-Site Request Forgery zielen erfolgreich darauf ab, die SOP zu umgehen.
* Andererseits sind die von der SOP gezogenen Grenzen in vielen Fällen unerwünscht. Insbesondere mit dem Aufkommen von Ajax-basierenden Anwendungen und Mashups gibt es legitimerweise den Wunsch, die Grenzen der SOP zu überschreiten. Eine Möglichkeit bietet das Cross-Origin Resource Sharing, dies wird allerdings nicht von allen Webbrowsern unterstützt.

##CORS or Cross Origin Resource Sharing         
 ein Mechanismus,der benutzt wird um auf die Webseiten zuzugreifen, die nicht der Origin (Port/Domain) entsprechen. 
 
 Um das zu tun, muss der request einen Origin-HTTP-Header enthalten. Der Server muss dann den Zugriff durch entsprechende HTTP-Header erlauben.
 Beispiel: ein Script will von der Seite http://api.bob.com will auf einen Server der abweichenden Domain http://api.alice.com zugreifen. Um ein request zu schicken kann folgenden JavaScript code benutzt werden:

```javascript
  var url = 'http://api.alice.com/cors';
  var xhr = createCORSRequest('GET', url);
  xhr.send();
 
```
Der Origin-HTTP-Header wird dann automatisch vom Webbrowser hinzugefüt, so dass HTTP-Request folgendermaßen aussieht:

```
  GET /cors HTTP/1.1
  Origin: http://api.bob.com
  Host: api.alice.com
  Accept-Language: en-US
  Connection: keep-alive
  User-Agent: Mozilla/5.0...
```
Falls der Server den Zugriff erlaubt, schickt er einen response mit einem Access-Control-Allow-Origin-Header:

```
  Access-Control-Allow-Origin: http://api.bob.com
  Access-Control-Allow-Credentials: true
  Access-Control-Expose-Headers: FooBar
  Content-Type: text/html; charset=utf-8

```

Mehr zum Thema CORS:                         
1. http://www.nczonline.net/blog/2010/05/25/cross-domain-ajax-with-cross-origin-resource-sharing/                
2. http://www.html5rocks.com/en/tutorials/cors/?redirect_from_locale=de#toc-adding-cors-support-to-the-server               


###Quellen:

1.	www.wikipedia.org  
2.	http://nodecode.de/php-oder-nodejs  
3.	http://stackoverflow.com/  
4.	http://www.hongkiat.com/blog/node-js-server-side-javascript/  
5.	http://nodeguide.com/beginner.html  
6.	http://t3n.de/magazin/serverseitige-javascript-entwicklung-nodejs-einsatz-231152/  
7.	http://strongloop.com/strongblog/node-js-is-faster-than-java/ (Node.JS Graphik)  
8.	http://molily.de/js/sicherheit.html  
9.	http://www.nczonline.net/blog/2010/05/25/cross-domain-ajax-with-cross-origin-resource-sharing/
