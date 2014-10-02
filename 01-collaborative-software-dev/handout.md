# Collaborative Software Development 
*Geosoftware II, WS 14/15    Luisa Bodem, Fabian Weber*
### Was ist *Collaborative Software Development*? 

Collaborative Software Development bezeichnet das gemeinsame Arbeiten an einem Softwareprojekt mit verschiedenen Personen und/oder Teams über meist räumlich verteilte Orte. Dabei werden verschiedene Tools und Technologien eingesetzt, die die Kommunikation und Kollaboration ermöglichen und fördern.

### Gründe zur Verwendung
In der heutigen Zeit haben Flexibilität und Mobilität eine hohe Bedeutung für Arbeitnehmer. Eben diese Eigenschaften bietet Collaborative Software Development als Modell der Entwicklung. Es erlaubt sowohl flexible Arbeitsplätze als auch Arbeitszeiten. Entwickler können jederzeit, unabhängig von ansonsten gemeinsamen Bürozeiten, an Elementen eines Projektes arbeiten – egal ob dies nun auf der Reise, zu Hause oder beliebig unterwegs ist. Dies ermöglicht nicht nur eine hohe Flexibilität, sondern auch Verfügbarkeit des Mitarbeiters für den Arbeitgeber.
Ebenso ist die kollaborative Softwareentwicklung auch heute noch ein großer Bestandteil der Open-Source-Gemeinschaft.
 
#### Vorteile 

- Einfacher Austausch in Open-Source-Projekten
- Höhere Mobilität für Unternehmen, Mitarbeiter
- Peer-Review (Fehler werden von Entwicklern mit mehr Erfahrung entdeckt und behoben -> Lerneffekt für weniger Erfahrene): eine Maßnahme zur 
Qualitätssicherung
- Kontinuierliche Weiterentwicklung des Codes einfacherer realisierbar


### Versionierung 

Die heute genutzten und bekannten Versionsverwaltungssysteme für Sourcecode sind darauf ausgelegt, es vielen Entwicklern zu ermöglichen, gleichzeitig am Code eines Projektes zu arbeiten. Viele Prinzipen und Begriffe sind bei den verschiedenen Systemen gleich: Das Repository ist der Ort, an dem das Projekt bzw. dessen Sourcecode gespeichert wird. Hierin enthalten sind die verschiedenen Branches des Projektes, also die verschiedenen Versionen bzw. Ableger des Hauptentwicklungszweiges, z.B. wichtige Meilensteine oder Kandidaten für finale Versionen. Mit Tags kann man ebenfalls Dateirevisionen kennzeichnen, zum Beispiel solche, die als funktionierend bekannt sind und in die nächste Version mit einfließen sollen. Technisch gesehen besteht ein Repository nur aus einem Ordner in dem die Projektdateien gespeichert sind, Branches und Tags sind Unterordner hiervon mit den entsprechenden Kopien eines Versionsstandes der Dateien. Die Verwaltung dieser Dateien und Ordner ist Aufgabe des Verwaltungssystems.

 
Möchte man an der Entwicklung eines Projektes teilnehmen, so wird man zunächst den Code mit einem passenden Client herunterladen (“check out”/”clone”). Um seinen veränderten Code wieder ins Projekt einfließen zu lassen, stellt man ihn wieder in das Verwaltungssystem (“check in”/”commit”). Um zu verhindern, dass Daten bei gleichzeitiger Änderung mehrerer Entwickler verloren gehen, kann man eine Datei vor Änderung entweder sperren (“lock”) oder man fügt die 
Änderungen am Ende des Bearbeitungsvorganges zusammen (“merge”), wenn dabei keine Konflikte entstehen. 


