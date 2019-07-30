# Zitieren mit biblatex


# Begriffsunterscheidung


* BibTeX ist das alte System zur Literaturverwaltung und zur Generierung
von Zitaten.
* biblatex ist ein Package. Es versteht die BibTeX-Syntax zur Literaturverwaltung (die bib-Dateien). Die Anzeige der Zitate ist völlig neu implementiert auf Basis von LaTeX.
* biber ist ein Programm um die cite Befehle zu übersetzen. Wenn utf8 im
Spiel ist, müssen Sie biber benutzen.
* BibTeX ist das altbewährte System, hat aber erhebliche Probleme mit
utf8. Deshalb verwenden Sie bei der Verwendung von utf8 zwar die Syntax
von BibTeX zur Organisation, aber biber zur Interpretation und biblatex
zur Übersetzung.

# Literatur in einer Datenbank verwalten

Es macht keinen Sinn Literatur für jede Arbeit neu zu erfassen. 
Stattdessen speichert man sie besser in einer zentralen Datenbank und referenziert diese über einen Schlüssel. 
Wenn man die Daten einmal richtig erfasst und es LaTeX überlässt die Darstellung zu generieren, erspart das sehr viel Arbeit.
Zudem kann man beruhigt sein ein vollständiges Literaturverzeichnis zu haben.

## Software zur Verwaltung

Diese Datenbank ist eine .bib-Datei. Die könnte man mit einem Texteditor selbst erstellen und pflegen, aber das ist fehleranfällig. 
Einerseits könnte man benötigte Informationen vergessen und andererseits hat man sich schnell vertippt und einen Syntaxfehler.
Deshalb nimmt man dazu spezialisierte Software:

Software | Kommentar
------ | ------
JabRef | Arbeitet ohne Umweg mit .bib-Dateien. Aktuell (Sommer 2019) keine Empfehlung, weil eine ganz bestimmte Version von Java benötigt wird.
Citavi | Kommerziell / Hat ein eigenes Format. / Man kann Unterstützung für LaTeX aktivieren, so dass Keys generiert werden und ein Export nach .bib möglich wird.
[Zotero](https://www.zotero.org/) | 

*Als Studierende der Universität Köln können Sie (mit Stand Sommer 2019) zumindest Endnote und Citavi vergünstigt beziehen.*


## Literatur einlesen


## .bib Datei generieren

# Zitieren im Dokument

# Das Literaturverzeichnis und die Zitate generieren

