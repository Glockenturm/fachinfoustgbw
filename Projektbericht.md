# Klassifikation für die Fachinformationsunterstützung der Bundeswehr (Klassifikation FachInfoUstgBw) in der 3. Auflage April 2020

## Beschreibung des gewählten Vokabulars (Anzahl der Deskriptoren, benutzten Sprachen etc.) seines Anwendungsbereichs und Begründung der Auswahl gerade dieses Vokabulars

Die **gewählte** Klassifikation wird zur **Erschließung** des Bestandes der Fachinformationsstellen der Bundeswehr genutzt. Die Klassifikation wird laufend aktualisiert. Die Klassifikation wurde als XML-Datei zur Verfügung gestellt. Stand der Klassifikation ist der 07.11.2024. Die Klassifikation ist, wie die meisten Klassifikationen, monohierarchisch aufgebaut, das heißt, eine Klasse kann maximal eine Oberklasse besitzen. Zur Definition der Klassen werden Kommentare und Verweisungen zwischen den Klassen benutzt. Zusätzlich gibt es noch Hilfsklassen, welche in jeder Hauptklasse hinzugefügt werden können.

Die Klassifikation besteht aus 54 Hauptklassen. Diese enthalten 331 Hundertklassen, 1140 Zehnerklassen und 2102 Einerklassen, insgesamt 3573 zur Klassierung zugelassene Klassen. Die Klassen verteilen sich auf die folgenden Sektoren:

- **Allgemeines**: 85 Klassen
- **Militärwesen**: 1121 Klassen
- **Geisteswissenschaften**: 318 Klassen
- **Sozialwissenschaften**: 746 Klassen
- **Naturwissenschaften**: 624 Klassen
- **Technik**: 679 Klassen

Es wurde ein Sektor aus der Klassifikation ausgewählt, welcher exemplarisch für die Klassifikation ist. Das Hauptgewicht der Klassifikation liegt auf dem Sektor Militärwesen. Aus diesem Grund wurde der *Sektor MIA (Militärwesen) mit den Unterklassen MIA00, MIA100 und MIA200 ausgewählt.* Insgesamt besteht dieser Ausschnitt aus 40 Klassen und Unterklassen, die in Deutsch und Englisch vorliegen und mit Hinweisen (Scope Note) versehen sind. Die Klassen sind alle hierarchisch miteinander verbunden, sind mittels *broader* als Teil einer Klasse bzw. *narrower* als übergeordneter Teil einer Klasse definiert. Mit *prefLabel* werden die Klassen definiert.

Als zweite Sprache wurde Englisch hinzugefügt, weil es die Sprache der Bundeswehr und ihrer Verbündeten ist. Die Übersetzung wurde von den Durchführenden durchgeführt. Insgesamt besteht dieser Ausschnitt aus 40 Unterklassen, die in Deutsch und Englisch vorliegen.

Die Werte der Klassifikation wurden in einer Excel-Datei definiert und anschließend mittels eines Python-Skripts in ein .ttl (Turtle) Format importiert. Turtle ist ein Format zur Darstellung von RDF-Daten (Resource Description Framework). Es wird verwendet, um Begriffe und ihre Beziehungen maschinenlesbar zu beschreiben. SKOS baut auf RDF auf. 

Eine manuelle Konvertierung ist zu aufwendig, deswegen wurde Python verwendet (Schritt 1: Mit Python und der Bibliothek Pandas wurden die Excel-Daten importiert. Schritt 2: Mit der Bibliothek rdflib wurden die RDF-Daten im Turtle-Format generiert). Die so entstandene Turtle-Datei wurde anschließend auf der vorher geforkten Seite des Repositoriums hochgeladen und in mehreren Schritten angepasst, bis das Ergebnis vorliegt.

## Zusammenarbeit mit Git und auf GitHub und – falls Sie das nutzen – unter Pflege eines gemeinsamen Kanban Boards. Wie hat es funktioniert? Was wurde gelernt? Wo sind noch Probleme?

Git und GitHub bieten sich sehr gut für das kollaborative Arbeiten mittels des Codes an. Jede Änderung ist nachvollziehbar. Für die bessere und schnellere Zusammenarbeit haben beide Projektteilnehmenden in einem Repositorium gearbeitet.

## Probleme beim Einrichten des Repos (Wie kann die Dokumentation verbessert werden?)

Es gab keine Probleme.

## Verständnis von RDF und SKOS vor und nach Bearbeitung der Aufgabe.

Vor der Bearbeitung war kein Verständnis vorhanden. Abschließend ist ein grundlegendes Verständnis vorhanden. Vor allem das Zusammenspiel zwischen der .ttl-Datei und das Anpassen sowie das Arbeiten mit den Changes auf GitHub war sehr lehrreich.

## Ausblick: Was ist durch die SKOS-Repräsentation des Vokabulars und seiner Publikation im Web gewonnen? Welche Anwendungsfälle werden nun ermöglicht?

Da es sich um eine spezialisierte Klassifikation in einem Randthema handelt und dies nun veröffentlicht wurde, ist eine Nutzung durch andere Bibliotheken möglich. Inwiefern das Vokabular noch weiterentwickelt und eventuell angereichert wird, bedarf einer internen Klärung.
