#WebSockets und HTML5#
##HTML5##
HTML5 ist:

* ...eine textbasierte Auszeichnungssprache zur Strukturierung und semantischen Auszeichnungen von Inhalten wie Texten, Bildern und Hyperlinks in Dokumenten.
* ...der Nachfolger von HTML4, unterstützt dieses aber.
* ...am 16.09.2014 als künftige HTML5 Empfehlung von W3C veröffentlicht worden.

[weitere allgemeine Infos](http://www.w3.org/TR/html5/ "weiter allgemeine Infos")


####Veränderungen zu HTML4####
####Aufbau eines HTML5 Dokumentes####

* als Erstes die Doctypedeklaration:

		<!DOCTYPE html>
		<html>

* dann der Kopf, in diesen gehört der Titel, die encoding declaration,...

		<head>
  		<title>Styling HTML5</title>
		<meta charset="utf-8">

* ... das Styling
	* In HTML5 kann der Style eines Dokumentes im Header durch ein Stylesheet festgelegt werden. Somit ist dieser ganz leicht veränderbar. Mit der Programmiersprache CSS3 kann für jedes Element im HTMLDoc ein Style festgelegt werden.
	* Mehr Infos zu [CSS](http://www.w3schools.com/css/default.asp) und [CSS3](http://www.w3schools.com/css/css3_intro.asp)
	* Beispiel:
			
			/*im <head>*/
			<link rel="stylesheet" href="style.css" type="text/css" media="screen" />

			/* CSS-Datei style.css */
			header {background-color: yellow;}
			nav {background-color: orange;}
			section {background-color: yellowgreen;}
			footer {background-color: deepskyblue;}

* ... und damit auch die neuen Style Elemente von HTML5 bei alten Browser funktionieren gibt es "the shiv" (HTML5 Enabling JavaScript). Ohne diesen Kommentar werden von alten Browsern unbekannte Elemente einfach als "inline elements" angezeigt.


  		<!--[if lt IE 9]>
  		<script src="http://html5shiv.googlecode.com/svn/trunk/html5.js"></script>
  		<![endif]-->
		</head>

		<body>
		...
		</body>
		</html>


####Neue Elemente####

#####semantische/strukturelle Elemente####
In Html5 wurden neue semantische/strukturelle Elemente hinzugefügt. Das heißt Elemente, die dem Browser und dem Entwickler klar sagen was sie bedeuten. 

* zum Beispiel:
	* `<footer>...</footer>`
	* `<header>`
	* `<nav>`
	* `<section>,<article>`
	* ...
* in Html4 sah das so aus:
	* `<div id="footer">...</div>`
	* `<div id="header">`
	* `<div id="menu">`
	* `<div id="content">`
	* ...
* alle neuen Elemente [hier](http://www.w3schools.com/html/html5_new_elements.asp)

 
#####Form Elemente#####

In HTML5 werden neue Formelemente eingeführt.(Diese werden nicht von allen Browsern unterstützt, aber dann erscheinen sie als Textfelder)
* `<datalist>` definiert eine Liste von vordefinierten Optionen für ein `<input>` Element (dropdown list)
	* Bsp:

			<datalist id="browsers">
  				<option value="Internet Explorer">
  				<option value="Firefox">
  				<option value="Chrome">
  				<option value="Opera">
 				<option value="Safari">
		 	</datalist>

* es gibt auch noch `<keygen>`,`<output>` [weitere Infos](http://www.w3schools.com/html/html5_form_elements.asp)

HTML5 unterstützt auch neue Input Types unter anderem:

* color
* date
* datetime
* email
* number
* ...

hinzu kommen noch neue Input Restriktionen/Attribute wie:

* disabled
* max
* min
* readonly
* required
* autofocus
* ...

[Beispiel](http://www.w3schools.com/html/tryit.asp?filename=tryhtml5_input_max_min_date)

	<form>
  	Enter a date before 1980-01-01:
  	<input type="date" name="bday" max="1979-12-31"><br>
  	Enter a date after 2000-01-01:
  	<input type="date" name="bday" min="2000-01-02"><br>
  	<input type="submit" value="Send"> 
	</form>	

* [Alle neuen Input Types/Attribute](http://www.w3schools.com/html/html5_new_elements.asp)
* [und weitere Erklärungen](http://www.w3schools.com/html/html5_form_attributes.asp)



#####Graphiken#####

HTML5 benutzt das Element **`<canvas>`** um Graphiken, on the fly, zu zeichnen via scripting. Diese Element stellt nur einen Container zur Verfügung, um das Bild zu zeichnen wird ein Skript benutzt.
([Beispiel](http://www.w3schools.com/html/tryit.asp?filename=tryhtml5_canvas_first))
		
Zusätzlich unterstützt HTML5 auch **`<svg>`**(Scalable Vector Graphics). Dieses ist eine Sprache um 2D Vektorgraphiken in XML zu beschreiben.
([Beispiel](http://www.w3schools.com/html/tryit.asp?filename=tryhtml5_svg_ex)
und [mehr Infos](http://www.w3schools.com/html/html5_svg.asp))

#####Multimedia#####

Vor HTML5 gab es keinen Standard um Videos anzeigen zu lassen. Man benötigte immer ein Plug-in. Mit dem `<video>` Element kann ein Video hinzugefügt werden und das `<source>` Element gibt die Quelle an.([Beispiel](http://www.w3schools.com/html/tryit.asp?filename=tryhtml5_video))
Jedoch werden nur MP4,WebM und Ogg Formate unterstützt, aber diese auch noch lange nicht von allen Browsern.

Bei Audio (`<audio>`) Formaten ist es ähnlich wie bei den Videos. Hier wird MP3, Wav und Ogg unterstützt.([Beispiel](http://www.w3schools.com/html/tryit.asp?filename=tryhtml5_audio_all))

#####Plug-ins#####

HTML5 hat zwei Tags um Plug-ins einzubinden `<object>,<embed>`. Beide haben die gleiche Funktion, nur gibt es `<embed>` erst seit HTML5 und wird daher nicht von allen Browsern unterstützt.

* Beispiel für [`<object>`](http://www.w3schools.com/html/tryit.asp?filename=tryhtml_object_plugin)
* Beispiel [`<embed>`](http://www.w3schools.com/html/tryit.asp?filename=tryhtml_embed_plugin)

####neue HTML APIs####

+ [Geolocation](http://www.w3schools.com/html/html5_geolocation.asp)
	+ die Funktion getCurrentPosition(), gibt die aktuelle geographische Position des Benutzers zurück
+ [Drag/Drop](http://www.w3schools.com/html/html5_draganddrop.asp)
+ [Local Storage](http://www.w3schools.com/html/html5_webstorage.asp)
	+ eine Web Application kann Daten local im Browser speichern
+ [App Cache](http://www.w3schools.com/html/html5_app_cache.asp)
	+ die Web App ist im Cache und der Benutzer kann sie auch noch offline benutzen
+ [Web Workers](http://www.w3schools.com/html/html5_webworkers.asp)
	+ der Web Worker wird unabhängig von anderen Scripts im Hintergrund ausgeführt
+ [Server-Sent Events](http://www.w3schools.com/html/html5_serversentevents.asp)
	+ die Webpage wird automatisch vom Server geupdated

####weitere nützliche Links####

* [offizielle W3C Proposed Recommendation](http://www.w3.org/TR/html5/)
* [HTML5 Handbuch](http://webkompetenz.wikidot.com/docs:html-handbuch)
* [Demos und Beispiele](http://html5demos.com/)
* Die Browser Kompabilität findet ihr jeweils auf der [W3schools-Seite](<http://www.w3schools.com/html/html5_intro.asp>)

####Quellen zu HTML5####

 
<https://de.wikipedia.org/wiki/HTML5>, Datum: 02.10.2014
<http://www.w3.org/TR/html5/>, Datum: 21.10.2014

Der HTML5 Teil des Handouts orientiert sich an der W3school, abgerufen am 02.10.2014
* <http://www.w3schools.com/html/html5_intro.asp>
* <http://www.w3schools.com/html/html5_browsers.asp>
* <http://www.w3schools.com/html/html5_new_elements.asp>
* <http://www.w3schools.com/html/html5_semantic_elements.asp>
* <http://www.w3schools.com/html/html5_migration.asp>
* <http://www.w3schools.com/html/html5_form_elements.asp>
* <http://www.w3schools.com/html/html5_form_input_types.asp>
* <http://www.w3schools.com/html/html5_form_attributes.asp>
* <http://www.w3schools.com/html/html5_canvas.asp>
* <http://www.w3schools.com/html/html5_svg.asp>
* <http://www.w3schools.com/html/html_media.asp>
* <http://www.w3schools.com/html/html5_video.asp>
* <http://www.w3schools.com/html/html5_audio.asp>
* <http://www.w3schools.com/html/html_object.asp>
* <http://www.w3schools.com/html/html5_geolocation.asp>
* <http://www.w3schools.com/html/html5_draganddrop.asp>
* <http://www.w3schools.com/html/html5_webstorage.asp>
* <http://www.w3schools.com/html/html5_app_cache.asp>
* <http://www.w3schools.com/html/html5_webworkers.asp>
* <http://www.w3schools.com/html/html5_serversentevents.asp>


##WebSockets##
####Was sind WebSockets?####
WebSockets erlauben bidirektionale Kommunikation zwischen einem Server und einem Client, ohne dabei jedes mal eine neue Verbindung aufbauen zu müssen. Nachrichten können...

* **gleichzeitig** in **beide Richtungen** (Server - Client, Client - Server)(vollduplex)
* mit geringem Overhead


...übertragen werden.[1] Websockets eignen sich deshalb besonders für Anwendungen mit viel Server-User-Interaktion oder mit mehreren Usern gleichzeitig. Beispiele sind Onlinespiele oder collaboratives Editieren von Inhalten (in unserem Fall Kartenanwendungen). 

####Bidirektional Kommunikation####
Ein Großteil der "normalen" Kommunikation zwischen Client und Server besteht darin, dass der Client einen HTTP-Request an den Server sendet und dieser ihm als Antwort darauf Informationen zurücksendet. Diese Art der Datenübertragung wird jedoch immer von Client initialisiert. Wenn auf dem Server eine Änderung der Daten stattfindet, gibt es erst dann die Möglichkeit diese Änderung zu übertragen, wenn der Client danach fragt.  
Aber auch vor der Einführung von Websockets gab es schon Möglichkeiten, im Browser dargestellte Seiten in mehr oder weniger Echtzeit mit neuen vom Server kommenden Informationen zu versorgen. So kann der Client zum Beispiel in regelmäßigen Abständen einen Request an den Server senden um zu gucken, ob sich etwas verändert hat (Polling). Eine andere Möglichkeit ist, pro forma einen Request an den Server zu senden, der jedoch erst dann beantwortet wird, wenn eine Änderung vorliegt (long Polling).  
Dies ist jedoch nur halbduplex, Nachrichten können zwar in beide Richtungen verschickt werden, jedoch ist für jede Nachricht ein eigener HTTP Request nötig. Der bei jeder Nachricht mitgesendete HTTP Header erzeugt einen relativ großen Overhead, besonders wenn sich der Zustand von Server oder Client oft ändert (z.B. Mehrspielerspiele).[2] Mit WebSockets spart man diesen Overhead ein, indem nur ein einzelner Kommunikationskanal geöffnet wird, über den sowohl Client als auch Server Nachrichten schicken können. Dieser Kanal bleibt für die länge der Session bestehen.



####Wie benutze ich WebSockets?####
Es gibt verschiedene Serverimplementierungen die das WebSocketprotokoll unterstützen sind zum Beispiel [3]:

+ Node.js
    + [Socket.IO](http://socket.io/)
    + [WebSocket-Node](https://github.com/Worlize/WebSocket-Node)
    + [ws](https://github.com/einaros/ws)
+ Java
    + [Jetty](http://www.eclipse.org/jetty/)
+ Ruby
    + [EventMachine](https://github.com/igrigorik/em-websocket)
+ Python
    + [pywebsocket](https://code.google.com/p/pywebsocket/)
    + [Tornado](http://www.tornadoweb.org/en/stable/)
+ Erlang
    + [Shirasu](https://github.com/michilu/shirasu)
+ C++
    + [libwebsockets](http://git.warmcat.com/cgi-bin/cgit/libwebsockets/)
+ .NET
    + [SuperWebSocket](http://superwebsocket.codeplex.com/)

Wie man mit JavaScript eine WebSocketverbinung aufbaut findet man [hier](http://www.html5rocks.com/de/tutorials/websockets/basics/#toc-introduction-sockets).  
Noch zu beachten ist vielleicht das Schema der URIs zur Verbindung mit einem WebSockets unterstützenden Server. Diese beginnen mit `ws:`, wenn die Verbindung unverschlüsselt ist und mit `wss:`, wenn sie verschlüsselt ist. 


####Links###

[1] <http://pusher.com/websockets>

[2] <http://www.heise.de/developer/artikel/WebSocket-Annaeherung-an-Echtzeit-im-Web-1260189.html>

[3] <http://www.html5rocks.com/de/tutorials/websockets/basics/>

Der Wikipediaartikel zu WebSockets:  
<http://de.wikipedia.org/wiki/WebSocket>

Zwei offizielle Seiten zu WebSockets:  
W3:  
<http://dev.w3.org/html5/websockets/>  
Internet Engineering Task Force:   
<http://tools.ietf.org/pdf/rfc6455.pdf>

Einige Beispiele für WebSocket-Implementierungen:   
<https://www.websocket.org/demos.html>

Welche Browser WebSockets unterstützen findet man hier:  
<http://caniuse.com/#feat=websockets>


##Linked Data##

Das klassische Internet, und auch große Teile dessen was wir täglich nutzen besteht aus Dokumenten die durch Links miteinander verbunden sind. Die Informationen, die wir aus dem Internet bekommen sind die, die in diesen Dokumenten enthalten sind. Wollen wir beispielsweise Informationen über Berlin erhalten, könnten wir den Wikipediaartikel zu [Berlin](http://de.wikipedia.org/wiki/Berlin) lesen und würden erfahren, dass Berlin die Hauptstadt, und gleichzeitig ein Bundesland, von Deutschland ist und ungefähr 3,4 Millionen Einwohner hat [1]. Wir könnten jetzt weiterlesen und uns über den [Berliner Fernsehturm](http://de.wikipedia.org/wiki/Berliner_Fernsehturm) informieren. Diese Zusammenhänge werden uns deutlich, weil wir in der Lage sind, Text zu lesen und Informationen daraus zu extrahieren. Ein Computer der vor die Aufgabe gestellt würde, die relevanten Informationen aus dem Artikel zu erarbeiten, wäre nicht dazu in der Lage, oder hätte die größten Schwierigkeiten.


Die Idee hinter Linked Data ist es jetzt eine Struktur zu schaffen, die weniger auf textuelle Informationen setzt, sondern deren Informationen in den Beziehungen zwischen einzelnen Objekten enthalten sind. Diese standardisierten Beziehungen, können auch von Computern interpretiert werden.

Daten werden nach dem [RDF Schema](http://de.wikipedia.org/wiki/Resource_Description_Framework) gespeichert. Hierbei entsteht ein gerichteter Graph, dessen Kanten durch Tripel aus Subjekt - Prädikat- Objekt beschrieben werden. Das oben genutzte Beispiel könnte beispielsweise folgende Tripel liefern:

+ Berlin - ist Hauptstadt - Deutschland
+ Berlin - ist Bundesland - Deutschland
+ Berlin - hat Einwohner - 3,4 Millionen
+ der Berliner Fernsehturm - steht in - Berlin

Diese Aussagen können auch von einem Computer verstanden werden, sofern er weiß, wie er die einzelnen Elemente zu interpretieren hat. Hier kommen Ressourcen ins Spiel, sie sind eindeutige Identifikatoren für das zu beschreibenden Objekt. Ressourcen werden eindeutig durch eine URI beschrieben. URIs müssen aber nicht zwangsweise im Netzwerk erreichbar sein.
Berlin wird beispielsweise in der [DBpedia](http://de.dbpedia.org/) mit `http://dbpedia.org/resource/Berlin` identifiziert. Von anderen Quellen kann jetzt auf das in der DBpedia-Datenbank enthaltene Berlin verwiesen werden, was demjenigen, der dem Verweis folgt alle in DBpedia enthaltenen Informationen und Verweise zur Verfügung stellt.

Es gilt, Subjekt und Prädikat müssen immer Ressourcen sein, das Objekt kann aus einer Resource bestehen, kann aber auch auf einen elementaren Wert verweisen (Literal). In unserem Beispiel wäre dies bei der Einwohnerzahl der Fall, diese Beziehung verweist auf eine einfache Zahl.
Prädikate bestehen aus Ressourcen, die jedoch keinen Gegenstand beschreiben, sondern eben die Beziehung zwischen zwei Objekten.

Mit Hilfe dieser Beschreibungen ist es möglich auch komplexe Zusammenhänge zu formalisieren und durch Abfragesprachen wie [SPARQL](http://de.wikipedia.org/wiki/SPARQL) abzufragen.

*Anmerkung:* Es macht Sinn, wenn die URI, die eine Resource beschreibt aufrufbar ist, und selbst weiterführende Informationen in Form von RDF Tripeln liefert nur so wächst der Graph und können die verfügbaren Informationen vermehrt werden



####Links####
[1] <http://de.wikipedia.org/wiki/Berlin>

Wikipediaartikel Linked Data:  
<http://de.wikipedia.org/wiki/Linked_Open_Data>

DBpedia  
<http://de.dbpedia.org/>

*Weiterführende Links:*

Lodum - Linked Open Data University of Münster  
<http://lodum.de/>
