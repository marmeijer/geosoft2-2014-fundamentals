## Collaborative Software Development ##
Geosoftware II, WS 14/15               
Fabian Weber, Luisa Bodem
## Was ist Collaborative Software Development?  ##

„die Abdeckung der **Kommunikations** - und **Koordinationsbedarfe** innerhalb eines Softwareentwicklungsprozesses, die für die Planung, Durchführung und Abstimmung aller aufgabenbezogenen, zeitlich und räumlich verteilten Aktivitäten erforderlich sind. Die kooperative Softwareentwicklung umfasst dementsprechend alle prozess- und produktbezogenen Aktivitäten aller Beteiligten, deren gemeinsames Ziel die Erstellung eines Softwareproduktes ist“
(Altmann, Josef: Kooperative Softwareentwicklung – Rechnerunterstützte Koordination und Kooperation in Softwareprojekten. Dissertation, Universitätsverlag Rudolf Trauner, Linz 1999)

**Collaborative Software Development** bezeichnet das gemeinsame Arbeiten an einem Softwareprojekt mit verschiedenen Personen und/oder Teams über meist räumlich verteilte Orte. Dabei werden verschiedene Tools und Technologien eingesetzt, die die Kommunikation und Kollaboration ermöglichen und fördern.
 
Entstanden ist der Gedanke von gemeinschaftlicher Softwareentwicklung mit der Entwicklung des Linux-Kernels im Jahr 1991. Mit der wachsenden Open-Source-Gemeinschaft entstand auch die Notwendigkeit von Informations- und im einfachsten Fall auch Quellcodeaustausch. Und so ist die kollaborative Softwareentwicklung auch heute noch ein großer Bestandteil der Open-Source-Gemeinschaft.
 
In der heutigen Zeit haben Flexibilität und Mobilität eine hohe Bedeutung für Arbeitnehmer. Eben diese Eigenschaften bietet Collaborative Software Development als Modell der Entwicklung. Es erlaubt sowohl flexible Arbeitsplätze als auch Arbeitszeiten. Entwickler können jederzeit, unabhängig von ansonsten gemeinsamen Bürozeiten, an Elementen eines Projektes arbeiten – egal ob dies nun auf der Reise, zu Hause oder beliebig unterwegs ist. Dies ermöglicht nicht nur eine hohe Flexibilität, sondern auch Verfügbarkeit des Mitarbeiters für den Arbeitgeber.
 
**Vorteile:**
 
* Einfacher Austausch in Open-Source-Projekten 
* Höhere Mobilität für Unternehmen 
* Peer-Review (Fehler werden von Entwicklern mit mehr Erfahrung entdeckt und behoben -> Lerneffekt für weniger Erfahrene): eine Maßnahme zur Qualitätssicherung 
* Kontinuierliche Weiterentwicklung des Codes einfacherer realisierbar 
* effektiveres Arbeiten an Projekten
* geringere Kosten bei gleichbleibender Qualität
* kürzerer Entwicklungszeitraum

**Effektivität:**

Laut des „*Collaborative Development Trends Report*“ der Linux Foundation vom März 2014 ist die kollaborativ Softwareentwicklung eine bevorzugte Art der Entwicklung bei großen Unternehmen. Die Daten wurden erhoben von 686 Softwareentwicklern und Managern von Unternehmen mit mehr als 500 Millionen Dollar Jahresumsatz und mehr als 500 Angestellten. Dieser Bericht bestätigt einige Vermutungen und Erfahrungen, die teils bereits unter den Vorteilen angesprochen wurden. So gaben 77 Prozent der Befragten an, dass kollaborative Softwareentwicklung half den Entwicklungszeitraum enorm zu verkürzen. Für die Unternehmen stellten sich des Weiteren Vorteile heraus, dass die Kosten der Entwicklung sanken und gleichzeitig die Qualität der Software stieg.
Mehr als 80 Prozent der Entwickler fanden die Art der Entwicklung persönlich hilfreich, sei es bei der Erweiterung des eigenen Netzwerks unter Entwicklern, dem Kennenlernen neuer Entwicklungsmethoden aber auch einfach dem Gefühl ein Teil etwas großem zu sein.

