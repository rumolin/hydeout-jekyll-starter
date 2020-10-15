---
layout: post
title: Lektion 4 Funktion und Aufbau von Archivsystemen
excerpt_separator: "<!--more-->"
comments: false
sidebar_link: true
categories: 
tags: 
- archivesspace
- ISAD(G)
- EAD
- RIC
 

---

<img alt="Mobile home page" src="https://github.com/rumolin/lerntagebuch-bain/blob/master/_screenshots/Bild 5.PNG?raw=true" width="70%"/>

---

##### offene Fragen und To Do's

---

Während der Stunde habe ich bei der Übung mit Archivesspaces eine Fehlermeldung unter dem public Interface erhalten. Gaby hat sich zum Glück meiner Überforderung angenommen und mir erklärt, wie ich mit dem folgenden Befehl meine log-files auslesen kann:

grep -B 100 -A 100 "WARNING: ERROR" archivesspace.out

Dieser musste im Verzeichnis archivesspache/logs ausgeführt werden, wo sich die Logfiles befinden. grep ist ein Programm, das zur Suche und Filterung von bestimmten Zeichenketten dient (in diesem Fall "WARNING: ERROR") in der Datei archivesspace.out. -B und -A 100 wirft die 100 Zeilen vor und nach dem gesuchten String aus. Der Text aus dem Logfile habe ich an die Dozierenden ermittelt und die haben dann zum Glück das Problem eruieren können: Komischerweise hatten Gaby und ich beide Java 11 statt 8 aktiviert. Dies hat mit archivesspace offenbar zu Problemen geführt. Mit sudo update-alternatives --config java konnte das von Herr Lohmeier zum Glück behoben werden und das public interface funktioniert nun einwandfrei. 
Nun gilt es, Accession und Ressources noch zu vervollständigen.

Ebenfalls wurde noch geklärt, weshalb wir OAI-PMH nutzen. Über diese Schnittstelle können Daten zur Weiterverarbeitung abgerufen werden und es nützt der Aggregation für Verbundsrecherchen (wohl wie bei Nebis)...

#### ISAD(G)
 
---

Um eine ungefähre Ahnung davon zu kriegen, wie Archive arbeiten, war es wichtig, sich in Erinnerung zu rufen, dass Archive anders arbeiten als medienzentrierte Bibliothekssysteme. Bei Archiven ist die Pertinenz zentral. ISAD(G) wurde dabei als Standard für Archive entwickelt und entstand aus der starken Orientierung an den bis dahin genutzten Findbüchern. Die analoge Arbeitsweise sollte in der Software abgebildet werden, dies hat offenbar zu Eigenheiten geführt, die man heute praktischer lösen könnte (und wohl auch würde). ISAD(G) ist dabei die Abkürzung für *International Standard Archival Description (General)*. 

ISAD(G) hat 26 Verzeichnungselemente in 7 Informationsbereichen (Identifikation, Kontext, Inhalt und innere Ordnung, Zugangs- und Benutzungsbedingungen, Sachverwandte Unterlagen, Anmerkungen und Kontrolle) Von besonderer Bedeutung sind die 6 Pflichtfelder Signatur, Titel, Provenienz, Entstehungszeitraum, Umfang und Verzeichnisstufe. Wie gesagt: Archive arbeiten so, dass der Entstehungszusammenhang (Provenienz) eine besondere Bedeutung hat. Deshalb wird nicht wirklich das Medium beschrieben, sondern eher der/die Urheber\*in, respektive Aktenbilder\*in. 

##### Grenzen von ISAD(G) 

Folgende Probleme zeigen sich mit ISAD(G):
* Ein einzelner Datensatz ist eventuell nur im Kontext zu verstehen
* Die Tektonik ist eindimensional (Mehrfachzuordnungen sind nicht möglich)
* Der Standard enthält keine Vorgaben zur Digitalisierung oder zur digitalen Langzeitarchivierung (Gemäss Dozierenden ist dies ja aber eigentlich ein Glücksfall, da Archive und Bibliotheken so gezwungenermassen näher zusammenrücken müssen, was die Digitalisierung betrifft...)

In diesem Zusammenhang kommt dann RIC, *RecordsInContext* ins Spiel. An diesem Standard wir gearbeitet, weil ISAD(G) genau die oben beschreibenen Defizite aufweist. 

##### Normdaten mit ISAD(G) 

Um Normdateien verzeichnen zu können, kam dann später ISAAR(CPF) als ergänzender Standard ins Spiel. Wird in der Praxis jedoch nur selten verwendet. 

##### EAD

Das *Encoded Archival Description* ist ein XML-Standard. Da wir später praktisch damit arbeiten werden, wird dies hier (wie in den Folien) nicht weiter ausgeführt. 

##### aktuelle Entwicklungen

Umstieg von ISAD(G) auf RiC (Systemwechsel usw.) wird grosse Migrationsprojekte nach sich ziehen, da sich grunsätzliche Verzeichnungsart ändern wird. Immer mehr Volltexte werden generiert durch die Möglichkeiten von der Handschrifterkennung und die automatisierte Anrecherung von Volltexten durch Named Entity Recognition.  

#### Übungen zu Archivkatalogen

--- 
Hier eine ganz kurze Zusammenfassung aus der Übung: die beiden betrachteten Archivsysteme der ETH und im Online Archivkatalog des Staatsarchivs BS ergab folgende Unterschiede: Grundsätzlich ist das Archivsystem der ETH neuer, jedoch unübersichtlicher als das System von BS. Dies scheint etwas unglücklich... Ansonsten sind die Angaben ungefähr ähnlich, auch wenn sie im ETH-Katalog jeweils etwas gesucht werden müssen. Der Vergleich mit einem Bibliothekskatalog finde ich persönlich recht schwierig. Intuitiv würde ich sagen, dass der Bibliothekskatalog (zumindest in einer Freihandbibliothek) ganz klar aufzeigt, wie und wo an das Medium zu kommen ist. Das ist beim Archivskatalog nicht der Fall. (Entfernte) Ähnlichkeiten sehe ich aber zwischen Schlagwortketten im Bibliothekskatalog und der Verzeichnisstufen im Archivsystem. 


#### archivesspace

---

archivesspace ist ein Open-Source-Archivinformationssystem mit (ich denke beachtlichen) 400 zahlenden Mitgliedern. 
Bei der Übung haben wir frei nach Gefühl einige Archivobjekte aufgenommen, ohne gross auf Regeln oder Abläufe zu achten. Ich war da ehrlich gesagt etwas verloren, vor allem auch, weil mein Public Interface nicht funktionieren wollte. Zuhause habe ich dann in aller Ruhe nochmals diese (Kurzanleitung)[https://guides.nyu.edu/ld.php?content_id=23198351] studiert und nachher war einiges klarer. Ich habe in der Nachbereitung dann folgende Ressource nach diesem Prinzip aufgenommen: 

[to be continued...]
Als besonderes Learning ist folgendes zu verbuchen: Bei der Accession wird ein Datensatz zur Erwerbung angelegt. Daraus dann die konkreten Ressourcen. 






