---
layout: post
title: Lektion 8 Suchmaschinen und Discovery-Systeme I 
excerpt_separator: "<!--more-->"
comments: false
sidebar_link: true
categories: 
tags: 
- OpenRefine
- GREL
- Metadaten
 

---

<img alt="Mobile home page" src="https://github.com/rumolin/lerntagebuch-bain/blob/master/_screenshots/Bild 9.PNG?raw=true" width="70%"/>

--- 
- evt. SWORD nachtragen DSpace und RSS-Feed
- Import und Export bei ArchivesSpace sei nie verlustfrei ist etwas übertrieben, XML lässt sich technisch überprüfen, ob sauber. In der Praxis ist es aber so, dass es oft nicht verlustfrei ist. Gute Praxis wäre mindestens validieren, damit Form stimmt. 
- Verlustfreie Konvertierung ist möglich, wenn das Zielformat mehr Möglichkeiten bietet als das Ausgangsformat, also z.B. von DC zu MARC21. Es verschwinden dann zumindest keine Daten, es geht nicht verloren, obwohl manchmal Annahmen getroffen werden mussten. 

##### Nachtrag von OpenRefine

Validierung XML: MARCXML-Schema definiert Regeln. Wenn man saubere XML-Daten produzieren möchte, muss das abgeglichen werden. XSD-Format um Schema zu definieren für XML-Daten. Was soll wann vor kommen und wie soll es aussehen? Schema kann Form vorgeben und validieren, aber auch Inhalte im Feld vorgeben. Prüfung der Form soll mindestens sichergestellt werden, wenn man XML-Dateien geschrieben hat. Validierung als wichtige Grundlage. 

Template exportieren, abspeichern und dann im Skript verschiedene Möglichkeiten der Validierung. 

````
wget https://www.loc.gov/standards/marcxml/schema/MARC21slim.xsd
xmllint *.xml --noout --schema MARC21slim.xsd
````

---

###### XML-Deklaration

zusätzliche Textzeile am Anfang der XML-Datei: <?xml version="1.0" encoding="utf-8" standalone="yes"?> -> Software erhält Hinweis, dass es XML ist beim Öffnen. Software muss nicht erst ganze Datei einlesen und prüfen sondern bekommt beim Lesen der 1. Zeile Hinweis, dass es sich um XML handelt. Bei grossen Dateien vor allem hilfreich. 

Wir sagen: Es ist XML und wir sagen, welche Version (wir haben 1.0 und 1.1), encoding meint, in welcher Zeichencodierung wir das gespeichert haben. Sonderzeichen Umlaute u.ä. werden im Zeichensatz direkt abgebildet. Standalone klärt ob Dokumenttypdefinition in der Datei selbst anbeiliegt. Standalone yes = Dokumenttypdefinition ist integriert, no heisst es gibt eine, allerdings muss die noch abgefragt werden. Weglassen heisst, es gilt Standarddokumenttypdefinition von XML. Wenn wir Standalone angeben, muss Versionangabe beiliegen, encoding ist gute Praxis. Standalone kommt in Praxis nicht häufig vor. Reihenfolge der Attribute ist festgelegt und kann nicht geändert werden. 

Offene Frage: was fällt unter DOkumenttypdeklaration? XSD und DTD? -> klären! 

Es gibt natürlich alternative Software zu OpenRefine, generell gilt, dass Software anhand des Anwendungsfalls gewählt werden sollte. In der PRaxis wählt man das, was man schon gut kann, dafür wird es dann manchmal sehr umständlich. Catmandu und Metafacture ist mehr programmier-lastig, OpenRefine hat halt wunderbare graphische Oberläche. Catmandu kann auch RDF. 

###### JSON-APIs

Im normalen Internet haben wir meistens mit Programmierschnittstellen zu tun, die JSON ausliefern. Es gibt auch immer mehr bibliothekarische Schnittstellen, die so arbeiten. JSON lässt sich halt gut parsen und auswerten. Finde JSON sowieso toll. Zum Beispiel über lobid lässt sich alles als JSON runterladen. Maschinell kann man das gut auswerten und verarbeiten. 
weniger Bibliotheks- und Archivspezifisch sondern generell IT-Praxis. Kennen wir aus dem Modul DGUI. 

###### LIDO

Lido: **Lightweight** Information Describing Objects basiert auf CIDOC Conceptual Reference Model. XML-Standard vor allem für Kulturobjekten. In Museen stark verbreitet. Ist etwas anders geartet als alle anderen Metadatenstandards. Vereinfachte XML-Version von CIDOC-CRM.

CIDOC ist Vereinigung von Museen und deren Experten. CIDOC-CRM ist sehr abstrakt, nicht für direkte Anwendung, eher Modell für Standards und Metadatenableitung. Definiert Konzepte und Relationen, die dann verwendet werden können. Konzepte sind Entitäten beispielsweise, Dinge die ich beschreiben kann und Relationen wären Beziehungen, die Entitäten haben können. Alles wird mit URIs identifiziert. LIDO nutzt Modell von CIDOc-CRM und verwendet Terminologie, die daran orientiert ist. LIDO entspricht Linked Open Data-Paradigma. 

