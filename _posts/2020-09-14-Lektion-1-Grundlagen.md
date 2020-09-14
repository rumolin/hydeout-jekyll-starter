---
layout: post
title: Lektion 1 Grundlagen
excerpt_separator: "<!--more-->"
comments: false
sidebar_link: true
categories: 
tags: 
- start
- basics
- shell
- jekyll
- markdown

---
<img alt="Mobile home page" src="https://github.com/rumolin/lerntagebuch-bain/blob/master/_screenshots/Bild 1.PNG?raw=true" width="70%"/>
---

Aufsetzen des Lernblogs
---

Bei der Übernahme des bereitgestellten Templates habe ich bemerkt, dass es verschiedene Jekyll-Themes gibt, die theoretisch als Grundlage verwendet werden können. Dies hat mich sogleich gepackt und wollte unbedingt ein schönes Layout für meinen Blog finden. Schlussendlich fiel die Wahl auf [Hydeout](http://jekyllthemes.org/themes/hydeout/). Für das Aufsetzen des Blogs habe ich das Repository von [@Forestryio](https://github.com/forestryio/hydeout-jekyll-starter) geforked und bearbeitet. Folgende Anpassungen habe ich vorgenomnen,, damit die Website funktioniert:
*	CName-file gelöscht 
*	Baseurl im config-file durch meine URL ersetzt ('/lerntagebuch-bain')
*	Den Branch gh-pages gelöscht (so lange ich diesen Branch und den masterbranch hatte, hat das online-Stellen komischerweise nicht geklappt….)
  
  Folgendes habe ich angepasst:
  *	Title, tagline, description und persönliche Angaben
  *	Sidebar personalisiert
  *	Favicon geändert
  
Folgende Änderungen am Blog sind noch geplant: 
  *	Auf der Hauptseite soll nicht mehr der ganze Blogartikel sichtbar sein, sondern nur noch eine Vorschau (inklusive Beitragsbild) 
  *	About, Thema 1, Thema 2 und Post Formats (Menüpunkte in der Sidebar) sollen im Laufe der Zeit zu Überthemen umbenannt werden, worüber passende Blogposts jeweils gefunden werden können. 
  *	Evt. Neues CNAME-File erstellen
  
Momentan stellt sich mir noch die Frage, wie ich am einfachsten Änderungen am Lernblog vornehmen kann, damit diese gleich sichtbar werden. Beim Arbeiten mit Gitlab letztes Jahr war der grosse Vorteil, dass ich viele Änderungen lokal bei mir auf dem Rechner ausprobieren konnte. Erst sobald etwas definitiv funktioniert hat, habe ich committed und gepusht. Mit Github-pages scheint es so, als ob jede kleine Änderung sofort committed werden muss, um sie sichtbar zu machen. Das hat viele Commits zur Folge. Das werde ich noch in Erfahrung bringen. 

Markdown
---
Ein Thema das mich sowohl im Zusammenhang mit dem Lernblog, aber auch generell beschäftigt, ist Markdown. Ich kannte das vorher noch nicht und bin aber bis jetzt recht begeistert von der simplen Syntax. Folgende Übersicht habe ich erstellt:

|Code|Ausgabe|
|-----------------|-----------------|
|```` #Überschriften Note: (je mehr # desto kleiner ````|#Überschrift1|
|```` *kursiv* ````|*kursiv*|
|```` **fett** ````|**fett**|
|```` - liste 1 ````| - liste 1|
|```` * liste 2  ````| * liste 2|
|```` + liste 3  ````|+ liste 3|
|```` 1. Liste  ````|1. Liste|
|```` [link text](https://link.ch)  ````|[link text](https://link.ch)  |
|```` <img alt="Mobile home page" src="https://github.com/rumolin/
lerntagebuch-bain/blob/master/_screenshots/binaer.jpg?raw=true" width="30%"/>````
|<img alt="Mobile home page" src="https://github.com/rumolin/lerntagebuch-bain/blob/master/_screenshots/binaer.jpg?raw=true" width="30%"/>[^1]|
|```` > Zitat  ````|> Zitat|
|```` ---   ````|---|
|```` Ich bin eine Fussnote.[^2]  ````| Ich bin eine Fussnote.[^2]  |


Gemäss [CMSStash](https://cmsstash.de/website-praxis/markdown-fur-webseiten) gibt es unter anderem den GitHub-Flavoured-Dialekt, der allenfalls etwas anders funktioniert. Bei zukünftigen Unklarheiten werde ich also die [GitHub-Seite](https://github.github.com/gfm/) besuchen.

Unix Shell Kommandos:
---
Um die Shell-Kommandos nochmals zu repetieren habe ich die Übungen aus der Library Corpentry gemacht. Zusätzlich habe ich über die Shell ein File erstellt, um die nützlichen Befehle zu notieren. Dies ist hier abgelegt: [commands.txt](https://github.com/rumolin/lerntagebuch-bain/blob/master/commands.txt)
Offene To Do’s bis nächstes Mal:

- [ ] Blog Vorschau auf Hauptseite einrichten
- [ ] offene Fragen klären
- [ ] ...

[^1]: Komischerweise hat die Eingabe des Dateipfades alleine nicht gereicht und mit der empfohlenen Markup-Variante wurde mir kein Bild angezeigt.
[^2]: Fussnotentext jeweils am Ende der Seite platzieren
