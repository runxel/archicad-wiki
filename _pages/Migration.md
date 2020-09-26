---
layout: default
title: Migration
permalink: /migration/
---
# Migrationsleitfaden

Wer updatet, hat die Qual der Wahl: Das aktuelle Projekt bis zum Ende in der Version, mit der es begonnen wurde weiterführen, und so auf Neuerungen verzichten – Oder doch den Weg gehen das Projekt zu migrieren...

## Vorbereitung
- Eine vernünftige Migration benötigt Zeit.  
Wer im akuten Abgabestress ist, verzichtet besser.
- Schau die Änderungen der neuen Archicadversion genau an: Lohnt sich eine Migration für dieses Projekt überhaupt?
- Teamworkprojekte sollten als Soloprojekt migriert werden, und anschließend wieder freigegeben werden.
- Reihenfolge beachten!

## Backup
Wie immer überlebensnotwendig ;)

## Bibliotheken
Archicad nimmt uns die Bibliothekenmigration ab; einfach beim Öffnen der Datei im neuen Archicad die automatische Migration annehmen.

Im Bibliothekenmanager dann zunächst auf fehlende und/oder doppelte Elemente prüfen, und Fehler beheben. An dieser Stelle lohnt sich auch der kritische Blick auf die Eingebettete Bibliothek: Sind tatsächlich alle der vorliegenden Objekte in Verwendung? Bei viel Inhalt kann es sich auch lohnen, diesen in einen externen Ordner zu extrahieren, gerade bei Texturen.

## Klassifizierung und Eigenschaften
Heikle Stelle: Meistens gibt es Anpassungen am Klassifizierungssystem (auch an den IFC Übersetzern!). Wer sein eigenes System verwendet, kann das natürlich weiterhin tun.

Es kann sich jedoch lohnen das Archicad-eigene Klassifizierungssystem zu updaten. Dazu öffnen wir zunächst den Klassifizierungsmanager und ändern dort den Versionsnamen z.B. von 23 auf 24.  
Anschließend können wir aus der mitgelieferten Beispielvorlage das neue Klassifizierungssystem importieren.

## Übersetzer
Anpassungen an den Übersetzern nicht vergessen, oder aus der Beispielvorlage holen.

## Attribute
Eine Migration ist auch immer ein guter Moment, um die Attribute des Projekts zu reorganisieren.

## Hotlinks
Falls im Projekt _Hotlinks_ eingesetzt werden, müssen diese **vor** dem Host-Projekt migriert werden. Man achte besonders auf übereinstimmende Attribute und Klassifizierungen.
