---
layout: default
title: Teamwork
permalink: /teamwork
# has_children: true
nav_order: 130
---
# Teamwork

## Reservierung Spezial
Ist gerade kein Element ausgewählt, so öffnet ein Klick auf den <samp>Reservieren</samp> Button ein Fenster, in dem sich a) ganze Projektregionen (wie ein Ausschnitt oder ein Geschoss) und anschließend b) Elemente nach Kriterien (wie <samp>Suchen&Aktivieren</samp>) auswählen lassen.  
Der Vorteil dieser Methode ist, dass keine Rücksicht auf die Sichtbarkeit von Ebenen genommen wird.

Reservierte Elemente lassen sich nach einem Klick auf <samp>Mein Arbeitsbereich</samp> in der Teamworkpalette anzeigen.

Achtung bei Projekten mit Hotlinks! Hotlinks lassen sich nur insgesamt reservieren, nicht individuelle Elemente daraus.


## Build Nummer
Die Buildnummern von Archicad zu Teamworkserver müssen nicht gleich sein, aber jedoch im selben Hunderter-Abschnitt sein. Beispiel: Die Builds 4019 und 4032 sind kompatibel zu einander. Alle Builds im Bereich 40xx wären möglich nebeneinander zu betreiben.


## Troubleshooting
Wenn Probleme auftreten, empfiehlt es sich, dass sämtliche Beteiligte alles senden/freigeben. Auf einem Rechner/mit einem Benutzer dann den aktuellsten Stand konsolidieren (nun ist auch ein guter Zeitpunkt die Datei allgemein etwas aufzuräumen) und als Solo-PLN lokal abspeichern. Nun muss auf jedem Rechner das Projekt verlassen werden (<samp>Teamwork > Projekt > Teamwork-Projekt verlassen</samp>). Das Verlassen eines Teamwork-Projekts löscht alle lokalen Daten; diese werden bei einem erneuten Beitritt frisch vom Server geladen.  
_Nicht_ gelöscht werden dagegegen jedoch heruntergeladene Bibliotheken. Treten Schwierigkeiten mit Bilbiothekselementen auf, so hilft es unter <samp>Teamwork > Projekt > Lokale-Daten-Manager</samp> die lokale Kopie der Bibliothek zu löschen. Das lässt sich auch im "laufenden Betrieb" erledigen – anschließend kann mit <samp>Neu laden & Anwenden</samp> im Bibliothekenmanager das Neuladen der Bibliothek forciert werden.  
Auf dem BIM-Server sollte nun noch das Projekt umbenant, verschoben, und gesperrt werden. Der BIM-Koordinator kann zum Schluss die aufgeräumte Datei (auch ein Öffnen&Reparieren mag manchmal Wunder zu bewirken) wieder auf den BIM-Server laden. Nach dem Beitreten der Beteiligten kann jetzt wieder normal weiter gearbeitet werden.

Siehe auch [Helpcenter: ARCHICAD Reports 0 Bytes Libraries in Teamwork Project](https://helpcenter.graphisoft.com/knowledgebase/119387/).

Profitipp: Das, was im Moment des Freigebens im Grundrissfenster sichtbar ist, ist auch das, was man sieht, wenn man einem TW-Projekt beitritt.

### Windows
In Firmenumgebungen mit Windows, bei denen die Benutzeraccounts zentral verwaltet werden (_Domäne mit Active Directory_), kann es passieren, dass die Teamwork-Daten korrumpiert werden. Denn: die lokalen TW-Daten liegen im Allgemeinen unter `C:\Users\<name>\Graphisoft\TW Daten`. Es kann helfen den Speicherort zu ändern (sodass die TW-Daten nicht innerhalb des Userordners liegen). Alternativ kann nach dem Verlassen des Projekts der Ordner händisch geleert werden.
