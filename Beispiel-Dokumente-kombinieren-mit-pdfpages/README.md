# Dokumente kombinieren mit pdfpages


Gelegentlich muss man verschiedene Dokumente in einer Datei zusammenfassen. Klassischer Anwendungsfall ist eine Bewerbung wo manchmal Anschreiben, Lebenslauf und Zeugnisse in Form eines *einzigen* Dokuments eingereicht werden sollen. Da Sie in der Regel nicht die gleiche Dokumentenklasse für die Einzeldokumente verwenden, müssen Sie sie gesondert erstellen. Mit dem LaTeX-Package [pdfpages](https://www.ctan.org/pkg/pdfpages) und einem Hauptdokument, können Sie diese dann einfach zusammenführen.

Dieses Beispiel besteht aus drei Dokumenten:


* Einem Anschreiben im gleichnamigen Ordner. Erstellt mit der documentclass `scrlttr2`.
* Ein Lebenslauf im gleichnamigen Ordner. Erstellt mit der documentclass `moderncv`. Es gibt noch [viele andere Möglichkeiten einen Lebenslaif in LaTeX zu erstellen](https://www.overleaf.com/articles/tagged/cv). Suchen Sie sich eine passende Documentclass heraus.
* Ein Hauptdokument in diesem Ordner, welches mit `pdfpages` die Dokumente kombiniert. Diesem sollten Sie einen aussagekräftigen Dateinamen geben, wie `Jahreszahl-Bewerbung-StellenID-IhrName.tex`.



Beachten Sie:


* Für ein stimmiges Gesamtbild sollten Sie in allen Dokumenten die gleiche Schriftart verwenden.
* Die Dokumente sollten die gleiche Papiergröße (also zum Beispiel DIN A4) haben.
* Oft gibt es Limits für die Gesamtgröße des Dokuments. Das kann schwierig werden, wenn Sie Scans von Dokumenten einfügen.
