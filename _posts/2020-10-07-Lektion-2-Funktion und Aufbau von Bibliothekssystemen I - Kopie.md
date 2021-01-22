---
layout: post
title: Lektion 2 Funktion und Aufbau von Bibliothekssystemen I
excerpt_separator: "<!--more-->"
comments: false
sidebar_link: true
categories: 
tags: 
- koha
- github pages
- MARC21
- Dublin Core

---

<img alt="bundle jekyll" src="https://github.com/rumolin/lerntagebuch-bain/blob/master/_screenshots/Bild 2.PNG?raw=true" width="70%"/>

---

#### offene Fragen aus der letzten Stunde


Mit der bereitgestellten [Anleitung](https://docs.github.com/en/github/working-with-github-pages/testing-your-github-pages-site-locally-with-jekyll) im Skript konnte ich den Static-Site-Generator Jekyll lokal installieren. Damit werden mir Änderungen lokal angezeigt und ich muss erst committen, sobald ich weiss, dass die Änderungen funktionieren. 

<!--more-->

Damit sollte ich mir einige künftige Commits ersparen. Zudem aktualisiert sich mein Lernblog lokal sehr viel schneller als bei Github Pages, was ein zusätzlicher Vorteil ist. 

Leider hatte ich noch keine Gelegenheit, meine anderen offenen To Do's aus dem letzten Block abzuarbeiten:
  *	Auf der Hauptseite soll nicht mehr der ganze Blogartikel sichtbar sein, sondern nur noch eine Vorschau (inklusive Beitragsbild) 
  *	About, Thema 1, Thema 2 und Post Formats (Menüpunkte in der Sidebar) sollen im Laufe der Zeit zu Überthemen umbenannt werden, worüber passende Blogposts jeweils gefunden werden können. 
  *	Evt. Neues CNAME-File erstellen
  
Dies werde ich zu einem späteren Zeitpunkt in Angriff nehmen. 
Die Übungen in der Stunde zu Github haben mir keine Mühe bereitet, im Modul Dynamic Graphical User Interfaces letztes Jahr konnte ich einen guten Einblick in die Funktionsweise von Gitlab bekommen und fühle mich da deshalb einigermassen sicher. Deshalb werde ich das Thema Git/Github/Gitlab in meinem Lerntagebuch auch nicht weiter vertiefen.

---

#### MARC 21 und Dublin Core

Da ich Metadatenstandards und -formate nur so mässig spannend finde (dünnes Eis, das ist mir bewusst...) und mich dementsprechend in WOR nur mit dem Nötigsten auseinandergesetzt habe, versuche ich, dieses Thema hier etwas breiter aufzugreifen. 

---

##### Dublin Core

Gemäss Folien gilt Dublin Core als kleinster gemeinsamer Nenner. [Gantert (2016)](https://recherche.nebis.ch/primo-explore/fulldisplay?docid=ebi01_prod010601549&context=L&vid=NEBIS&lang=de_DE&search_scope=default_scope&adaptor=Local%20Search%20Engine&isFrbr=true&tab=default_tab&query=any,contains,gantert%20bibliothekarisches%20grundwissen&sortby=date&facet=frbrgroupid,include,320387376&offset=0) schreibt dazu, Dublin Core habe besondere Verbreitung bei der Erschliessung von Webdokumenten erlangt, da es ein einfach zu handhabendes Metadatensystem sei. Gemäss [Kuhlen, Semar und Strauch (2014)](https://recherche.nebis.ch/primo-explore/fulldisplay?docid=ebi01_prod007608008&context=L&vid=NEBIS&lang=de_DE&search_scope=default_scope&adaptor=Local%20Search%20Engine&isFrbr=true&tab=default_tab&query=any,contains,kuhlen%20semar%20strauch&sortby=date&facet=frbrgroupid,include,376931003&offset=0) ist dies ein Standard, der zur inhaltlichen Erschliessung infomrationeller Einheiten dient. 
Es wurde ein XML-Namesparce definiert, dieser umfasst 15 Elemente, die teilweise den traditionellen bibliothekarischen Beschreibungskategorien entsprechen (beispielsweise Autor, Subjekt, Thema, Verlag usw.)
Dublin Core-Metadaten können zum Beispiel mit RDF/XML dargestellt werden, werden aber auch in HTML-Websites genutzt. Dort werden sie als meta-Element im Dokumentenkopf angegeben. Als Hinweis auf den Namensraum wird dann jeweils "DC" verwendet [(Wikipedia, 2020)](https://de.wikipedia.org/wiki/Dublin_Core)

Hier mein Beispiel mit RDF/XML:

<img alt="Mobile home page" src="https://github.com/rumolin/lerntagebuch-bain/blob/master/_screenshots/Bild 3.PNG?raw=true" width="70%"/>

Und hier mein Beispiel für eine HTML-Website:

> ````<head profile="http://dublincore.org/documents/dcq-html/">````<br>
    ````<titel>BAIN Lerntagebuch</titel>````<br>
        ````<link rel="schema.DC" href="http://purl.org/dc/elements/1.1">````<br>
        ````<link rel="schema.DCTERMs" href="http://purl.org/dc/terms/">````<br>
        ````<meta name="DC.format" scheme="DCTERMS.IMT" content="text/html"/>````<br>
        ````<meta name="DC.title" content="Harper Lee"/>````<br>
    ````</head>````

---

##### MARC21

MARC21 ist der international verbreitete Metadaten-Standard, der 1999 von der Library of Congress gebründet wurde. Hauptzweck ist die Übertragung von bibliographischen Daten zwischen Bibliotheken. MARC liefert das Protokoll, du das bibliografische Informationen ausgetauscht werden können. Die Datenelemente bilden die Grundlage für die meisten Bibliothekskataloge [(Wikipedia, 2020)](https://de.wikipedia.org/wiki/Machine-Readable_Cataloging). Fremddatenübernahmen sind somit einfacher zu gestalten, setzt aber voraus, dass alle teilnehmenden Bibliotheken gleiche oder ähnliche Katalogisierungsregeln sowie ein einheitliches Datenformat, bzw. Austauschformat verwenden [Gantert (2016)](https://recherche.nebis.ch/primo-explore/fulldisplay?docid=ebi01_prod010601549&context=L&vid=NEBIS&lang=de_DE&search_scope=default_scope&adaptor=Local%20Search%20Engine&isFrbr=true&tab=default_tab&query=any,contains,gantert%20bibliothekarisches%20grundwissen&sortby=date&facet=frbrgroupid,include,320387376&offset=0). In der Praxis ist dies gemäss Folien anders, wegen den unterschiedlichen Regeln und der Möglichkeit, eigene Felder zu belegen, scheint die Verwendung stark vom vermeintlichen Standard abzuweichen. 

MARC21 soll voraussichtlich durch BIBFRAME (basiered auf RDF) abgelöst werden. Etwas genauer wird das Thema in (diesem Blogpost)[] behandelt 

---

##### Übung Vergleich MARC21 und Dublin Core

In der Stunde haben wir mit Zugriff auf [Swissbib](http://sru.swissbib.ch) Daten im Format MARC21 und Dublin Core verglichen. Folgende Aspekte sind aufgefallen:

* CD weist eine Vielzahl von Tags auf, die ohne viel Hintergrundwissen zu verstehen sind
* MARC21 hat Feldbezeichnungen in Form von Zahlen, was nur mit Hintergrundwissen zu verstehen ist
* MARC21 ist viel umfangreicher und enthählt dementsprechend auch mehr Informationen als DC

Dieser (Blogpost)[http://librariesandmetastuff.blogspot.com/2008/12/marc-and-dublin-core.html#:~:text=The%20most%20notable%20\(\and%20obvious,in%20the%20Dublin%20Core%20record] von (librariesandmetastuff)[http://librariesandmetastuff.blogspot.com/] weist ebenfalls auf diese Punkte hin, beschreibt aber die "fehlenden" Informationen in Dublin Core nicht unbedingt als grosses Problem, da dies in der Praxis (also beispielsweise in einer OPAC-Recherche) keine signifikanten Nachteile darstellen würde. Als grosses Manko von Dublin Core wird aber die Flexibilität genannt, die bereits im Zusammenhang mit MARC21 angesprochen wurde und bei Dublin Core wohl noch grösser sein soll. Die sorgt dafür, dass Dublin Core nicht so standardisiert ist, wie die Theorie das vorsehen würde und das Austauschen von Daten so sehr erschwert wird. 

---

#### Koha Bibliothek einrichten

Das Einrichten der Koha-Bibliothek habe ich nach den Angaben in den Folien gemacht. Da die Installation keinerlei Probleme gemacht hat und ich mich mit dem Arbeiten in der Shell eigentlich gut vertraut fühle, werde ich das hier nicht weiter ausführen. 
Auch das Bearbeiten des [Tutorials](https://zefanjas.de/wie-man-koha-installiert-und-fuer-schulen-einrichtet-teil-1/) hat keine Probleme bereitet. Einzig die Schnellaufnahme war bei mir möglich, da habe ich wohl vergessen, irgendwo ein Haken zu setzen. Durch Recherche habe ich dann eine csv-Datei gefunden, von der ich dachte, ich könnte sie importieren, um die Schnellaufnahme trotzdem zu machen. Dies hat leider nicht funktioniert. Eine Kollegin hat mir dann ihre ods-Datei zur Verfügung gestellt. Ich werde versuchen, das zu importieren. 

---

#### Offene To Do’s bis nächstes Mal:

[x] Schnellaufnahme in Koha 
[x] Koha-Tutorial durcharbeiten