LIDO nutzt dieses Modell von CIDOC CRM um Beschreibungssprache zu erstellen. LIDO folgt also dem Linked Open Data Paradigma, da es für alles URIs gibt. global gültige Identifier. Erlaubt Querverweise zu anderen Institutionen, OBjekte uw. 
struktur ist recht speziell, enn Lido ist ereigniszentriert. Bisher hatten wir nur mit dokumentzentrierten Standards zu tun. Da ich bei Entitäten und Relationen automatisch an Datenbankmodelle denke, ist es für mich eine Challenge, mir das für Ereignisse vorzustellen. 

Objekte können dann Ereignis teilen, wodurch sie miteinander in Verbindung stehen. Werkzeug und Werk können so in Beziehung stehen, da sie durch Ereignis miteinander verbunden sind. Nachteil ist jedoch, dass die Überführung in andere Standards beinahe unmöglich ist. kaum verlustfrei möglich, infos können zwar übernommen werden, allerdings geht Beziehungsgeflecht verloren. 

LIDO Struktur: 
- deskriptive Metadaten: 
    - Identifikation (Titel/Name, Beschreibung, Masse etc.)
    - Klassifikation (Art, Gattung, Form usw.) -> müssen CIDOC CRM entsprechen. 
    - *Ereignisse* (Herstellung, Bearbeitung, Besitzwechsel, Restaurierung etc.)
    - Relationen (Objekte, Personen, Orte usw.)
- administrative Metadaten:
    - Rechte (Objekt, Datensatz, Nutzung, Verbreitung...)
    - Datensatz (Identifikation, Urheber*in...)
    - Resssourcen (Digitalisat, Nachweis...)

Unterschied Display und Index-Elements: wie sollen Daten auf Oberfläche aussehen? für jede Angabe die man macht, kann man unterscheiden zwischen technischer, interner Form und Anzeigeform. 

Bisher eher als Austauschformat, ansonsten arbeiten Museen immer noch eher dokumentzentriert. 

#### Suchmaschinen und Discovery-Systeme

###### VuFind Installation

VuFind gibt es schon recht lange, Entwicklung wird aber vorallem von einigen wenigen vorangetrieben. Bei OpenHub kann man generell Überblick finden -> anschauen! Vufind ist eine php-Software, die eine Datenbank (MariaDB) und für die Suche solR verwendet. Müssen wir also starten, während Datenbank im Hintergrund bereits läuft. 

Linux-Konvention: Wenn man Datei starten möchte innerhalb des Verzeichnisses, in de man sich befindet, muss Datei mit ./ vorgängig aufgerufen werden. 

Die Installation war eine schwere Geburt. Beim Installationstermin musste ich leider früher weg und habe die Installation deshalb dann nicht beendet, wohl aber angefangen. Als ich das dann später nachholen wollte, scheiterte ich an mehreren Problemen:

- Beim Start von solr hiess es, der Port sei schon besetzt. Kein Problem, eine kurze Google-Suche später wusste ich, was zu tun ist: ```` sudo kill [process-pid]  ```` Danach konnte solr normal gestartet werden

<img alt="Mobile home page" src="https://github.com/rumolin/lerntagebuch-bain/blob/master/_screenshots/Bild 10.PNG?raw=true" width="50%"/>

- Nächstes Problem: Error 404 beim Aufrufen von http://localhost/vufind/Install/Home. Alles klar, also nochmals von vorne alles neu installiert. Zwischenzeitlich war ich unsicher, ob tatsächlich Java 8 installiert war, deshalb habe ich das überprüft mit ```` Java -version ````. So ganz schlau geworden daraus bin ich nicht, aber in der Versionsnummer war eine 8 enthalten, deshalb dachte ich, dass das schon passen wird. Auch nach der Neuinstallation trat das Problem auf, dass solr nicht gestartet werden konnte, aber das war ja inzwischen kein Hindernis mehr. Und siehe da, die Seite liess sich mit der Neuinstallation tatsächlich aufrufen. Problem gelöst. 
- Die nächste (und mühsamste) Stolperfalle war dann der Import der Dateien im MARC21-Format. Dies liess sich nicht bewerkstelligen, ganz egal, wie ich das versucht habe. Am Ende dämmerte es mir dann doch: Da war doch was mit einem Befehl, der in der ersten Version der Anleitung nicht richtig ausgeführt worden war... Doch wie reparieren? Ich habe dann mal bei meinen Kolleginnen und Kollegen in den Lerntagebüchern gespickt, um zu schauen, wie die das gelöst haben und natürlich wurde ich bei [Gaby Leuenberger](https://regrebneuel.github.io/bain-log/2020-11-27/OpenRefine-reloaded) fündig:

```` sudo apt-get update ````
```` sudo apt-get upgrade ````
Dann Java 8 installieren:
```` sudo apt install -y openjdk-8-jdk ````

Alle Schritte gemäss [Anleitung](https://pad.gwdg.de/ywogyRNTQ_CTg9PvrQywsQ?both) bis und mit dem Starten von Solr nochmals durchgeführt und wow, schon läufts wie geschmiert und ohne Probleme. Alle Konfigurationsschritte auf (http://localhost/vufind/Install/Home) konnte ich mir sparen, da ich das schon durchgeführt hatte. Nun klappte auch der Import der Beispieldaten problemlos: 

<img alt="Mobile home page" src="https://github.com/rumolin/lerntagebuch-bain/blob/master/_screenshots/Bild 11.PNG?raw=true" width="70%"/>