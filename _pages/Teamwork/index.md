---
layout: default
title: Teamwork
permalink: /teamwork
# has_children: true
---
# Teamwork

## Troubleshooting
Wenn Probleme auftreten, empfiehlt es sich, das Projekt zu verlassen (<samp>Teamwork > Projekt > Teamwork-Projekt verlassen</samp>). Das Verlassen eines Teamwork-Projekts löscht alle lokalen Daten; diese werden bei einem erneuten Beitritt frisch vom Server geladen.  
Nicht gelöscht werden dagegegen jedoch heruntergeladene Bibliotheken. Treten Schwierigkeiten mit Bilbiothekselementen auf, so hilft es unter <samp>Teamwork > Projekt > Lokale-Daten-Manager</samp> die lokale Kopie der Bibliothek zu löschen. Das lässt sich auch im "laufenden Betrieb" erledigen – anschließend kann mit <samp>Neu laden & Anwenden</samp> im Bibliothekenmanager das Neuladen der Bibliothek forciert werden.

Siehe auch [Helpcenter: ARCHICAD Reports 0 Bytes Libraries in Teamwork Project](https://helpcenter.graphisoft.com/knowledgebase/119387/)

In Firmenumgebungen mit Windows, bei denen die Benutzeraccounts zentral verwaltet werden (_Domäne mit Active Directory_), kann es passieren, dass die Teamwork-Daten korrumpiert werden. Denn: die lokalen TW-Daten liegen im Allgmeinen unter `C:\Users\<name>\Graphisoft\TW Daten`. Es kann helfen den Speicherort zu ändern (sodass die TW-Daten nicht innerhalb des Userordners liegen). Alternativ kann nach dem Verlassen des Projekts der Ordner händisch geleert werden.