Bei der Versionsverwaltung unterscheidet man zwischen zwei Arten von Systemen, den verteilten und den zentralen Systemen. In zentralen Verwaltungssystemen existiert ein Repository mit zugehöriger Versionsgeschichte in dem Änderungen direkt vorgenommen werden. Bekannte Beispiele für zentrale Verwaltungssystem sind Concurrent Version System (CVS), dessen Entwicklung jedoch eingestellt wurde, und Apache Subversion (SVN).
Im Gegensatz zu zentralen System legt sich bei einer verteilten Versionsverwaltung jeder Entwickler ein eigenes Repository eines Projektes an. Möchte man an einem Projekt mitarbeiten, so klont man dessen Repository und arbeitet an diesem. Es entsteht ein neuer Branch dieses Projektes. Über Pull Requests kann man Veränderungen an seinem Repository in das ursprüngliche Projektrepository wieder einfließen lassen. 

##### Bekannte Versionsverwaltungssysteme: 


- **CVS** `(http://www.cvshome.org/)`
- **SVN** `(http://tortoisesvn.net/)`
- **Git** `(http://git-scm.com/)`
- **Mercurial** `(http://mercurial.selenic.com/)` 
- **Bazaar** `(http://bazaar.canonical.com/en/)`

### Webbasierte Hosting-Dienste

#### GitHub `(https://github.com/)`
-   Erlaubt nur Git als Versionsverwaltung
-	Bekannte Projekte auf Git: Linux Mint, PHP, jQuery
-	Nur öffentliche Repositories, diese aber dauerhaft kostenlos 
-	Private Repositories gegen Entgelt


#### SourceForge `(http://sourceforge.net/)`

-	Erlaubt SVN, Git, Mercurial, Bazaar, CVS
-	Bekannte Projekte auf SourceForge: VLC, 7zip
-	Nur öffentliche Repositories
-	Kostenlose Version: https://fusionforge.org/
-	Jedes Projekt kann ein eigenes Wiki anlegen


#### BitBucket `(https://bitbucket.org/)`

-	Erlaubt Git oder Mercurial
-	Teilweise kostenlos
-	Stellt private Repositories zur Verfügung an denen man mit maximal 5 Leuten arbeiten kann

#### Google Code`(https://code.google.com/)`
-	Erlaubt SVN, Mercurial, Git
-	Nur öffentliche Repositories
-	Kostenlos

### Projektmanagement

Das kollaborierte Arbeiten an Sourcecode ist jedoch in der Softwareentwicklung nicht die einzige Herausforderung, die es zu bewältigen gilt. Geht es um die Projektplanung und die Dokumentation des Fortschritts, so bietet **Trello** (*https://trello.com/*) eine unterstützende Plattform. 
Diese ermöglicht die Organisation einzelner Aufgaben oder Teilbereiche mittels Boards und Cards. Auf einem Board kann man beliebig viele Cards anlegen und ausrichten, wie beispielsweise die zeitliche Abfolge sein soll. Ebenso können Listen erzeugt werden, die den aktuellen Fortschritt darlegen. Den einzelnen Cards lassen sich beliebige Anhänge zufügen und Aufgaben können direkt an andere Trello Mitglieder delegiert werden. 

### Wikis
In der Softwareentwicklung wurde der immense Nutzen von Wikis für ein effektives Wissensmanagement in einem kollaborativen Umfeld zuerst erkannt. Ein Wiki-System kann in der Softwareentwicklung insbesondere der Erstellung von Dokumentationen, zur Verwaltung von Softwarefehlern oder der Koordination unter den Software-Entwicklern dienen. Insbesondere in Entwicklungsprojekten von Open-Source-Software fällt den Wikis eine Schlüsselrolle zu. Heute kommen Wikis in einer Vielzahl von Anwendungen zum Einsatz, bei denen inhaltliche Flexibilität mehr zählt als ein repräsentatives Layout.

weitere Informationen unter: `(https://ub-madoc.bib.uni-mannheim.de/1649/1/Wikis_SE_Arbeitspapier_2007_03_16.pdf)`

### Weiterführende Links
- **Egit**, Github Integration in Eclipse: `(http://eclipse.org/egit/download/)`
- Egit Tutorial: `(http://eclipsesource.com/blogs/tutorials/egit-tutorial/)`
- Egit Wiki: `(https://wiki.eclipse.org/EGit/User_Guide)`
