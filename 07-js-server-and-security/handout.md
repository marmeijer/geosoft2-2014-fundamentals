Server-Side JS und JS Security
==============================
Node.JS, Same-origin policy
--------------------------
Client-Side vs. Server-Side Scripting

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
 




**Quellen:**  
1.	www.wikipedia.org    
2.	http://nodecode.de/php-oder-nodejs  
3.	http://stackoverflow.com/  
4.	http://www.hongkiat.com/blog/node-js-server-side-javascript/  
5.	http://nodeguide.com/beginner.html  
6.	http://t3n.de/magazin/serverseitige-javascript-entwicklung-nodejs-einsatz-231152/  
7.	http://strongloop.com/strongblog/node-js-is-faster-than-java/ (Node.JS Graphik)  
8.	http://molily.de/js/sicherheit.html  
