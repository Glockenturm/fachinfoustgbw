# Klassifikation für die Fachinformationsunterstützung der Bundeswehr (Klassifikation FachInfoUstgBw) in der 3. Auflage April 2020
*(Klassifikation FachInfoUstgBw, 3. Auflage April 2020)* 

## 1. Beschreibung des gewählten Vokabulars (Anzahl der Deskriptoren, benutzten Sprachen etc.) seines Anwendungsbereichs und Begründung der Auswahl gerade dieses Vokabulars

Die gewählte Klassifikation wird zur Erschließung des Bestandes der 59 Fachinformationsstellen der Bundeswehr genutzt. Die Klassifikation wird laufend aktualisiert. Die Klassifikation wurde als XML-Datei zur Verfügung gestellt. Stand der Klassifikation ist der **07.11.2024**. Die Klassifikation ist, wie die meisten Klassifikationen, monohierarchisch aufgebaut, das heißt, eine Klasse kann maximal eine Oberklasse besitzen. Zur Definition der Klassen werden Kommentare und Verweisungen zwischen den Klassen benutzt. Zusätzlich gibt es noch Hilfsklassen, welche in jeder Hauptklasse hinzugefügt werden können.

Die Klassifikation besteht aus 54 Hauptklassen. Diese enthalten 331 Hundertklassen, 1140 Zehnerklassen und 2102 Einerklassen, insgesamt 3573 zur Klassierung zugelassene Klassen. Die Klassen verteilen sich auf die folgenden Sektoren:

| **Sektor**           | **Anzahl Klassen** | 
|-----------------------|--------------------|
| Allgemeines           | 85                |
| Militärwesen          | 1121              |
| Geisteswissenschaften | 318               |
| Sozialwissenschaften  | 746               |
| Naturwissenschaften   | 624               |
| Technik               | 679               | 


### Fokus: Militärwesen  
Es wurde ein Sektor aus der Klassifikation ausgewählt, welcher exemplarisch für die Klassifikation ist. Der Schwerpunkt der Klassifikation liegt auf dem Sektor **Militärwesen**. Aus diesem Grund wurde der Sektor **MIA (Militärwesen)** mit den Unterklassen **MIA00, MIA100** und **MIA200** ausgewählt. Insgesamt besteht dieser Ausschnitt aus 40 Klassen und Unterklassen, die in Deutsch und Englisch vorliegen und mit Hinweisen (Scope Note) versehen sind. 

Die Klassen sind hierarchisch durch folgende SKOS-Properties definiert:

- `skos:broader`: Übergeordnete Klasse.
- `skos:narrower`: Untergeordnete Klasse.
- `skos:prefLabel`: Bevorzugter Begriff.

Als zweite Sprache wurde Englisch hinzugefügt, weil es die Sprache der Bundeswehr und ihrer Verbündeten ist. Die Übersetzung ist nicht offiziell und wurde zwecks der Aufgabe durch die Studierenden nach ihren Vorstellungen übersetzt. Insgesamt besteht dieser Ausschnitt aus 40 Unterklassen, die abschließend in Deutsch und Englisch vorliegen.

Die Werte der Klassifikation wurden in einer Excel-Datei definiert. Folgende Teststrings wurden als SKOS-Konzepte definiert: `skos:prefLabel`, `dct:title`, `dct:description`, `skos:definition`, `skos:scopeNote`. Außerdem wurden nach Aufgabenvorgabe die Teststrings `dct:language` und `dct:audience` definiert. Neben den grundlegenden SKOS-Properties (`hasTopConcept`, `topConceptOf`, `inScheme`, `prefLabel`) wurden drei zusätzliche Properties genutzt: `broader`, `notation`, `narrower`.

Anschließend wurde mit einem Python-Skript die Excel-Tabelle in ein `.ttl` (Turtle) Format importiert. Turtle ist ein Format zur Darstellung von RDF-Daten (Resource Description Framework). Es wird verwendet, um Begriffe und ihre Beziehungen maschinenlesbar zu beschreiben. SKOS baut auf RDF auf.

Eine manuelle Konvertierung wäre zu aufwendig gewesen, weshalb Python verwendet wurde.  
(Schritt 1: Mit Python und der Bibliothek Pandas wurden die Excel-Daten importiert.  
Schritt 2: Mit der Bibliothek rdflib wurden die RDF-Daten im Turtle-Format generiert.)  
Die so entstandene Turtle-Datei wurde anschließend auf der vorher geforkten Seite des Repositories hochgeladen und in mehreren Schritten angepasst, bis das Ergebnis vorlag.

#### Beispiel einer Klasse:  

```turtle
@prefix skos: <http://www.w3.org/2004/02/skos/core#> .

MIA:MIA000 a skos:Concept ;
    skos:prefLabel "Militärwesen"@de, "Military Affairs"@en ;
    skos:narrower MIA:MIA001, MIA:MIA002, MIA:MIA008 ;
    skos:notation "MIA000" ;
    skos:scopeNote "Hinw.: Allgemeines"@de, "Note: General"@en ;
    skos:topConceptOf MIA: .

```

## Zusammenarbeit mit Git und auf GitHub und – falls Sie das nutzen – unter Pflege eines gemeinsamen Kanban Boards. Wie hat es funktioniert? Was wurde gelernt? Wo sind noch Probleme?

