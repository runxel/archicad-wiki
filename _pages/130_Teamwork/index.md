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

## Troubleshooting
Wenn Probleme auftreten, empfiehlt es sich, das Projekt zu verlassen (<samp>Teamwork > Projekt > Teamwork-Projekt verlassen</samp>). Das Verlassen eines Teamwork-Projekts löscht alle lokalen Daten; diese werden bei einem erneuten Beitritt frisch vom Server geladen.  
Nicht gelöscht werden dagegegen jedoch heruntergeladene Bibliotheken. Treten Schwierigkeiten mit Bilbiothekselementen auf, so hilft es unter <samp>Teamwork > Projekt > Lokale-Daten-Manager</samp> die lokale Kopie der Bibliothek zu löschen. Das lässt sich auch im "laufenden Betrieb" erledigen – anschließend kann mit <samp>Neu laden & Anwenden</samp> im Bibliothekenmanager das Neuladen der Bibliothek forciert werden.

Siehe auch [Helpcenter: ARCHICAD Reports 0 Bytes Libraries in Teamwork Project](https://helpcenter.graphisoft.com/knowledgebase/119387/)

In Firmenumgebungen mit Windows, bei denen die Benutzeraccounts zentral verwaltet werden (_Domäne mit Active Directory_), kann es passieren, dass die Teamwork-Daten korrumpiert werden. Denn: die lokalen TW-Daten liegen im Allgmeinen unter `C:\Users\<name>\Graphisoft\TW Daten`. Es kann helfen den Speicherort zu ändern (sodass die TW-Daten nicht innerhalb des Userordners liegen). Alternativ kann nach dem Verlassen des Projekts der Ordner händisch geleert werden.