## Versionierung und Versionsverwaltung ##
Bei der Arbeit an komplexeren Projekten kommt man an der Versionierung von Sourcecode nicht vorbei. Ein **Versionsverwaltungssystem** hilft dabei getätigte Änderungen im Überblick zu behalten, Änderungen zu kontrollieren, verschiedene Entwicklerzugriffe zu koordinieren aber auch Revisionen eines früheren Zeitpunktes wiederherzustellen.

Die heute genutzten und bekannten Versionsverwaltungssysteme für Sourcecode sind darauf ausgelegt, es vielen Entwicklern zu ermöglichen, **gleichzeitig** am Code eines Projektes zu arbeiten. Viele Prinzipen und Begriffe sind bei den verschiedenen Systemen gleich: Das **Repository** ist der Ort, an dem das Projekt bzw. dessen Sourcecode gespeichert wird. Hierin enthalten sind die verschiedenen **Branches** des Projektes, also die verschiedenen Versionen bzw. Ableger des Hauptentwicklungszweiges, z.B. wichtige Meilensteine oder Kandidaten für finale Versionen. Mit **Tags** kann man ebenfalls Dateirevisionen kennzeichnen, zum Beispiel solche, die als funktionierend bekannt sind und in die nächste Version mit einfließen sollen. Technisch gesehen besteht ein Repository nur aus einem Ordner in dem die Projektdateien gespeichert sind, Branches und Tags sind 
Unterordner hiervon mit den entsprechenden Kopien eines Versionsstandes der Dateien. Die Verwaltung dieser Dateien und Ordner ist Aufgabe des Verwaltungssystems. 

Möchte man an der Entwicklung eines Projektes teilnehmen, so wird man zunächst den Code mit einem passenden Client herunterladen (**check out/clone**). Um seinen veränderten Code wieder ins Projekt einfließen zu lassen, stellt man ihn wieder in das Verwaltungssystem (**check in/commit** ). Um zu verhindern, dass Daten bei gleichzeitiger Änderung mehrerer Entwickler verloren gehen, kann man eine Datei vor Änderung entweder sperren (**lock**) oder man fügt die Änderungen am Ende des Bearbeitungsvorganges zusammen (**merge**), wenn dabei keine Konflikte entstehen.
 
Bei der Versionsverwaltung unterscheidet man zwischen **zwei Arten von Systemen**, den **verteilten** und den **zentralen Systemen**:

In zentralen Verwaltungssystemen existiert ein Repository mit zugehöriger Versionsgeschichte in dem Änderungen direkt vorgenommen werden. Möchte eine Benutzer an den Daten arbeiten, ruft er diese per check out ab. Nach den Änderungen kann er diese wieder an den Server übergeben. Bekannte Beispiele für zentrale Verwaltungssystem sind Concurrent Version System (CVS), dessen Entwicklung jedoch eingestellt wurde, und Apache Subversion (SVN).
 
Im Gegensatz zu zentralen System legt sich bei einer verteilten Versionsverwaltung jeder Entwickler ein eigenes Repository eines Projektes an. Möchte man an einem Projekt mitarbeiten, so klont man dessen Repository und arbeitet an diesem. Es entsteht ein neuer Branch dieses Projektes. Über Pull Requests kann man Veränderungen an seinem Repository in das ursprüngliche Projektrepository wieder einfließen lassen. Ein entscheidender Vorteil hierbei gegenüber eines zentralen Systems ist, dass im Falle eines Ausfalls des Servers auf dem das Repository liegt alle Daten mehrfach in ggf. verschiedenen Revisionen (in den working copies) vorhanden sind und auch wiederhergestellt werden können.
 

