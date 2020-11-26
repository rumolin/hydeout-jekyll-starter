---
layout: post
title: Lektion 3 Funktion und Aufbau von Bibliothekssystemen II
excerpt_separator: "<!--more-->"
comments: false
sidebar_link: true
categories: 
tags: 
- koha


---

<img alt="Koha_Screenshot" src="https://github.com/rumolin/lerntagebuch-bain/blob/master/_screenshots/Bild 4.PNG?raw=true" width="70%"/>

---

##### offene Fragen und To Do's

Der Import der Schnellaufnahme in Koha hat problemlos funktioniert. Offene Fragen oder ähnliches gibt es dieses Mal nicht. 

---

#### Namespaces

Als Wiederholung haben wir die Defnition von Namespaces nochmals geklärt: Ein XML Namespace dient dazu, mehrere im selben Dokument verwendete XML-Formate voneinander unterscheien zu können (wenn diese beispielsweise gleichlautende Elementnamen verwenden). Beim Namespace handelt es sich in der Regel um eine URI (Beispiel: http://www.w3.org/1999/xhtml). Fürs Verständnis nützlich war die Aufschlüsselung am Beispiel von Dublin Core:
* Namespace: http://purl.org/dc/elements/1.1/
* Namespace-Kürzel: dc
* Elementname: title
* Qualifizierter Elementname: dc:title

---

##### Koha Übungen

Die Übungen zu Koha haben allesamt gut geklappt. Da die Schnellaufnahme beim ersten Mal nicht funktionierte, habe ich es einfach mit der normalen Aufnahme durchgeführt und das war meiner Meinung nach kein grosser Unterschied. Mit dem Import einer ods-Datei war das dann aber kein Problem. Das System schien sehr einfach und intuitiv, sowohl für die Aufnahme von Büchern aber auch das Ausleihen und Rückbuchen. 

Den neuen SRU-Server einzurichten hat ebenfalls gut geklappt. Unter dem Begriff SRU-Server oder Z39.50 konnte ich mir zu Beginn wenig vorstellen, eine kurze Wikipediarecherche hat ergeben, dass es sich dabei um ein Netzwerkprotkoll handelt, dass im Bibliothekswesen als Standard zur Abfrage von bibliographischen Informationssystemen verwendet wird. [Wikipedia 2020](https://de.wikipedia.org/wiki/Z39.50).

Um nun eine Abfrages des Gesamtkatalogs zu machen, haben wir OAI_PMH genutzt, das *Open Archive Initiative Protcol for Metadata Harvesting*. Gemäss Wikipedia [(2020)](https://de.wikipedia.org/wiki/Open_Archives_Initiative) wurde das Protokoll im Jahr 2000 entwickelt und basiert auf XML und REST. Im Gegensatz zu dem Z39.50-Protokoll dient das OAI-PMH zum Sammeln von Metadaten, die von Data Providern bereitgestellt werden. Als kleinster gemeinsamer Nenner nutzt das Protokoll Dublin Core, dies erklärt auch, weshalb mir die Daten als DC angezeigt wurden und nicht im MARC21-Format, obwohl wir die Daten ja in diesem Format importiert haben. Bei genauerem Nachsehen hat sich aber herausgestellt, dass die Daten auch als MARC21 oder MARCXML angezeigt werden können. So ganz ist mir der Nutzen davon aber ehrlichgesagt noch nicht klar...

---

##### Installation Archives Space 2.8.0

archivesspace starten: archivesspace/archivesspace.sh

Die Installation und das Anmelden hat problemlos geklappt. Hier als Erinnerung für mich die URLs:

* http://localhost:8080/ – the staff interface
* http://localhost:8081/ – the public interface
* http://localhost:8082/ – the OAI-PMH server
* http://localhost:8089/ – the backend
* http://localhost:8090/ – the Solr admin console

Bisauf Solr admin console kann ich mir unter allem ungefähr etwas vorstellen.

über schnittstellen: wir greifen auf Daten zu, auf die wir sonst keinen Zugriff hätten. die nicht in unserem eigenen System liegen. 
XSL = Scriptsprache, um XML zu manipulieren XST-> Transformation
MARCXML ist MARC21, MARC gibt es auch noch, ist Vorläufer von MARC21

crosswalk: gängiger Begriff im IT-Bereich, Information Science, um Konvertierung von Metadatenstandards in anderen zu beschreiben. beinhaltet Regeln, wie Elemente und ggf. Werte zugeordnet oder verändert werden müssen. Nicht einfach, weil Standards erzwingen, dass Entscheidungen getroffen werden müssen, in welches Feld. Nicht immer einfach. So gehen manchmal Inhalte oder Zusammehhänge verloren. Prozess von Zuordnung von Elementen nennt man Mapping. 

ursprünglich für windows entwickelt, damit man unter linux laufen lassen kann, muss man laufzeitumgebung installieren (mono) damit das läuft. schriftenpaket um utf-8 zeichen darstellen zu können ist schriftart noto. 

