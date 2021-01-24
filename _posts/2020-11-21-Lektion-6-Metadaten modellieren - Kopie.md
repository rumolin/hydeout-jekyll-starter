---
layout: post
title: Lektion 6 Metadaten modellieren und Schnittstellen nutzen I
excerpt_separator: "<!--more-->"
comments: false
sidebar_link: true
categories: 
- Übungen
- Metadaten
tags: 
- oai-pmh
- sru
- Z39.50
- Harvesting
- Crosswalks
 

---

<img alt="Crosswalk" src="https://github.com/rumolin/lerntagebuch-bain/blob/master/_screenshots/Bild 7.png?raw=true" width="70%"/>

---

Dieses Schaubild zeigt den Zusammenhang aller Programme, Tools und Software, die wir bereits in diesem Modul kennegelernt haben. Es umfasst Koha (Bibliothekssoftware), ArchivesSpace (Archivsoftware) sowie DSpace als Software für Open Access und Open Data. Über die OAI-PMH-Schnittstelle lassen sich jeweils Daten abrufen, das machen wir mit VuFindHarvest (OAI-Harvester). 

<!--more-->

Diese Daten liegen dann je nach Software entweder als MARC21-XML (Koha), EAD (ArchivesSpace) oder Dublin Core (DSpace) vor. Alle diese Formate können wir mit marcEdit behandeln und einen Crosswalk durchführen, so dass wir schliesslich bei MARC21-XML landen. 

Diesen Schritt behandeln wir in diesem Unterrichtsblock, in den nächsten Blöcken werden wir mittels VuFind auf Basis von Solr noch Discovery-Systeme kennenlernen. 

---
 
#### Schnittstellen 

Es gibt zahlreiche Übertragungsprotokolle im Bibliotheks- und Archivbereich. Drei sind besonders verbreitet:

- **Z39.50** von der Library of Congress, haben wir bereits im Rahmen von Koha benutzt. Ist sehr alt aber tatsächlich immer noch im Einsatz. Es Ergänzung wird jedoch oft SRU angeboten
- **SRU** Search/Retrieve via URL (ebenfalls Library of Congress)
- **OAI-PMH** Open Archives Initiative Protocol for Metadata Haresting (Open Archives Initiative)

Z39.50 und SRU eigenen sich besonders für Live-Abfragen, wohingegen OAI-PMH vor allem auf grössere Datenbezüge abzielt. SRU und OAI-PMH lassen sich über die URL abfragen, während Z39.50 eine zusätzliche Software benötigt. 

---

##### Vorgehen Harvesting

Metadaten werden über OAI-PMH "geernet", also über die Schnittstelle. Wir verwenden VuFindHarvest, ein OAI-Harvester aus dem VuFind-Projekt. Es kann nur OAI-PMH abfragen. 

Vorgehen: 
1. sicherstellen, dass OAI-PMH Endpoints verfügbar sind für alle Programme
2. mit dem Tool die Daten abrufen und als XML auf der Festplatte speichern 


OAI-PMH Endpoints: Da es bei mir langsam etwas unübersichtlich wurde, welche Angaben man wo wofür und warum braucht, habe ich ein Cheat-Sheet erstellt: (https://github.com/rumolin/lerntagebuch-bain/blob/master/Cheat%20Sheet%20BAIN.docx) Dort sind auch alle OAI-PMH Endpoints und eine Kurzanleitung zur jeweiligen Bedienung aufgeführt. Da ich aber darauf spekuliere, dass wir auch nach Beendigung des Kurses Zugriff auf die jeweiligen Anleitungen haben, sind die Befehle jeweils nicht so detailliert aufgeführt. 

Unterschied Export / Abfrage OAI-Schnittstelle: OAI liefert Daten anders aus, als wenn man Daten beispielsweise aus DSpace exportiert. OAI-Schnittstelle hat noch Infos drumherum. Deshalb andere Darstellung der Daten. Muss beim Experimentieren bedenkt werden!

---

###### Befehle für Harvesting:

- Koha:
    ````
    $ mkdir nv_koha
    cd ~/vufindharvest-4.0.1
    php bin/harvest_oai.php --url=http://bibliothek.meine-schule.org/cgi-bin/koha/oai.pl --metadataPrefix=marcxml nv_koha ````

- ArchivesSpace:
    ````
     $ mkdir nv_archivesspace
     cd ~/vufindharvest-4.0.1
    php bin/harvest_oai.php --url=http://localhost:8082/ --metadataPrefix=oai_ead nv_archivesspace ````

- DSpace
    ````
    $ mkdir nv_dspace
    php bin/harvest_oai.php --url=http://demo.dspace.org/oai/request --metadataPrefix=oai_dc --set=com_10673_1 nv_dspace ````

Die Übung hat noch Korrektur der ArchivesSpace-Dateien problemlos geklappt. Ich habe für alles je ein neues Verzeichnis erstellt und die Dateien dort abgespeichert. 

---

##### Crosswalks

Crosswalks: Begriff für Konvertierung von einem Metadatenstandard in einen anderen. Der "Crosswalk" beinhaltet Regeln, wie Elemente und Werte zugeordnet/verändert werden müssen (Mapping). Im Idealfall ist ein Crosswalk verlustfrei, meistens ist aber keine 1:1-Zuordnung möglich.

Wir nutzen MarcEdit für die Konvertierung von EAD und Dublin Core nach Marc21-XML. Das ist eine kostenlose Software (allerdings nicht Open Source). 

Auch diese Übung hat nach dem Korrigieren der Voreinstellungen geklappt, wenn auch bei EAD über Umweg von EAD zu Marc zu Marc21xml. 

