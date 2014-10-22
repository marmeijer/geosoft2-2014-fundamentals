Server-Side JS und JS Security
==============================
**Inhaltsverzeichnis:**                       

1. Clientseitige und serverseitige Skriptsprachen              
2. Vorteile von Server-Side JS im Vergleich zu anderen serverseitigen Sprachen              
3. Node.js             
4. JS Sicherheit              
5. Same-origin-policy, CORS                

--------------------------
**Clientseitige und serverseitige Skriptsprachen**            

Client-Side:

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

Server-Side:

* Programmcode wird auf dem Webserver ausgeführt.
* Serverseitige Skriptsprachen: PHP, ASP.NET, Perl, Python, Server-Side JS.  
**positiv:**  
•	Sicherer, weil Sourcecode nicht sichtbar  
•	Ermöglicht Zugriff auf eine Datenbank,  ein Dateisystem  
•	Ermöglicht es, große Mengen von Daten auszutauschen  
**negativ:**  
• Langsamer  


**Vorteile von  Server-Side JS**  
●	ermöglicht das Verwenden von gemeinsamen Code auf Server und Client   
●	schnellere und performantere Ausführung  
●	weniger Arbeitsspeicher-Nutzung   

**Node.js**  
●	Basiert auf Javascript-Umgebung „V8“ von Google  
●	serverseitige Plattform zum Betrieb von Netzwerkanwendungen   
●	ressourcenschonend, da nicht Thread-, sondern Event-Basiert  
●	asynchrones I/O  

![Node.JS](http://dev-ops.net/wp-content/uploads/2014/07/threading_node.png)  
 
Bei Node.JS gibt es nur einen Thread, der Anfragen annimmt und sie direkt weitergibt. Er ist also im Gegensatz zu den mehreren Threads bei „normalen“ Webservern nie blockiert oder muss warten. Grund dafür ist auch das asynchrone Input/Output, welches zeitlich versetzt stattfindet, um Prozesse nicht zu blockieren. 

**JS-Sicherheit**  
●	JS kann Sicherheitslücken hervorrufen  
●	 durch zu freizügige oder nicht funktionierende Sicherheitsmechanismen  
●	 Sandbox-Prinzip als Lösung:  strenger Rahmen für Script (nur Zugriff auf Browserfenster und Dokument, nicht Dateisystem)  
  - Website/ -anwendung wird in Browser isoliert ausgeführt, um Datenaustausch zu unterbinden   
  - kann keine Daten lesen oder schreiben  
  - schützt vor z.B. Cross-Site-Scripting (Informationen aus nicht vertrauenswürdigen Kontext werden in anderen eingefügt, um als vertrauenswürdig eingestuft zu werden (Ziel: sensible Benutzerdaten in parallel geöffnetem Browserfenster auslesen/manipulieren))  

●	 Auch möglich: JavaScript deaktivieren   

**Same-Origin Policy**  
ein Sicherheitskonzept, das clientseitigen Skriptsprachen aber auch Cascading Style Sheets untersagt, auf Objekte zuzugreifen, die von einer anderen Webseite stammen oder deren Speicherort nicht der Origin entspricht.

Den Hintergrund für die große Bedeutung der SOP bildet im Wesentlichen die Kombination aus zwei Tatsachen:

* Skriptsprachen im Browser haben über das Document Object Model (DOM) direkten Zugriff auf die gesamte Kommunikation zwischen Browser und Web-Server. Dies beinhaltet sowohl das Auslesen als auch die Manipulation von Daten und betrifft neben dem Empfangen auch das Senden von Daten.
* Das Vertrauensverhältnis zwischen Browser (bzw. Anwender) und verschiedenen Webseiten kann extrem unterschiedlich sein.

Daraus ergibt sich die Anforderung, dass keine Informationen aus einem Kontext (zum Beispiel der Verbindung des Browsers zu der Seite einer Bank) von einem Skript aus einem anderen Kontext zugreifbar oder manipulierbar sein darf. Um dies zu erreichen, wird beim Zugriff eines Skriptes auf ein Objekt einer Webseite die Herkunft (origin) von beiden verglichen.

Die Grenzen der Same-Origin-Policy sind in zweierlei Hinsicht von Bedeutung:

* Die SOP ist als Sicherheitsmechanismus nicht ausreichend wirksam. Viele aktuelle Angriffsmethoden wie DNS Rebinding und Cross-Site Request Forgery zielen erfolgreich darauf ab, die SOP zu umgehen.
* Andererseits sind die von der SOP gezogenen Grenzen in vielen Fällen unerwünscht. Insbesondere mit dem Aufkommen von Ajax-basierenden Anwendungen und Mashups gibt es legitimerweise den Wunsch, die Grenzen der SOP zu überschreiten. Eine Möglichkeit bietet das Cross-Origin Resource Sharing, dies wird allerdings nicht von allen Webbrowsern unterstützt.

**CORS: Cross-Origin Resource Sharing**              
 ein Mechanismus,der benutzt wird um auf die Webseiten zuzugreifen, die nicht dem Origin (Port/Domain) entsprechen. 
 
 Um das zu tun, muss ein request ein Origin-HTTP-Header enthalten. Der Server muss dann den Zugriff durch entsprechende HTTP-Header erlauben.
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


**Quellen:**  
1.	www.wikipedia.org    
2.	http://nodecode.de/php-oder-nodejs  
3.	http://stackoverflow.com/  
4.	http://www.hongkiat.com/blog/node-js-server-side-javascript/  
5.	http://nodeguide.com/beginner.html  
6.	http://t3n.de/magazin/serverseitige-javascript-entwicklung-nodejs-einsatz-231152/  
7.	http://strongloop.com/strongblog/node-js-is-faster-than-java/ (Node.JS Graphik)  
8.	http://molily.de/js/sicherheit.html  
9.	http://www.nczonline.net/blog/2010/05/25/cross-domain-ajax-with-cross-origin-resource-sharing/
