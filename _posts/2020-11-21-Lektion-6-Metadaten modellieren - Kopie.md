---
layout: post
title: Lektion 6 Metadaten modellieren und Schnittstellen nutzen I
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

##### offene Fragen aus dem letzten Mal

---

Daemon: wie kann ich Prozess im Hintergrund laufen lassen? Link auf Folie zu ausführlicher Erklärung. Open Swiss knife: open space = open stage / mic. usw. blabalbal

archivesspace und dspace waren Thema. kann mich nur schlecht erinnern....

--- 

solr: volltextsuchmaschine, weit verbreitet, netflix nutzt auch solr. keine spezifische bibliotheks- oder archivsoftware, sondern internetstandard. 
apache solr als alternative zu solr? elasticsearch und solr komisch... 

Schnittstellen: es gibt reihe von übertragungsprtokollen, 3 sind wichtig: Z39,5 von loc mit anderen zusammen, moderner ist sru, funktioniert ähnlich auch von loc. und oai-pmh gibt es auch noch, was von open archives initiative spezifiziert wurde. 
zertifikat für repositorien, (für gute mit bestimmten erfüllten Kriterien) anhand von Zertifikat kann auf gute Praxis geschlossen werden. Auch Datacite ist als Empfehlung drin. Initiative DINI-Zertifikat. 
resourceSync? 

* wir ernten über oai-pmh-schnittstellen angebotene Daten
dazu nutzen wir vufindharvest, ein oai harvester aus dem vuFind-Projekt. 
sicherstellen, dass oai-pmh endpoints für Koha, archivesspace und Dspace überhaupt verfügbar sind. 








