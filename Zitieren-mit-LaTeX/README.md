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

Es gibt drei Möglichkeiten Literatur in Ihre Datenbank einzulesen:

1. Manuell: Sie wählen die Literaturart aus und füllen alle Felder manuell aus. Das ist fehleranfällig und mühsam.
1. Über Exportdateien: Wenn Sie die Seite des Artikels auf der Seite des Verlags finden, können Sie dort oft Dateien mit allen nötigen Informationen im .bib oder .ris Format runterladen. Diese müssen Sie dann mit Ihrer Literaturverwaltung importieren und gegebenfalls etwas bereinigen. (manche Verlage erzeugen diese unsauber und Sie finden zum Beispiel LaTeX-Befehlszeichen im Abstract.)
1. Über die DOI-Nummer: Nicht jeder Artikel hat eine [DOI-Nummer](https://de.wikipedia.org/wiki/Digital_Object_Identifier), aber der Großteil der in den letzten Jahren erschienen Fachliteratur. Die meisten Literaturverwaltungsprogramme haben ein Eingabefeld für diese Nummer und sind in der Lage alle nötigen Informationen darüber aus dem Internet zu ziehen. Hier müssen Sie die Eingabe nur noch gegenchecken.


## .bib Datei generieren

Falls Ihre Software direkt im .bib-Format arbeitet, müssen Sie hier nichts tun.

Falls Ihre Software ein eigenes Format hat, müssen Sie jedesmal wenn Sie neue Quellen hinzugefügt haben, einen Export in das .bib-Format vornehmen. Wenn noch nicht geschehen, sollten Sie das automatisch generieren von keys aktiviert haben, oder selbst solche für jeden Eintrag erstellen.

# Zitieren im Dokument

# Das Literaturverzeichnis und die Zitate generieren

## Informationen ausblenden

