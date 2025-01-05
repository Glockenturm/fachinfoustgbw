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

Als zweite Sprache wurde Englisch hinzugefügt, weil es die Sprache der Bundeswehr und ihrer Verbündeten ist. Die Übersetzung ist nicht offiziell und wurde zwecks der Aufgabe durch die Studierednen nach ihren Vorstellungen übersetzt. Insgesamt besteht dieser Ausschnitt aus 40 Unterklassen, die abschliessend in Deutsch und Englisch vorliegen.

Die Werte der Klassifikation wurden in einer Excel-Datei definiert. Folgende Teststrings wurden SKOS-Konzepte wurden definiert: skos:prefLabel, dct:title, dct:description, skos:definition, skos:scopeNote. Außerden wurden noch nach Aufgabenvorgabe die Teststrings dct:language und dct:audience denfiniert. Neben den grundlegenden SKOS-Properties (hasTopConcept, topConceptOf, inScheme, prefLabel), wurden drei zusätzliche Properties genutzt: broader, notation, narrower.
Anschließend mittels eines Python-Skripts die Excel-Tabelle in ein .ttl (Turtle) Format importiert. Turtle ist ein Format zur Darstellung von RDF-Daten (Resource Description Framework). Es wird verwendet, um Begriffe und ihre Beziehungen maschinenlesbar zu beschreiben. SKOS baut auf RDF auf. 

Eine manuelle Konvertierung ist zu aufwendig, deswegen wurde Python verwendet (Schritt 1: Mit Python und der Bibliothek Pandas wurden die Excel-Daten importiert. Schritt 2: Mit der Bibliothek rdflib wurden die RDF-Daten im Turtle-Format generiert). Die so entstandene Turtle-Datei wurde anschließend auf der vorher geforkten Seite des Repositoriums hochgeladen und in mehreren Schritten angepasst, bis das Ergebnis vorliegt.

#### Beispiel einer Klasse:  

```turtle
@prefix skos: <http://www.w3.org/2004/02/skos/core#> .

<MIA100> a skos:Concept ;
    skos:prefLabel "Militärgeschichte"@de ;
    skos:altLabel "History of Military"@en ;
    skos:broader <MIA> ;
    skos:scopeNote "Beschreibt die historische Entwicklung militärischer Konflikte und Organisationen."@de .
`---`

## Zusammenarbeit mit Git und auf GitHub und – falls Sie das nutzen – unter Pflege eines gemeinsamen Kanban Boards. Wie hat es funktioniert? Was wurde gelernt? Wo sind noch Probleme?

Git und GitHub bieten sich sehr gut für das kollaborative Arbeiten an. Jede Änderung ist nachvollziehbar. Für die bessere und schnellere Zusammenarbeit haben beide Projektteilnehmenden in einem Repositorium gearbeitet. Die Kommunikation erfolgte über Mail und Whatsapp. Wöchentliche Zoom-Meetings halfen beim Vorankommen und beim gemeinsamen Arbeiten an Problemen. Mit den verwendeten Tool hat die Zusammenarbeit sehr gut funktioniert, allerdings waren wir nur zwei Studierende. Je mehr Personen an einem Vokabular arbeiten, desto schwieriger wäre die Umsetzung mit den derzeit genutzten Tools. Es würde sich ein Kanban Board besser eignen.

Ein Kanban-Boards wurde erstellt, jedoch kaum verwendet. Dies hat mehrere Gründe:
1. Im Ideallfall sollte mit einem Kanban Board gearbeitet werden, dass einem bekannt ist. Das Kanban Board bei Github war für beide Studierenden neu, weswegen sich sich da zuerst einarbeiten müssten. Allerdings war das eher zweitrangig, da auch die Aufgabe neu war und da auch eine längere Einarbeitungszeit notwenig war. So ist das Kanban Board in den Hintergrund gerückt. Bekannte Kanban Board für die Studierenden wäre z.B. ein Kanban Board bei Trello. Allerdings muss das Kanban Board im Voraus zumindest im Groben erst erstellt werden.
2. Um ein gutes Kanban-Board zu erstellen, sollte klar sein, wie die Aufgabe anzugehen ist. So sollten alle Schritte schon zumindest im Groben vorher klar sein. Dies war nicht von Anfang an der Fall, da beide solch eine Aufgabe zum ersten Mal angegangen sind.
3. Ein Kanban Board eignet sich sehr gut, um mit mehreren, auch unbekannten Personen zeitunabhängig zu arbeiten. Dies funktionert aber nur, wenn ganz klar ist, was zu tun ist. Das war in unserem Fall nicht möglich. Eine regelmäßige Absprache über Zoom war notwendig, damit beide den gleichen Wissenstand haben und Unklarheiten gemeinsam in Echtzeit besprochen werden können und Änderungen in Echtzeit vorgenommen werden können.
4. Grundsätzlich ist das Kanban Board eine sehr Möglichkeit, um mit mehreren Personen, die schon mit dem Aufgabenbereicht verttraut sind, gemeinsam an einem SKOS-Vokabular zu arbeiten. In unserem Fall war es aber nicht notwendig. 

## Probleme beim Einrichten des Repos (Wie kann die Dokumentation verbessert werden?)

Nach anfägnglichen Schwierigkeiten ist das Repo nun soweit fortgeschritten, dass auch der Rest des Vokabulars erstellt werden könnte. Das vohandene Gerüst würde dafür reichen. Im nächsten Schritt kann nun ein Kanban Board erstellt werden, in dem die jeweiligen Hauptklassen aufgelistet sind und Schritt für Schritt bearbeitet werden können.

## Verständnis von RDF und SKOS vor und nach Bearbeitung der Aufgabe.

Vor der Bearbeitung war kein Verständnis vorhanden. 
RDF: Die Standartisierung bei RDF ermöglich eine weltweite Darstellung einen Vokabulars. Die Turtle-Syntax für RDF ist eine sehr gut verständliche und auf den Menschen leicht lesbare Darstellung. Die URI ermöglicht eine einfache Auffindung im Web, ohne eine PDF Datei durchsuchen zum müssen, was man zu Beginn mit der Klassifizierung machen müsste, bevor wir das Vokabular veröffentlicht hatten.
SKOS: SKOS eigent sich sehr gut für die Dastellung der von uns gewählten Klassifikation. Alle Inhalte des Vokabulars konnen wir dort prolemlos einfügen. Die Beziehungen ermöglichen eine konkrete Darstellung der Beziehungen innerhalb des Vokabluars. Die Konzepte, Labels, semantische Relation und die Beziehungen lassen sich sehr gut auf die Klassifikation übertragen und bieten eine übersichtlichere Datstellung als ein PDF Dokument oder eine XML-Datei.

## Ausblick: Was ist durch die SKOS-Repräsentation des Vokabulars und seiner Publikation im Web gewonnen? Welche Anwendungsfälle werden nun ermöglicht?

Da es sich um eine spezialisierte Klassifikation in einem Randthema handelt und dies nun veröffentlicht wurde, ist eine Nutzung durch andere Bibliotheken möglich. Inwiefern das Vokabular noch weiterentwickelt und eventuell angereichert wird, bedarf einer internen Klärung.
