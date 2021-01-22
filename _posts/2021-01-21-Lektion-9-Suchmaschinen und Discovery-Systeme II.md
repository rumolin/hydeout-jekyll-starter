---
layout: post
title: Lektion 8 Suchmaschinen und Discovery-Systeme II
excerpt_separator: "<!--more-->"
comments: false
sidebar_link: true
categories: 
tags: 
- Discoverysysteme
- Vufind
- Solr

---

<img alt="Mobile home page" src="https://github.com/rumolin/lerntagebuch-bain/blob/master/_screenshots/Bild 9.PNG?raw=true" width="70%"/>

--- 

##### Solr und VuFind

Wir erarbeiten heute die Funktionen von Suchmaschinen am Beispiel von Solr. Solr ist Suchmaschine, Vufind Discovery-System? Solr selber hat keine Website mitgeliefert, nur Admin-Oberfläche. Solr ist für Hintergrundarbeit gedacht. Solr ist mit Elasticsearch quasi "Industriestandard". Die beiden meistgenutzten Suchmaschinen im Internet und bei volltextsuchen. Auch ausserhalb des Bibliotheksbereichs interessant. Üblicherweise soll vor Import der Daten in einem Schema festgelegt wreden, welche Felder existieren und welche Datentypen diese beinhalten dürfen. Ungeauigkeiten können so beim Import festgestellt werden. Was soll durchsucht werden muss vorher optimalerweise geklärt werden. Trotzdem gibt es inwzischen auch schemaless. Also arbeiten ohne schema. SOLR versucht Daten so gut wie möglich zu übernehmen. Tabellendaten haben oft Text oder Nummern oder Koordinaten. Daten müssen richtig zugeordnet werden, damit geokoordinaten beispielsweise nicht als Text sondern als Raumdaten durchsuchbar sind. Analog Datum und Zeiträume. Schema macht also Sinn. Solr hat integrierte Suchoberfläche in Adminoberfläche, zum nachstellen und es gibt auch Demowebsite. Allerdings nur zu Testzwecken gedacht. Viele komerzielle Produkte basieren auf SOlr, wie beispielsweise Ex Libris Primo. Auch Vufind basiert auf Solr. 

Wozu Suchindex und warum nicht Datenbank? Beides sind Systeme, die mit Daten gespeist werden mit unterschiedlichen Schwerpunkten. 

**Solr** | **MySQL
flache Dokumente (keine Beziehungen innerhalb des Index) | relationele Datensätze 
lexikalische Suche (Begriff wird mit Grammatik verstanden und dementsprechend behandelt, beispielsweise Verben auf Grundform brechen und dann sinngemäss suchen) | reiner Glyphenvergleich (Vergleichen, was in der Datenbank steht wortwörtlich)
keine Konsistenzprüfung (Suchindex hat keien Kontrolle über Konsistenz, nicht geeignet für persistente Datenspeicherung)| Transaktionssicherheit (Abbruch der Übertragung usw. hat keine Auswirkung auf Datenstand)
statische Daten | veränderliche Daten
**Retrieval** (suche) | **Storage** (CRUD, Create, Read, Update, Delete)

Schema: mehrere Felder unterschiedlich (beispiel Author und title), Title zum Beispiel nimmt text und string und je nachdem ist Ranking dann am Ende höher. 

Übung 1:
Über Vufind können nur ausgewählte Felder ausgewählt werden, vieles kann gar nicht genau angegeben werden (beispielsweise Publishdate, was über solr geht). 

Logfile für Suche über VuFind ist sehr viel länger. Zudem gibt es dort eine Autovervollständigung, wodurch immer wieder für jeden Buchstaben ein neues Logfile generiert wird. Mit allfield:1983 wurden drei Treffer erzielt (hits=3)und die ^zahlen verdeutlichen die Gewichtung. In der Expertensuche kann man Gewichtung selber bestimmen, in dem man Felder anwählt, wodurch sich Gewichtung selber erübrigt. Es gab Versuche, Personalisierungen durchzuführen, sod ass beispielsweise Kunststudent*innen anderes Ranking erhalten als Maschinenbauer*innen. hat aber nicht wirklich so funktioniert, wie das beispielsweise bei Google klappt.  


Daten aus Vufind löschen: Seeeehr uncool. Habe ich mühsam in 2 Stunden Arbeit eingespeist :-/ 

Übung 2: Der Import mit Koha und doaj hat problemlos geklappt, wie erwartet ging es mit koha und archivesspace nicht. Dies lag daran, dass solr gemäss Schema ein Unique-Key verlangt, welcher bei MARC21 lediglich optional ist. Als Lösung lässt sich händisch eine ID für das Feld 001 vergeben oder über OpenRefine einfügen. Meine Idee wäre ja gewesen, dass Schema.xml abzuändern und den Unique Key zu löschen. Das habe ich versucht, hat aber nicht geklappt, und da ich diesen Lösungsweg trotz Googlesuche nicht gefunden habe, gehe ich davon aus, dass das wohl nicht die eleganteste (oder grundsätzlich erlaubte) Lösung ist. Mit dem vorgeschlagenen Lösungsweg, die Dateien händisch abzuändern, hat das jedoch geklappt. 

Was ich auch noch versucht habe, war, nach [dieser Anleitung](https://lucene.apache.org/solr/7_6_0//solr-core/org/apache/solr/update/processor/UUIDUpdateProcessorFactory.html) automatisch eine ID vergeben zu lassen. Das hat aber leider auch nicht funktioniert, ich vermute, dass mir Plugins fehlen(?) oder dass ich das Teilcodestück einfach am falschen Ort eingefügt habe. 

---

###### Marktüberblick Discovery Systeme

Wir haben schon über Library Systems Report gesprochen, da gibt es nochmachls einen Überblick. Wir haben bis anhin vor allem über integrierte Bibliothekssysteme gesprochen. Discovery Systeme gibt es aber auch. Primo von Exlibris ist Marktführer. In der Schweiz wurde ExLibris Alma und damit das dazu gehörige Discovery-System Primo VE eingeführt. Im Vergleich ist Vufind gar nicht so schlecht, FUnktionalitäten unterscheiden sich nicht gross. Ein weiterer wichtiger Punkt ist die Frage der Daten: In grossen Discoverysystemen wird grosse Datenmengen bereits mitgeliefert. 

Central Index: Nachfolger vo ALeph und Co können E-Ressourcen besser verwalten. Pakete müssen an- und abgeschaltet werden können. Häufig hat man einen grossen Index, also Suchindex, den man mitkauft, damit man in Discovery-Oberfläche oder E-Ressourcen-Management-Tool Zugriff hat auf Info, was es überhaupt gibt. Wenn man Discoverysystem mach, kauft man in der Regel Software und gleichzeitig Index dazu, bei Primo wäre das Primo Central. Discoverysystem ohne Arikelindex bringt im Prinzip nicht mehr sooo viel. 