### Bekannte Versionsverwaltungssysteme:  ###
CVS: [http://www.cvshome.org/](http://www.cvshome.org/)

SVN: [http://tortoisesvn.net/](http://tortoisesvn.net/)

Git: [http://git-scm.com/](http://git-scm.com/)

Mercurial: [http://mercurial.selenic.com/](http://mercurial.selenic.com/) 

Bazaar: [http://bazaar.canonical.com/en/](http://bazaar.canonical.com/en/)



### Webbasierte Hosting-Dienste ###

**GitHub**: [https://github.com/](https://github.com/)
* Erlaubt nur Git als Versionsverwaltung
* Bekannte Projekte auf Git: Linux Mint, PHP, jQuery
- Nur öffentliche Repositories, diese aber dauerhaft kostenlos 
- Private Repositories gegen Entgelt
- Hilfreiches Buch: http://git-scm.com/book/de/ 
- Tutorial: https://www.youtube.com/watch?v=mvnPj_0_GmE
- **Egit**, Github Integration in Eclipse: http://eclipse.org/egit/download/
- Egit Tutorial: http://eclipsesource.com/blogs/tutorials/egit-tutorial/
- Egit Wiki: https://wiki.eclipse.org/EGit/User_Guide

**SourceForge**: http://sourceforge.net/
-	Erlaubt SVN, Git, Mercurial, Bazaar, CVS
-	Bekannte Projekte auf SourceForge: VLC, 7zip
-	Nur öffentliche Repositories
-	Kostenlose Version: https://fusionforge.org/
-	Jedes Projekt kann ein eigenes Wiki anlegen

**BitBucket**: https://bitbucket.org/
-	Erlaubt Git oder Mercurial
-	Teilweise kostenlos
-	Stellt private Repositories zur Verfügung an denen man mit maximal 5 Leuten arbeiten kann

**Google Code**: https://code.google.com/
-	Erlaubt SVN, Mercurial, Git
-	Nur öffentliche Repositories
-	Kostenlos

## Projektmanagement ##
Das kollaborierte Arbeiten an Sourcecode ist jedoch in der Softwareentwicklung nicht die einzige Herausforderung, die es zu bewältigen gilt. Geht es um die Projektplanung und die Dokumentation des Fortschritts, so bietet zum Beispiel Trello (https://trello.com/) eine unterstützende Plattform. Dies ermöglicht die Organisation einzelner Aufgaben oder Teilbereiche mittels Boards und Cards. Auf einem Board kann man beliebig viele Cards anlegen und ausrichten, wie beispielsweise die zeitliche Abfolge sein soll. Ebenso können Listen erzeugt werden, die den aktuellen Fortschritt darlegen. Den einzelnen Cards lassen sich beliebige Anhänge zufügen und Aufgaben können direkt an andere Trello Mitglieder delegiert werden. 
Hier noch eine Auflistung weiterer Projektmanagementsysteme:

**Jira**:
-	Kostenpflichtige webbasierte Anwendung zur Fehlerverwaltung, Problembehandlung und operativen Projektmanagement
-	Funktionsweise: wird vom Nutzer durch Tickets gefüllt, Tickets können einfach nur editiert werden oder den Status wechseln, jede Änderung wird geloggt
-	Tickets: können vielfältig angesehen werden; haben anpassbare Instrumententafeln (Dashboards) eigene Suchfilter und Statistiken; bestehen aus einer Projektzuordnung, einer Zusammenfassung, einem Typ, einer Priorität, einem Inhalt und aus einer oder mehreren Komponentenzuordnungen
-	Erweiterbar mit Confluence (einer Wiki-Software)
- Eine Plattform für den Kommunikations- und Wissensaustausch, unterstützt das Teilen aller PDF`s, Dokumente, Bilder; enthält eine automatische Versionierung, man kann Berechtigungen vergeben und Voll-Text suchen
- https://www.atlassian.com/de/software/jira?_mid=b00dde054b938aaa5e703e6efecca296&gclid=Cj0KEQjwtvihBRCd8fyrtfHRlJEBEiQAQcubtMBYDzGthaaahJ3QyLmX8jnkvgU5tlnm0VcmNBZiF-gaAl5f8P8HAQ
- https://www.atlassian.com/de/software/confluence
- **kostenlose Alternativen:** http://alternativeto.net/software/jira/?license=free 

**Trac**:
-	Web based
-	Enthält:
- eine webbasierte Seite zum lesenden Zugriff auf das Projektarchiv
- Einen Bugtracker zm Verwalten von Programmfehlern und Erweiterungswünschen
- Ein Wiki
-	http://trac.edgewall.org/
-	Demo-Seite: http://trac.edgewall.org/demo-1.0

**Basecamp**:
-	Funktionen:
-	To-do Listen
-	Webbasierte Textdokumente im Wiki-Style
-	Meilenstein-Management
-	Teilen von Dateien
-	Nachrichten System
-	Verfolgung der Aktivitäten in Abhängigkeit der Zeit
-	https://basecamp.com/
-	Wie es angewendet wird: https://basecamp.com/tour

### Open Source Projektmanagement Tools ###

**LibrePlan**:
-	Web based
-	Gut zugänglich für jeden Teilnehmer
-	Unterstütz die Resourcenzuweisung, Gantt charts, Finanzen
-	Hat ein modernes Design und ein ausgewogenes User Interface
-	https://www.youtube.com/watch?v=EcsR0edIiuo
-	http://www.libreplan.com/

**Open Project**:
-	Bietet eine Vielzahl an Funktionen und Plugins zur Unterstützung der Projektteams während des gesamten Projektverlaufs
-	Zeitpläne gestalten 
-	Arbeitspakete erstellen 
-	Dokumente und Code im Repository verwalten 
-	Wiki 
-	Meeting Plugin
-	Controlling Plugin 
-	Scrum Plugin,
-	News und Foren
-	https://community.openproject.org/

**]project-open[**:
-	Spezialisiert auf Organisationen mit 10-1000 Mitarbeitern
-	Bietet viele Integrationsmöglichkeiten für z.B. 
-	http://www.project-open.com/index.html
-	Zum selber ausprobieren: http://demo.project-open.net/ 

**Redmine**:
-	Web based
-	Läuft auf Ruby and Rails (quelloffenes Web Applikation Framework)
-	Es enthält zusätzlich zu den normalen Management Features ein Wiki, ein Repository und einen Verlauf der Themen, außerdem kann man Rechte vergeben und es gibt ein News und Benachrichtigungssystem
-	http://www.redmine.org/

**Weitere: http://en.wikipedia.org/wiki/Comparison_of_project_management_software**

### Wikis ###
Ein Wiki ist eine Sammlung von Texten, dessen Inhalt von Benutzern gelesen und auch geändert werden kann. So ist es möglich seine Erfahrungen und sein Wissen zu teilen und zu dokumentieren. Das gemeinschaftliche Erarbeiten von Texten nennt man auch kollaboratives Schreiben.
Ein Wiki bietet wenige Gestaltungsmöglichkeiten, denn der Focus liegt auf der Bearbeitung des Inhaltes, was auch für Neulinge so einfach wie möglich sein sollte.
Auch hier gibt es eine Versionsverwaltung, die es erlaubt frühere Versionen wiederherzustellen, wenn neuere auf Grund von Fehlern nicht gültig sind.
Mit Hyperlinks stellt man in einem Wiki die Querverbindungen zwischen den einzelnen Themen her.
Ein Wiki kann öffentlich zugänglich im Internet sein oder nur für bestimmte Nutzergruppen in lokalen Netzwerken.

**DokuWiki**:
-	Wurde für das Dokumentationsmanagement von Softwareprojekten entwickelt
-	Wikisystem, für das sich die meisten Nutzer interessieren
-	Rechteverwaltung
- Versionsverwaltung
-	Es eignet sich für Kollaborationszwecke, da nicht mehrere Nutzer eine Wikiseite zur gleichen Zeit editieren können
-	Mit unzähligen Plug-ins kann man es als vollwertiges Content-Management-System (CMS), als  Projektmanagement- und Webblog-Software oder Framework für Webanwendungen nutzen
-	https://www.dokuwiki.org/dokuwiki 

**MediaWiki**:
-	Basis von Wikipedia -> Software wird noch gepflegt
-	Zur Installation benötigt man einen Webserver und eine Datenbank
- ein eigenes Wiki-Markup
- Templates
-	Das Anlegen von Unterseiten
-	Rechtemanagement (aber mit nur drei verschiedenen Rollen)
-	Gut geeignet um Fakten zusammenzutragen und zu verwalten
-	Mit mehr als 1100 Anwendungen erweiterbar
-	http://www.mediawiki.org/wiki/MediaWiki/de 

**Wiki für den eigenen PC ohne Datenbank und Server:** **lexiCan**

**Kostenlose Hostingmöglichkeiten:** 
http://www.gutestun.org/internet/moglichkeiten-ein-wiki-gratis-zu-hosten-359/

**Liste von Wikis:** 
http://de.wikipedia.org/wiki/Liste_von_Wiki-Software 

**Vergleichsmöglichkeiten unter Wikis:**
http://www.wikimatrix.org/

**Erfahrungen zu verschiedenen Wikis:**
http://sommergut.de/wp/archives/die-wahl-der-richtigen-wiki-software/ oder http://www.heise.de/open/artikel/Freie-Wiki-Systeme-im-Vergleich-221792.html

**Einheitliche Markup Sprache für Wikis:**
http://www.wikicreole.org/wiki/Home 


