Metadaten
=========

[Metadaten](http://andreas-pfund.de/definition/metadaten/metadaten.php) sind Daten über Daten, also Informationen über andere Informationsressourcen. Sie sind besonders wichtig bei größeren Datenmengen und müssen maschinell lesbar und auswertbar sein.
Metadaten definieren die Struktur der Daten, wie sie gespeichert werden und dokumentiert werden sollen.


> 
Formate für Metadaten
- ISO 19xxx
- RDF
- OWL
- OGC Catalog
- Folksonomies
- microformats
- Dublin Core
  
  
ISO 19xxx Standards
----


**Standards**

Stellen Anforderungen, Spezifikationen, Richtilinien oder Eigenschaften für Materialien, Produkte, Prozesse oder Dienste bereit. Außerdem stellen sie sicher, dass Daten austauschbar, sicher, zuverlässig, von guter Qualität und vielseitig benutzbar sind.

>**19xxx Standards**
- [PDF 19005](http://de.wikipedia.org/wiki/PDF/A), [Qualitätsmanagement 19011](http://de.wikipedia.org/wiki/ISO_19011), [Document Schema Definition Languages (DSDL) 19757](http://de.wikipedia.org/wiki/Document_Schema_Definition_Languages)
- [Geoinformation 191xx](https://www.google.de/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&ved=0CCEQFjAA&url=https%3A%2F%2Fwww.wmo.int%2Fpages%2Fprog%2Fwww%2FWDM%2FIPET-MI-II%2Fdraft_guidance_catalogues.doc&ei=1s0qVNbXPILAPOKIgPgO&usg=AFQjCNH3tp9Ey7q3luOnF4guzmljl0N-ZA&sig2=-kO1OjzrS-RVrOX_dNICbw&bvm=bv.76477589,d.ZWU&cad=rja)
    - [Raumbezugsschema 19107](http://de.wikipedia.org/wiki/ISO_19107)
    - [Regel zur Erstellung von Anwendungsschemata 19109](http://de.wikipedia.org/wiki/ISO_19109)
    - [Geographisches Objekt](http://de.wikipedia.org/wiki/Geographisches_Objekt)
    - [Koordinatenreferenzsysteme 19111](http://de.wikipedia.org/wiki/ISO_19111)
    - [Qualitätsgrundsätze 19113](http://de.wikipedia.org/wiki/ISO_19113)
    - [Metadaten 19115](http://de.wikipedia.org/wiki/ISO_19115)
    - [Coverage Geometrie u. Funktionsschema 19123](http://de.wikipedia.org/wiki/ISO_19123)
    - [Registrierungsverfahren für geographische Informationseinheiten 19135](http://de.wikipedia.org/wiki/ISO_19135)
    - [Geography Markup Language (GML) 19136](http://de.wikipedia.org/wiki/ISO_19136)

[**191xx Standards**](https://www.google.de/url?sa=t&rct=j&q=&esrc=s&source=web&cd=4&ved=0CDYQFjAD&url=http%3A%2F%2Fwww.wmo.int%2Fpages%2Fprog%2Fwww%2FTECO-WIS%2F1-3-1_WMO-PKerherve_ISO-191xx-Geographic.pps&ei=2GkpVOrJBYHB7AaEkoCAAw&usg=AFQjCNGxQwO62dlzZ0sAa56KZowWUg6XFg&sig2=9K4x9c7E6p2uwy4SJNivyg&bvm=bv.76247554,d.ZGU&cad=rjahttps://www.google.de/url?) behandeln digitale Geoinformationen. Durch das Definieren, Beschreiben und Regeln wird Interoperabilität von Geoinformationssystemen ermöglicht. So können Geoinformationen plattformunabhängig benutzt werden.

<img src="ISO_UEBERSICHT.jpg" alt="ISO_UEBERSICHT.jpg">



RDF - Resource Description Framework
----

[RDF](http://www.w3.org/RDF/) ist ein System zur Beschreibung von Ressourcen. Ursprünglich war es ein Standard zur Beschreibung von Metadaten, mittlerweile ist es ein grundlegender Baustein des semantischen Webs. RDF ist sehr nützlich, um global einen eindeutigen Bezeichner für Ressourcen zu haben.

**Tripel**

Im RDF-Modell, welches eine formale Semantik besitzt und auf dem gerichteten Graphen basiert, enthält eine Aussage Subjekt, Prädikat und Objekt. Eine Ressource wird als Subjekt mit einer anderen Ressource oder einem Wert als Objekt mit einer weiteren Ressource als Prädikat näher beschrieben.

Ein Tripel stellt eine Behauptung dar: Subjekt und Objekt miteinander in Beziehung/Relation gesetzt.

```sh
Subjekt --> Objekt Prädikat

       * Geoinformatik enthält Geodatenmanagement

       * Bäume haben Blätter

       * Straßen bilden Netzwerke
       
    Subjekte: Geoinformatik, Bäume, Straßen
    Prädikate: enthält, haben, bilden
    Objekte: Geodatenmanagement, Blätter, Netzwerke

```



**URI - Uniform Resource Identifier**


Eine Ressourcen ist eindeutig bezeichnet und kann Subjekt Prädikat oder Objekt sein. Objekte können auch ein Literal sein, d.h. eine Zeichenkette wie z.B. Wahrheitswerte, Zahlen oder Datumsanganben.

RDF-Ressourcen werden durch einen eindeutigen Bezeichner, eine URI, identifiziert. Diese ähneln der Form einer URL, denn sie ist eine spezielle URI zum identifizieren von Websites.

Beispiel
```sh

    URI einer Website: http://geofs.uni-muenster.de/geoinf/doku.php

    URI einer Mailadresse: mailto:fsgi@uni-muenster.de

    URI eines Buches: urn:isbn:3-87907-265-5

```

Code-Beispiel
```sh
<?xml version="1.0"?>

<rdf:RDF
xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#"
xmlns:cd="http://www.recshop.fake/cd#">

<rdf:Description
rdf:about="http://www.recshop.fake/cd/Empire Burlesque">
  <cd:artist>Bob Dylan</cd:artist>
  <cd:country>USA</cd:country>
  <cd:company>Columbia</cd:company>
  <cd:price>10.90</cd:price>
  <cd:year>1985</cd:year>
</rdf:Description>

<rdf:Description
rdf:about="http://www.recshop.fake/cd/Hide your heart">
  <cd:artist>Bonnie Tyler</cd:artist>
  <cd:country>UK</cd:country>
  <cd:company>CBS Records</cd:company>
  <cd:price>9.90</cd:price>
  <cd:year>1988</cd:year>
</rdf:Description>

</rdf:RDF> 
```

XMP (Extensible Metadata Platform) ist eine praktische Anwendung von RDF. 
[Weitere Informationen hierzu](http://www.pdfa.org/2011/09/pdfa-metadaten-xmp-rdf-dublin-core/?lang=de)



OGC - Catalog
---

[Open Geospatial Consortium](http://www.opengeospatial.org/) ist eine Organisation, die Standards im Bezug auf Geodaten bereitstellt.
Diese stellen unter anderem folgenden Dienst bereit: [OGC - Catalog](http://www.opengeospatial.org/standards/cat)

<img src="OGC_GRAFIK.png" width="500" alt="OGC_GRAFIK-png">

Dieser bietet die Möglichkeit eine Ansammlung von Metadaten zu veröffentlichen und zu durchsuchen. Die dort hinterlegten Daten sind nur beschreibende Metadaten, welche durch gängige ISO Standards codiert wurden (z.B. ISO 19115 und 19119).

**Operationen**

* GetCapabilities
	* Abfragen, die diesen Catalog Service beschreiben
* DescribeRecord
	* Abfrage des XML-Schemas der Metadaten, die eine bestimmte Ressource beschreiben
* GetRecords
	* Abfrage von Metadaten der Ressourcen
* GetRecordById
	* Abfrage von Metadaten der Ressource mit einer bestimmten ID
* Transaction
	* Erstellen, Verändern und Löschen von bestimmten Metadaten
* Harvest
	* Einfügen oder Aktualisieren von Metadaten durch einlesen von Metadaten anderer Archive (repositories)

**Beispiel**
```sh
http://www.geoportal1.nrw.de/soapServices/CSWStartup?service=CSW&version=2.0.2&request=GetCapabilities
```

OWL - Web Ontology Language
---

[Web Ontology Language](http://www.w3.org/2001/sw/wiki/OWL) (= OWL) ist eine formale Beschreibungssprache zur Erstellung, Publikation und Verteilung von Ontologien. Technisch basiert sie auf der RDF-Syntax, allerdings weißt die OWL eine höhere Ausdrucksmächtigkeit auf. Aus diesem Grund wird OWL im Web-Bereich bevorzugt, außerdem dient sie dazu Daten zu verarbeiten und nicht "nur" darzustellen.

## 3 Untersprachen ##
Bei jeder Untersprache gelden folgende Beziehungen, aber nicht Umgekehrt:

* Jede korrekte OWL Lite Ontolie ist eine korrekte OWL DL Ontologie
* Jede korrekte OWL DL Ontologie ist eine korrekte OWL Full Ontologie
* Jede gültige OWL Lite Schlussfolgerung ist eine gültige OWL DL Schlussfolgerung
* Jede gültige OWL DL Schlussfolgerung ist eine gültige OWL Full Schlussfolgerung

### OWL - Lite ###
Unterstützt Nutzer, die Klassifikationshierarchien und einfache Restriktionen benötigen.

### OWL - DL ###
Unterstützt Nutzer, die eine maximale Ausdrucksstärke bei vollständiger Verarbeitbarkeit und Entscheidbarkeit haben möchte. Dies schließen alle Sprachkonstruktionen ein, welche man dann, nur unter bestimmten Voraussetzungen benutzen kann.
###### Beispiel ######
Eine Klasse kann Unterklasse von vielen Klassen sein, aber nur Instanz von einer anderen Klasse.

### OWL - Full ###
Unterstützt Nutzer, die volle Ausdrucksstärke und syntaktische Freiheit haben möchten. Allerdings muss man hierbei beachten, dass es keine Gewissheit gibt, ob man diese letzten endes verwenden kann.
###### Beispiel ######
Eine Klasse wird als Collection von Individuen behandelt,kann  aber auch als ein eigenes Individuum.

## Struktur ##
#### Header ####
Beschreibt und führt Informationen über:

* Namensräume (rdf,rdfs, owl, dc, ...)
* Kommentare
* Versionskonrolle
* Einbeziehen anderer Ontologien

#### Body ####
Beschreibt und führt Informationen über:

* Bezeichnung
	* *rdf:ID*
* hierarchische Klasse
	* *<owl:Class rdf:ID="Gebiet">*
* Individuen
	* implizit ein Element der Klasse *owl:thing*
	* z.B. *<Gebiet rdf:ID=...>*
* komplexere Strukturen
	* Objekteigenschaften
		* *ObjectProperty*
	* Datentypeigenschaften
		* *domain*
		* *range*
	* Eigenschaftsbeschränkungen
		* *alleValue* oder *hasValue*

### Beispiel ###
###### 1. Beispiel ######
Das UML-Diagramm zeigt, dass *Stadt* eine Unterklasse von *Ort* ist und der widerrum eine Unterklasse von *Gebiet*. Weiter wird festgelegt, dass *Berlin* eine Instanz von *Stadt* ist.

<img src="OWL_BSP1.png" width="150" align="center" alt="Bild: OWL_BSP1.png">

```sh
	<owl:Class rdf:ID="Ort"/>
	<owl:Class rdf:ID="Stadt"> 
		<rdfs:subClassOf rdf:resource="#Ort"/> 
	</owl:Class>
  <Stadt rdf:ID="Berlin"/>

```

###### 2. Beispiel ######
Das UML-Diagramm zeigt die Beziehung zwischen *Wein* und einer *Weinkellerei*, nämlich *hergestelltVon*.

<img src="OWL_BSP2.png" alt="Bild: OWL_BSP2.png">

```sh
<owl:ObjectProperty rdf:ID="hergestelltVon"> 
	<rdfs:domain rdf:resource="&owl;Thing"/> 
	<rdfs:range rdf:resource="&owl;Thing"/>
</owl:ObjectProperty> 

<owl:Class rdf:ID="Wein">
	<rdfs:subClassOf>
		<owl:Restriction>
			<owl:onProperty rdf:resource="hergestelltVon"/>
			<owl:allValuesFrom rdf:resource="Weinkellerei"/>
			<owl:cardinality>1</owl:cardinality> 
		</owl:Restriction>
	</rdfs:subClassOf>
</owl:Class>
```

Der Header zeigt an, welche Beziehung beschrieben wird und welche *domain* und *range* gegeben sind. Hier: alle Elemente der Klasse *owl:Thing*. Im Body wird die Klasse *Wein* genauer beschrieben, nämlich dass *Wein* alle Werte der *Weinkellerei* übernehmen soll, von dieser hergestellt wird und nur von genau einer hergestellt wird.


# Folksonomy #

> *„**Folksonomy*** is the result of **personal free tagging** of information and objects (anything with a URL) for one's own retrieval. The tagging is done **in a social environment** (usually shared and open to others). Folksonomy is **created** from the act of tagging **by the person consuming the information**.“*

[Folksonomy](http://www.socialtagging.org/) setzt sich aus *Folks* und *Taxonomie* zusammen. Es gibt bei einer Folksonomy keine hierarchische Struktur, die Tags sind gleichwertig.
Tags sind simple Tupel aus *Bezeichnendem, Bezeichnetem, Tag und ggf. der Zeit*.


# Microformats #

Microformats( zu Deutsch Mikroformate) ist eine Sammlung von Auszeichnungsformaten zur semantischen Annotation von HTML oder XHTML, die sowohl gut lesbar für Menschen als auch für Maschinen sind. Ein Microformat beschreibt ein spezifisches Themengebiet (Personen, Plätze, Veranstaltungen, …) Diese Auszeichnungen lassen sich einfach aus den Internetseiten auslesen ( Beispiel : Firefox Plug-in„Operator“)
## Bespiele von Microformats ##
* hCard
* hCalendar
* adr
* hproduct
* geo

Es gibt meistens notwendige und optionale Elemente eines Microformats.
### hCard ###
Dient zur Beschreibung von Personen, Firmen und Organisationen. Beispiel in HTML :

[Spezifikation](http://www.microformats.org/wiki/hcard "Spezifikation")
<pre><code>
	&lt;ul class="vcard"&gt;
		&lt;li class="fn">Joe Doe&lt;/li> 
		&lt;li class="org">The Example Company</li> 
		&lt;li class="tel">604-555-1234</li>
		&lt;li><a class="url" href="http://example.com/">http://example.com/</a>&lt;/li>
	&lt;/ul>

und hier wie es angezeigt wird:
<ul class="vcard">
	<li class="fn">Joe Doe</li> 
	<li class="org">The Example Company</li> 
	<li class="tel">604-555-1234</li>
	<li><a class="url" href="http://example.com/">http://example.com/</a></li>
</ul>
</code>
</pre>

### hCalendar ###
dient zur Beschreibung von Veranstultungen. Beispiel in HTML :

[Spezifikation](http://www.microformats.org/wiki/hcalendar "Spezifikation")
<pre><code>
	&lt;span class="vevent">
	&lt;span class="summary">The microformats.org site was launched</span> on &lt;span class="dtstart">2005-06-20</span> at the Supernova Conference in 
	&lt;span class="location">San Francisco, CA, USA</span>. </span>

</code>
und hier wie es angezeigt wird:
<span class="vevent">
	<span class="summary">The microformats.org site was launched</span> on <span class="dtstart">2005-06-20</span> at the Supernova Conference in 
	<span class="location">San Francisco, CA, USA</span>. </span>
</ul>
</pre>

### adr ###
dient zur Beschreibung von Adressen. Beispiel in HTML :

[Spezifikation](http://www.microformats.org/wiki/adr "Spezifikation")
<pre><code>
	&lt;div class="adr">
		&lt;div class="street-address">665 3rd St.</div> &lt;div class="extended-address">Suite 207</div>
		&lt;span class="locality">San Francisco</span>, <span class="region">CA</span>
		&lt;span class="postal-code">94107</span>
		&lt;div class="country-name">U.S.A.</div>
	&lt;/div>
</code>
und hier wie es angezeigt wird:
	<span class="vevent">
	<div class="adr">
	<div class="street-address">665 3rd St.</div> <div class="extended-address">Suite 207</div>
	<span class="locality">San Francisco</span>, <span class="region">CA</span>
	<span class="postal-code">94107</span>
	<div class="country-name">U.S.A.</div>
	</div>
</ul>
</pre>

### hProduct(nur Draft, Version 0.3) ###
dient zur Beschreibung von Produkten. Beispiel in HTML :

[Spezifikation](http://www.microformats.org/wiki/hproduct "Spezifikation")
<pre><code>
	&lt;div class="hproduct"> 
		&lt;span class="brand">ACME</span>
		&lt;span class="fn">Executive Anvil</span> 
		&lt;img class="photo" src="http://microformats.org/wiki/skins/Microformats/images/logo.gif" />
		&lt;span class="review hreview-aggregate"> 
		Average rating: &lt;span class="rating">4.4</span>
		, based on &lt;span class="count">89 </span> reviews </span> Regular price: $179.99 Sale: $&lt;span class="price">119.99</span> (Sale ends 5 November!) 
		&lt;span class="description">Sleeker than ACME's Classic Anvil, the Executive Anvil is perfect for the business traveler looking for something to drop from a height.</span> 
		Category: &lt;span class="category"> 
		&lt;span class="value-title" title="Hardware > Tools > Anvils">Anvils</span> </span>
	&lt;div>
</code>
und hier wie es angezeigt wird:
	<div class="hproduct"> 
	<span class="brand">ACME</span>
	<span class="fn">Executive Anvil</span> 
	<img class="photo" src="http://microformats.org/wiki/skins/Microformats/images/logo.gif" />
	 <span class="review hreview-aggregate"> 
	Average rating: <span class="rating">4.4</span>, based on <span class="count">89 </span> reviews </span> Regular price: $179.99 Sale: $<span class="price">119.99</span> (Sale ends 5 November!) 
	<span class="description">Sleeker than ACME's Classic Anvil, the Executive Anvil is perfect for the business traveler looking for something to drop from a height.</span> 
	Category: <span class="category"><span class="value-title" title="Hardware > Tools > Anvils">Anvils</span> </span>
</div>
</ul>
</pre>

### geo(nur Draft) ###
dient zur Beschreibung von Koordinaten. Beispiel in HTML :

[Spezifikation](http://www.microformats.org/wiki/geo "Spezifikation")
<pre><code>
	We met at a
	&lt;span class="geo">
	&lt;span class="latitude">
		&lt;span class="value-title" title="37.386013"> </span> </span>
	&lt;span class="longitude">
		&lt;span class="value-title" title="-122.082932"> </span> </span> certain location </span>
</code>
und hier wie es angezeigt wird:
<span class="vevent">
	We met at a <span class="geo"><span class="latitude"><span class="value-title" title="37.386013"></span></span><span class="longitude"><span class="value-title" title="-122.082932"></span></span> certain location </span>

</div>
</ul>
</pre>

# Dublin Core #
Ist ein Datenformat welches Dokumente und Objekte so beschreibt, damit diese leichter auffindbar sind. Es wurde 1995 bei einer Konferenz beschlossen. Seit 2009 ist es ein ISO Standard: [ISO 15836](http://www.iso.org/iso/catalogue_detail.htm?csnumber=52142). Die Elemente von Dublin Core dürfen in einer beliebigen Reihenfolge, so oft wie man will genutzt werden. Jedes Element ist optional.
## Die 15 Kernfelder von Dublin Core Metadata Element Set  1.1 ##

Englische [Spezifikation](http://dublincore.org/documents/dces/)

* Format
* Type
* Language
* Date
* Identifier
* Creator
* Publisher
* Contributor
* Rights
* Title
* Subject
* Description
* Coverage
* Source
* Relation

Diese Kernfelder kann man in folgende Kategorien unterteilen:

### Technische Daten ###
* **Format**: am besten als [MIME-Type](http://de.wikipedia.org/wiki/Internet_Media_Type) anzugeben
* **Type**: Sound, Image, Text, Service, ...
* **Languague**: Sprache des Dokumentes. Empfohlene Angabe nach [ISO 693](http://www.iso.org/iso/home/standards/language_codes.htm)
* **Date**: Startdatum oder Zeitspanne der Gültigkeit für das Objekt. Empfohlene Angabe nach [ISO 8601](http://www.iso.org/iso/home/standards/iso8601.htm)
* **Identifier**: Eindeutige Identifizierung des Objektes durch ISBN, URL, DOI, etc. 


### Inhaltsbeschreibung ###
* **Title**: Titel des Dokumentes
* **Subject** : Thema des Inhalts
* **Description**:  kurze Beschreibung (abstract)
*  **Coverage**: Abdeckungsbereich ( geographisch oder zeitlich)

### Personen und Rechte ###
* **Creator**: Autor
* **Publisher**: Herausgeber
* **Contributor**: Leute die zur Entstehung des Dokumentes beigetragen haben
* **Rights**: Lizenzbedingung 

###Vernetzung ###
* **Source**:  Verweist auf Dokument(e) von welchem dieses abgeleitet wurde
* **Relation**: Verweist auf Dokument(e) mit dem es in Beziehung steht

Einbinden in HTML im &lt;head>-Teil:

	<head profile="http://dublincore.org/documents/dcq-html/"> <title>Dublin Core</title>
		<link rel="schema.DC" href="http://purl.org/dc/elements/1.1/" /> <link rel="schema.DCTERMS" href="http://purl.org/dc/terms/" /> <meta name="DC.format" scheme="DCTERMS.IMT" content="text/html" />
		<meta name="DC.type" scheme="DCTERMS.DCMIType" content="Text" />
		<meta name="DC.publisher" content="Jimmy Wales" />
		<meta name="DC.subject" content="Dublin Core Metadaten-Elemente, Anwendungen" />
		<meta name="DC.creator" content="Björn G. Kulms" />
		<meta name="DCTERMS.license" scheme="DCTERMS.URI" content="http://www.gnu.org/copyleft/fdl.html" />
		<meta name="DCTERMS.rightsHolder" content="Wikimedia Foundation Inc." />
		<meta name="DCTERMS.modified" scheme="DCTERMS.W3CDTF" content="2006-03-08" />
	</head>

Außer den genannten 15 Kerfeldern gibt es noch weitere Attribute von Dublin Core die zur Beschreibung eines Objektes dienen können. Diese findet man [hier](http://dublincore.org/documents/dcmi-terms/). Es gibt einen einfachen [Online-Code-Generator](http://www.dublincoregenerator.com/generator_nq.html
).

# Quellen #

[http://andreas-pfund.de/definition/metadaten/metadaten.php](http://andreas-pfund.de/definition/metadaten/metadaten.php)

[http://www.iso.org/iso/home/standards.htm](http://www.iso.org/iso/home/standards.htm)

[http://www.w3.org/RDF/](http://www.w3.org/RDF/)

[http://www.pdfa.org/2011/09/pdfa-metadaten-xmp-rdf-dublin-core/?lang=de](http://www.pdfa.org/2011/09/pdfa-metadaten-xmp-rdf-dublin-core/?lang=de)

[http://www.w3.org/2001/sw/wiki/OWL](http://www.w3.org/2001/sw/wiki/OWL)

[http://www.semaweb.org/dokumente/w3/TR/2004/REC-owl-features-20040210-DE.html](http://www.semaweb.org/dokumente/w3/TR/2004/REC-owl-features-20040210-DE.html)

[http://de.wikipedia.org/wiki/Web_Ontology_Language](http://de.wikipedia.org/wiki/Web_Ontology_Language)

[http://www.opengeospatial.org/](http://www.opengeospatial.org/)

[http://www.opengeospatial.org/standards/cat](http://www.opengeospatial.org/standards/cat)

[http://de.wikipedia.org/wiki/Web_Catalogue_Service](http://de.wikipedia.org/wiki/Web_Catalogue_Service)

[http://www.wissensstrukturplan.de/wissensstrukturplan/glossar/f_folk.php](http://www.wissensstrukturplan.de/wissensstrukturplan/glossar/f_folk.php)

[http://www.socialtagging.org/](http://www.socialtagging.org/)

[http://dublincore.org/](http://dublincore.org/)

[http://de.wikipedia.org/wiki/Dublin_Core](http://de.wikipedia.org/wiki/Dublin_Core)

[http://microformats.org/](http://microformats.org/)

[http://code.tutsplus.com/tutorials/microformats-what-why-and-how--net-8097](http://code.tutsplus.com/tutorials/microformats-what-why-and-how--net-8097)

[http://de.wikipedia.org/wiki/Mikroformate](http://de.wikipedia.org/wiki/Mikroformate)
