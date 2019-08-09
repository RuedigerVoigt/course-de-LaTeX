# Zitieren mit biblatex


# Begriffsunterscheidung


* BibTeX ist das alte System zur Literaturverwaltung und zur Generierung
von Zitaten.
* [biblatex](https://ctan.org/pkg/biblatex) ist ein Package. Es versteht die BibTeX-Syntax zur Literaturverwaltung (die bib-Dateien). Die Anzeige der Zitate ist völlig neu implementiert auf Basis von LaTeX.
* `biber` ist ein Programm um die `\cite` Befehle zu übersetzen. Wenn utf8 im
Spiel ist, müssen Sie biber benutzen.

Anders gesagt: BibTeX ist das altbewährte System, hat aber erhebliche Probleme mit
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
BibDesk | Für MacOS
Citavi | Kommerziell / Hat ein eigenes Format. / Man kann Unterstützung für LaTeX aktivieren, so dass Keys generiert werden und ein Export nach .bib möglich wird.
[Zotero](https://www.zotero.org/) | 

*Als Studierende der Universität Köln können Sie (mit Stand Sommer 2019) zumindest Endnote und Citavi vergünstigt beziehen.*

**Bei Programmen, die nicht direkt mit .bib-Dateien arbeiten, müssen Sie oft den LaTeX-Support noch aktivieren!** Zum Beispiel müssen Sie dies in Citavi tun, damit Keys zum Zitieren generiert werden.


## Literatur einlesen

Es gibt drei Möglichkeiten Literatur in Ihre Datenbank einzulesen:

1. Manuell: Sie wählen die Literaturart aus und füllen alle Felder manuell aus. Das ist fehleranfällig und mühsam.
1. Über Exportdateien: Wenn Sie die Seite des Artikels auf der Seite des Verlags finden, können Sie dort oft Dateien mit allen nötigen Informationen im .bib oder .ris Format runterladen. Diese müssen Sie dann mit Ihrer Literaturverwaltung importieren und gegebenfalls etwas bereinigen. (manche Verlage erzeugen diese unsauber und Sie finden zum Beispiel LaTeX-Befehlszeichen im Abstract.)
1. Über die DOI-Nummer: Nicht jeder Artikel hat eine [DOI-Nummer](https://de.wikipedia.org/wiki/Digital_Object_Identifier), aber der Großteil der in den letzten Jahren erschienen Fachliteratur. Die meisten Literaturverwaltungsprogramme haben ein Eingabefeld für diese Nummer und sind in der Lage alle nötigen Informationen darüber aus dem Internet zu ziehen. Hier müssen Sie die Eingabe nur noch gegenchecken.


## .bib Datei generieren

Falls Ihre Software direkt im .bib-Format arbeitet, müssen Sie hier nichts tun.

*Falls Ihre Software ein eigenes Format hat, müssen Sie jedesmal wenn Sie neue Quellen hinzugefügt haben, einen Export in das .bib-Format vornehmen.* Wenn noch nicht geschehen, sollten Sie das automatische Generieren von Keys aktiviert haben, oder selbst solche für jeden Eintrag erstellen.

# Zitieren im Dokument

## Vorbereitungen in der Präambel


In der Präambel (also vor `\begin{document}`) müssen Sie einige Einstellungen setzen. zunächst müssen Sie die Optionen für biblatex festlegen. Zum Beispiel so:

```
\usepackage[backend = biber,
style=authoryear,
sorting = nyt
]{biblatex}
```

Die Option `style` stellt ein, wie das Zitat im Dokument dargestellt wird. Hier ist der Stil `authoryear`, das heißt ein Buch würde über den Nachnamen des Autors / der Autorin und der Jahreszahl des Erscheinens zitiert. Hat eine Person im gleichem Jahr mehrere Werke verfasst, wandelt das LaTeX zum Beispiel das Jahr 2019 in 2019a, 2019b und so weiter um.

Die Option `sorting` bezieht sich auf die Sortierreihenfolge in der Bibliographie. Hier `nyt` also Nachname, Jahr, Titel.

Nun müssen Sie biblatex noch mitteilen, wo es die .bib-Datei findet. Angenommen Sie heißt `literature.bib`und liegt im gleichen Verzeichnis wie das Hauptdokument, dann geht das so:

```
\addbibresource{literature.bib}
```

## Das eigentliche Zitieren


Das Zitieren erfolgt nun über den `Key`, den Ihre Literaturverwaltung für jeden einzelnen Eintrag erzeugt haben sollte. Angenommen der Key ist `Voigt2020`, dann zitieren Sie mit
```
\cite[123-125]{Voigt2020}
```
Die Zahl in eckigen Klammern ist dabei die Seitenzahl, die Sie zitieren möchten. Biblatex fügt abhängig von der eingestellten Sprache und dem Zitat-Stil noch ein `S.`, oder ein `p.` bzw. `pp.` hinzu. Mit dem Stil `authoryear `würde der Eintrag dann als "Voigt 2020, pp.123-125" im Text dargestellt. Den vollständigen Quellenverweis können Sie dann im Literaturverzeichnis anschauen. Übrigens: wenn Sie `hyperref`geladen haben, werden diese Zitate automatisch mit der Bibliographie verlinkt.


## Das Literaturverzeichnis und die Zitate generieren


Sie müssen LaTeX noch mitteilen, wo das Literaturverzeichnis / die Bibliographie angezeigt werden soll. Dazu fügen Sie im entsprechenden Dokument an der gewünschten Stelle den Befehl `\printbibliography` ein. Dort wird die Bibliographie dann ausgegeben. 

Das Literaturverzeichnis nethält nur die Elemente, die Sie auch zitiert haben. Allerdings muss es - wie die Einträge - zunächst einmal generiert werden. Das geht in drei Schritten:


1. Ein Durchlauf von `pdflatex`.
1. Ein Durchlauf von `biber`.
1. Ein weiterer Durchlauf von `pdflatex`.

In den meisten LaTeX-Editoren ist das Profil `pdflatex -> bibtex -> pdflatex` hinterlegt. Theoretisch sollte BibTeX wegen unserer Einstellungen in der Präambel von sich aus `biber`aufrufen, aber das funktioniert in der Praxis nicht zuverlässig. Daher empfiehlt es sich das Profil anzupassen, oder ein Neues anzulegen.

Diese Aufrufe müssen Sie immer dann durchführen, wenn Sie neue Quellen zitieren.

## Informationen ausblenden

Manchmal speichert Ihr Literaturmanager Informationen über die Quelle, die Sie nicht mit ausgeben möchten. Diese können Sie einfach in der Software belassen und stattdessen für das gesamte Dokument ausblenden.


# Das Literaturverzeichnis überprüfen

