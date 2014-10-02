#WebSockets und HTML5#
##HTML5##
HTML5 ist:

* ...eine textbasierte Auszeichnungssprache zur Strukturierung und semantischen Auszeichnungen von Inhalten wie Texten, Bildern und Hyperlinks in Dokumenten.
* ...der Nachfolger von HTML4, unterstützt dieses aber.
* ...am 16.09.2014 als künftige HTML5 Empfehltung von W3C veröffentlicht worden.

[weitere allgemeine Infos](https://de.wikipedia.org/wiki/HTML5 "weiter allgemeine Infos")


###Veränderungen zu HTML4###
####Aufbau eines HTML5 Dokumentes####

* als Erstes die Doctypedeklaration:

		<!DOCTYPE html>
		<html>

* dann der Kopf, in diesen gehört der Titel, die encoding declaration,...

		<head>
  		<title>Styling HTML5</title>
		<meta charset="utf-8">

* ... das Styling, siehe nächsten Abschnitt...

* ... und damit auch die neuen Style Elemente von HTML5 bei alten Browser funktionieren gibt es "the shiv" (HTML5 Enabling JavaScript). Ohne diesen Kommentar werden von alten Browsern unbekannte Elemente einfach als "inline elements" angezeigt.


  		<!--[if lt IE 9]>
  		<script src="http://html5shiv.googlecode.com/svn/trunk/html5.js"></script>
  		<![endif]-->
		</head>

		<body>
		...
		</body>
		</html>


####Styles####
 

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

HTML5 benutzt das Element **`<canvas>`** um Graphiken, on the fly, zu zeichnen via scripting. Diese Element stellt nur einen Kontainer zur verfügung, um das Bild zu zeichnen wird ein Skript benutzt.
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

####Funktionen####

+ [Geolocation](http://www.w3schools.com/html/html5_geolocation.asp)
+ [Drag/Drop](http://www.w3schools.com/html/html5_draganddrop.asp)
+ [Local Storage](http://www.w3schools.com/html/html5_webstorage.asp)
+ [App Cache](http://www.w3schools.com/html/html5_app_cache.asp)
+ [Web Workers](http://www.w3schools.com/html/html5_webworkers.asp)
+ [SSE](http://www.w3schools.com/html/html5_serversentevents.asp)


##WebSockets##
##Linked Data##

