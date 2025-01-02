# Klassifikation für die Fachinformationsunterstützung der Bundeswehr (Klassifikation FachInfoUstgBw) 
## Beschreibung des gewählten Vokabulars (Anzahl der Deskriptoren, benutzten Sprachen etc.) seines Anwendungsbereichs und Begründung der Auswahl gerade dieses Vokabulars
Diese Klassifikation basiert auf der Fachinformationsunterstützung der Bundeswehr (Klassifikation FachInfoUstgBw). Er stellt ein freiwilliges Regelwerk zur Harmonisierung und Standardisierung der Forschungsberichterstattung an Forschungseinrichtungen dar. In diesem Repositorium ist die Klassifikation für die Fachinformationsunterstützung der Bundeswehr (Klassifikation FachInfoUstgBw) in SKOS (Turtle Syntax) kodiert. Aus dieser Datei wird eine navigierbare und durchsuchbare Ansicht der FachInfoUstgBw generiert.
## Zusammenarbeit mit git und auf GitHub und – falls Sie das nutzen – unter Pflege eines gemeinsamen Kanban Boards. Wie hat es funktioniert? Was wurde gelernt? Wo sind noch Probleme?
## Probleme beim Einrichten des Repos (Wie kann die Dokumentation verbessert werden?)
Ablauf von Klassifikation FachInfoUstgBw zum Soks Vokabular.
Schritt 1: Konvertiertung des Vokabulars von Excel in eine Turtle-Datei. Turtle ist ein Format zur Darstellung von RDF-Daten (Resource Description Framework). Es wird verwendet, um Begriffe und ihre Beziehungen maschinenlesbar zu beschreiben. SKOS baut auf RDF auf.
Eine manuelle Konvertiertung ist zu aufwendig, deswegen wird Python verwendet (Schritt 1:  Mit Python und der Bibliothek pandas kannst du die Excel-Daten lesen. Schritt 2: Mit der Bibliothek rdflib kannst du RDF-Daten im Turtle-Format generieren.)
## Verständnis von RDF und SKOS vor und nach Bearbeitung der Aufgabe.
## Ausblick: Was ist durch die SKOS-Repräsentation des Vokabulars und seiner Publikation im Web gewonnen? Welche Anwendungsfälle werden nun ermöglicht?
