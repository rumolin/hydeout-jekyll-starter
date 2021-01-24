---
layout: post
title: Lektion 3 Funktion und Aufbau von Bibliothekssystemen II
excerpt_separator: "<!--more-->"
comments: false
sidebar_link: true
categories: 
- Tools
- Übungen
tags: 
- koha
- archivesspace


---

<img alt="Koha_Screenshot" src="https://github.com/rumolin/lerntagebuch-bain/blob/master/_screenshots/Bild 4.PNG?raw=true" width="70%"/>

---

#### offene Fragen und To Do's aus der letzten Stunde

Der Import der Schnellaufnahme in Koha hat problemlos funktioniert. Offene Fragen oder ähnliches gibt es dieses Mal nicht. 

<!--more-->

---

#### Namespaces

Als Wiederholung haben wir die Defnition von Namespaces nochmals geklärt: Ein XML Namespace dient dazu, mehrere im selben Dokument verwendete XML-Formate voneinander unterscheien zu können (wenn diese beispielsweise gleichlautende Elementnamen verwenden). Beim Namespace handelt es sich in der Regel um eine URI (Beispiel: [http://www.w3.org/1999/xhtml](http://www.w3.org/1999/xhtml)). Fürs Verständnis nützlich war die Aufschlüsselung am Beispiel von Dublin Core:
* Namespace: http://purl.org/dc/elements/1.1/
* Namespace-Kürzel: dc
* Elementname: title
* Qualifizierter Elementname: dc:title

---

#### Koha Übungen

Die Übungen zu Koha haben allesamt gut geklappt. Da die Schnellaufnahme beim ersten Mal nicht funktionierte, habe ich es einfach mit der normalen Aufnahme durchgeführt und das war meiner Meinung nach kein grosser Unterschied. Mit dem Import einer ods-Datei war das dann aber kein Problem. Das System schien sehr einfach und intuitiv, sowohl für die Aufnahme von Büchern aber auch das Ausleihen und Rückbuchen. 

Den neuen SRU-Server einzurichten hat ebenfalls gut geklappt. Unter dem Begriff SRU-Server oder Z39.50 konnte ich mir zu Beginn wenig vorstellen, eine kurze Wikipediarecherche hat ergeben, dass es sich dabei um ein Netzwerkprotkoll handelt, dass im Bibliothekswesen als Standard zur Abfrage von bibliographischen Informationssystemen verwendet wird. [Wikipedia 2020](https://de.wikipedia.org/wiki/Z39.50).

Um nun eine Abfrages des Gesamtkatalogs zu machen, haben wir OAI_PMH genutzt, das *Open Archive Initiative Protcol for Metadata Harvesting*. Gemäss Wikipedia [(2020)](https://de.wikipedia.org/wiki/Open_Archives_Initiative) wurde das Protokoll im Jahr 2000 entwickelt und basiert auf XML und REST. Im Gegensatz zu dem Z39.50-Protokoll dient das OAI-PMH zum Sammeln von Metadaten, die von Data Providern bereitgestellt werden. Als kleinster gemeinsamer Nenner nutzt das Protokoll Dublin Core, dies erklärt auch, weshalb mir die Daten als DC angezeigt wurden und nicht im MARC21-Format, obwohl wir die Daten ja in diesem Format importiert haben. Bei genauerem Nachsehen hat sich aber herausgestellt, dass die Daten auch als MARC21 oder MARCXML angezeigt werden können. So ganz ist mir der Nutzen davon aber ehrlichgesagt noch nicht klar...

---

#### Installation ArchivesSpace 2.8.0

Obwohl die Installationen sowohl für Koha aber auch für ArchivesSpace problemlos geklappt haben, würde ich gerne die Befehle dafür mal etwas genauer anschauen:

```bash
    sudo apt update
    sudo apt install openjdk-8-jre-headless
```

Der Befehl `sudo` kann Programmaufrufen vorangestellt werden. Er macht es möglich, dass Benutzer\*innen das Programm im Namen und mit Rechten ovn anderen Benutzer\*innen ausführen können, beispielsweise um Aufgaben auszuführen, die eigentlich Administrator\*innen vorbehalten sind (beispielsweise Programm installieren, wie in diesem Fall). sudo ist ein esentieller Bestandteil jeder Ubuntu-Installation ([Ubunut-Wiki, 2020](https://wiki.ubuntuusers.de/sudo/))

<img alt="Koha_Screenshot" src="https://github.com/rumolin/lerntagebuch-bain/blob/master/_screenshots/Bild 16.png?raw=true" width="70%"/>[^1]

<small>Quelle: [https://wiki.ubuntuusers.de/sudo/](https://wiki.ubuntuusers.de/sudo/)</small>

`apt` steht für Advanced Packaging Tool und ist ein Paketmangement-System, das es vereinfacht, Programmpakete zu suchen, zu installieren oder auch das ganze System auf den neusten Stand zu bringen. `apt-get` (das teilweise auch benutzt wird) ist eine Weiterentwicklung davon, die beispielsweise grafische Elemente wie der farbige Fortschrittsbalken bietet ([ITrig, 2020](https://itrig.de/index.php?/archives/2316-apt-vs.-apt-get-Was-ist-der-Unterschied.html)). 

Mit `update`installieren wir aber nicht wirklich ein neues Update, vielmehr werden die eingetragenen Paketquellen in /etc/apt/sources.list und /etc/apt/sources.list.d/ neu eingelesen. ([Ubuntu-Wiki, 2020](https://wiki.ubuntuusers.de/apt/apt-get/#apt-get-update)) quasi als Vorbereitung für den nachfolgenden Befehl. 

Mit `sudo apt install openjdk-8-jre-headless` installieren wir Java 8, allerdings die Java-Laufzeitumgebung OHNE grafische Oberfläche ([Debian, 2020](https://packages.debian.org/de/sid/openjdk-8-jre-headless)). 

Nun können wir das Zip-Archiv zu Archivesspace herunterladen und entpacken:

```bash
    wget https://github.com/archivesspace/archivesspace/releases/download/v2.8.0/archivesspace-v2.8.0.zip
    unzip -q archivesspace-v2.8.0.zip
```

Mit `wget` werden direkt aus dem Terminal Dateien vom https-Server heruntergelanden, in diesem Fall der Ornder archivesspace-v2.8.0.zip ([Ubuntu-Wiki, 2020](https://wiki.ubuntuusers.de/wget/)). Das -q steht dabei für qiet und sorgt dafür, dass wget keine Informationen auf der Konsole ausgibt. Dann wird die Datei archivesspace-v2.8.0.zip im gleichen Verzeichnis entzippt. 

Nun muss ArchivesSpace lediglich noch gestartet werden:

```bash
    archivesspace/archivesspace.sh
```

Die Installation und das Anmelden hat problemlos geklappt. Hier als Erinnerung für mich die URLs:

* http://localhost:8080/ – the staff interface
* http://localhost:8081/ – the public interface
* http://localhost:8082/ – the OAI-PMH server
* http://localhost:8089/ – the backend
* http://localhost:8090/ – the Solr admin console

Bis auf Solr admin console kann ich mir unter allem ungefähr etwas vorstellen.

Über Schnittstellen: wir greifen auf Daten zu, auf die wir sonst keinen Zugriff hätten, weil sie nicht innerhalb unseres eigenen Systems liegen. 

XSL = Scriptsprache, um XML zu manipulieren XST-> Transformation

MARCXML ist identische XML-Version MARC21, MARC gibt es auch noch, ist Vorläufer von MARC21. Mehr dazu [in diesem Blogpost](https://rumolin.github.io/lerntagebuch-bain/2021/01/22/Lektion-10-Linked-Data.html)

Crosswalk: gängiger Begriff im IT-Bereich, um Konvertierung von Metadatenstandards in anderen zu beschreiben. Crosswalks beinhalten Regeln, wie Elemente und gegebenenfalls Werte zugeordnet oder verändert werden müssen. Dies ist nicht so einfach, weil Standards erzwingen, dass Entscheidungen getroffen werden müssen, in welches Feld was vermerkt wird. So gehen manchmal Inhalte oder Zusammehhänge verloren. Der Prozess von der Zuordnung der Elemente nennt man Mapping. 

ArchivesSpace wurde ursprünglich für Windows entwickelt, damit man das unter Linux laufen lassen kann, muss man Laufzeitumgebung installieren (mono).

---
[^1]: Mein Freund beginnt im April eine IT-Weiterbildung. Mal schauen, wie lange es dauert, bis ich dann wirklich ein Sandwich kriege :D
