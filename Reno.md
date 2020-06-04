---
layout: default
title: Umbaufilter in Archicad
permalink: /reno/
---
# Der Umbaufilter in Archicad

## Darstellung
Um transparente Abbruchdarstellungen in den Schnitten/Ansichten zu erreichen, gibt es folenden Workaround:

1. "Transparenz" in den "Ansichts-Einstellungen" aktivieren
1. Damit nun nicht alle Elemente hinter den Fenstern angezeigt werden die "Durchlässigkeit" des Fensterglasmaterials auf `49` stellen – dies gilt in der Ansichtsdarstellung als nicht transparent und wird opak dargestellt.
1. Ein gelbes Abbruchmaterial mit einem sehr hohen Transparenzfaktor (sprich über `50`) erstellen.
1. In den Umbau-Überschreibungsstilen der Grafischen Überschreibung bei Abbruch die "Oberfläche" mit dem neuen Abbruchmaterial überschreiben

Wenn jetzt die Abbruchelemente in der Ansicht/im Schnitt überschrieben werden, sieht man gelbe Linien und transparente 3D Elemente mit den dahinterliegenden Neubauelementen.