Git und GitHub bieten sich sehr gut für das kollaborative Arbeiten an. Jede Änderung ist nachvollziehbar. Für die bessere und schnellere Zusammenarbeit haben beide Projektteilnehmenden in einem Repository gearbeitet. Die Kommunikation erfolgte über Mail und WhatsApp. Wöchentliche Zoom-Meetings halfen beim Vorankommen und beim gemeinsamen Arbeiten an Problemen. Mit den verwendeten Tools hat die Zusammenarbeit sehr gut funktioniert, allerdings waren wir nur zwei Studierende. Je mehr Personen an einem Vokabular arbeiten, desto schwieriger wäre die Umsetzung mit den derzeit genutzten Tools. Ein Kanban-Board würde sich hier besser eignen.

Ein Kanban-Board wurde erstellt, jedoch kaum verwendet. Dies hat mehrere Gründe:

Im Idealfall sollte mit einem Kanban-Board gearbeitet werden, das einem bekannt ist. Das Kanban-Board bei GitHub war für beide Studierenden neu, weshalb sie sich zuerst einarbeiten mussten. Allerdings war das eher zweitrangig, da auch die Aufgabe neu war und eine längere Einarbeitungszeit erforderlich war. So ist das Kanban-Board in den Hintergrund gerückt. Bekannte Kanban-Boards für die Studierenden wären z.B. Kanban-Boards bei Trello. Allerdings muss ein Kanban-Board im Voraus zumindest im Groben erstellt werden.
Um ein gutes Kanban-Board zu erstellen, sollte klar sein, wie die Aufgabe angegangen wird. Alle Schritte sollten zumindest im Groben vorher klar sein. Dies war nicht von Anfang an der Fall, da beide solch eine Aufgabe zum ersten Mal angegangen sind.
Ein Kanban-Board eignet sich sehr gut, um mit mehreren, auch unbekannten Personen zeitunabhängig zu arbeiten. Dies funktioniert aber nur, wenn ganz klar ist, was zu tun ist. Das war in unserem Fall nicht möglich. Eine regelmäßige Absprache über Zoom war notwendig, damit beide den gleichen Wissensstand hatten und Unklarheiten gemeinsam in Echtzeit besprochen und Änderungen vorgenommen werden konnten.
Grundsätzlich ist das Kanban-Board eine sehr gute Möglichkeit, um mit mehreren Personen, die bereits mit dem Aufgabenbereich vertraut sind, gemeinsam an einem SKOS-Vokabular zu arbeiten. In unserem Fall war es aber nicht notwendig. 

## Probleme beim Einrichten des Repos (Wie kann die Dokumentation verbessert werden?)

Nach anfänglichen Schwierigkeiten ist das Repository nun soweit fortgeschritten, dass auch der Rest des Vokabulars erstellt werden könnte. Das vorhandene Gerüst würde dafür reichen. Im nächsten Schritt kann nun ein Kanban-Board erstellt werden, in dem die jeweiligen Hauptklassen aufgelistet sind und Schritt für Schritt bearbeitet werden können.

Das einrichten eines Permalinks nach der folgender Anleitung  [Publishing SKOS the easy way](https://blog.skohub.io/2024-03-21-skohub-pages/) hat nicht funktioniert. Hierbei kam immer die Fehlermeldung *NOT FOUND

You just hit a route that doesn't exist... the sadness*. Erst der Austausch der custom domain in der config.yaml von [https://glockenturm.github.io/fachinfustgbw](https://glockenturm.github.io/fachinfustgbw) auf den Permalink [https://w3id.org/fachinfo-bw](https://w3id.org/fachinfo-bw) brachte die Lösung. 

## Verständnis von RDF und SKOS vor und nach Bearbeitung der Aufgabe.

Vor der Bearbeitung war kein Verständnis vorhanden. 
**RDF**: Die Standardisierung bei RDF ermöglicht eine weltweite Darstellung eines Vokabulars. Die Turtle-Syntax für RDF ist eine sehr gut verständliche und für den Menschen leicht lesbare Darstellung. Die URI ermöglicht eine einfache Auffindung im Web, ohne eine PDF-Datei durchsuchen zu müssen, was man zu Beginn mit der Klassifizierung machen müsste, bevor wir das Vokabular veröffentlicht hatten.
**SKOS**: SKOS eignet sich sehr gut für die Darstellung der von uns gewählten Klassifikation. Alle Inhalte des Vokabulars können dort problemlos eingefügt werden. Die Beziehungen ermöglichen eine konkrete Darstellung der Verhältnisse innerhalb des Vokabulars. Die Konzepte, Labels, semantischen Relationen und die Beziehungen lassen sich sehr gut auf die Klassifikation übertragen und bieten eine übersichtlichere Darstellung als ein PDF-Dokument oder eine XML-Datei.

## Ausblick: Was ist durch die SKOS-Repräsentation des Vokabulars und seiner Publikation im Web gewonnen? Welche Anwendungsfälle werden nun ermöglicht?

Da es sich um eine spezialisierte Klassifikation in einem Randthema handelt und diese nun veröffentlicht wurde, ist eine Nutzung durch andere Bibliotheken möglich. Inwiefern das Vokabular noch weiterentwickelt und eventuell angereichert wird, bedarf einer internen Klärung.
