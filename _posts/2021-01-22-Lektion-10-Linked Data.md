---
layout: post
title: Lektion 10 Linked Data
excerpt_separator: "<!--more-->"
comments: false
sidebar_link: true
categories: 
tags: 
- BIBFRAME
- MARC
- RDA
- FRBR
- Metadaten
- Metadatenstandards

---

<img alt="Mobile home page" src="https://github.com/rumolin/lerntagebuch-bain/blob/master/_screenshots/Bild 9.PNG?raw=true" width="70%"/>

--- 

#### Bibframe und Records in Context

Als Buchhändlerin, die zwar in einer Bibliothek arbeitet, jedoch nichts mit Katalogisieren zu tun hat (und das definitiv auch nicht möchte) sind die verschiedenen Metadatenstandards und -formate für mich teilweise etwas verwirrend. Hier deshalb nochmals die Zusammenhänge kurz erklärt.

<!--more-->

---

##### Zusammenhang MARC, RDA und FRBR: 

**MARC** (machine-Readable-Cataloging) ist ein Datenformat, das dazu dient, bibliografische Daten zu erfassen, zu speichern und auszutauschen. MARC21 ist die weltweit am häufigsten verwendete Version ([DNB, 2020](dng.de/DE/Professionell/Standardisierung/standards_node.html)). MarcXML ist eine inhaltlich identlische XML-Version dieses Datenformats (ebd.).

**RDA** (Resource Descritption and Access) ist ein internationaler Katalogisierungsstandard und bibliothekarisches Regelwerk zur Katalogisierung. Der Text des Regelwerks wird als "RDA Toolkit" publiziert ([Wikipedia, 2020](https://de.wikipedia.org/wiki/Resource_Description_and_Access)). RDA basiert auf FRBR.

**FRBR** (Functional Requirements for Bibliographic Records) ist das Datenmodell, auf dem RDA basiert. Es unterscheidet Werk (Idee von *Wer die Nachtigall stört*, Expression (deutsche Ausgabe und englische Ausgabe des Textes), Manifestation (Auflage 1 der deutschen Ausgabe, ebook der deutschen Ausgabe) und Item (dieses eine Buch, das in der Bibliothek XY ausgeliehen werden kann) ([Wikipedia, 2020](https://de.wikipedia.org/wiki/Functional_Requirements_for_Bibliographic_Records#:~:text=Die%20FRBR%20gehen%20auf%20eine,Description%20and%20Access%20(RDA).)). 


**BIBFRAME** ist nun nicht nur der Name vom *neuen* Format, sondern auch von Initative der Library of Congress. BIBFRAME war als Nachfolger vom antiquierten MARC21 gedacht, das Strukturen von "neuen" Daten und Semantic Web nicht mehr genügen abbilden konnte durch die tabellarische Form. Seit 2016 gibt es BIBFRAME 2.0. 

BIBFRAME basiert auf Functional Requirements for Bibliographic Records (FRBR) als Konzept sowie Resource Description and Access (RDA) als Regelwerk, setzt aber beides nicht vollständig um, was auch häufig kritisiert wird. BIBFRAME besteht aus *Model* und *Vocabulary*, das Datenmodell unterscheidet zwischen Work, Instance und Item (im Gegensatz zu FRBR also etwas vereinfacht) und hat die Entitäten Agent, Subject und Event. 

Das Vokabular definiert Konzepte und deren Eigenschaften zur Beschreibung der Entitäten des Datenmodells. BIBFRAME folgt dem Linked Data-Paradigma, alles hat also eindeutige URIs und Identifier. 

Work | Idee von Werk an sich (analog zu Werk von FRBR) 
Instance | Expression und Manifestation (das finde ich sowieso schwierig, diesen Unterschied in FRBR zu fassen, das zusammenzunehmen erscheint mir sinnvoll) 
Item | analog Item bei FRBR

Agent | beteiligte Personen, die zur Entstehung des Werks beigetragen haben. 
Subjects | alles, was Werk behandelt, können auch Personen und Körperschaften sein aber auch Ereignisse oder Themen usw. 
Events | etwas, was das Werk wiedergibt, beispielsweise Aufzeichnung eines Theaterstücks, Theater wäre das Event 

Entitäten sind nicht zwingend logischerweise, nur wenn sie zutreffen. 

---

#### Records in Context

basiert auch auf Linked-Data-Paradigma. Soll aber neue und mehrfache Beziehungen zwischen Entitaäten ermöglichen (was momentan mit ISAD(G) nicht funktioniert!) Es handelt sich dabei um einen Verzeichnungsstandard, der die vier bestehenden Standards ISAD(G), ISAAR(CPF), ISDF und ISDIAH harmonisiert, integriert und weiterentwickelt ([Wikipedia, 2020](https://de.wikipedia.org/wiki/Records_in_Contexts)). Ganz ehrlich, ich werde wohl mit Archivthemen generell und Records in Context im Besonderen nicht mehr warm. Deshalb verzichte ich hier auf weitere Ausführungen, obwohl die Länge des Artikels eher knapp bemessen ist. Da ich aber an anderen Stellen ohnehin viel zu viel geschrieben habe, hoffe ich, dass das so passt. 




 



