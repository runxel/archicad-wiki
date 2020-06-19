---
layout: default
parent: Modelltechniken
title: Workarounds
permalink: /workarounds/
---
# Cheats & Workarounds

## Symbollinien
Zieht man eine Polylinie mit einem Symbollinientyp, passiert es leicht, dass die Ecken nicht besonders ansehnlich sind, denn die Linie muss ja irgendwie um die Ecke geführt werden. Diese Glitches kann man leicht dadurch loswerden, dass man die Eckpunkte leicht verrundet. Tipp: Gibt man als Verrundungsradius `0` ein, wird Archicad automatisch die kleinstmögliche Verrundung durchführen.

![Runde Ecken](../img/runde-polylinien-ecke.png)

## Abgeschrägte Wände
Für Wände, die _einseitig_ in ihrer Höhe abgeschrägt sind, kann man ein Fenster verwenden, z.B. das [FreeFormWindow](https://bimcomponents.com/GSM/Details/8405).
Legt man ein dreieckiges Fenster (natürlich ohne Rahmen usw.) in die Ecke – in der _Längsansicht_ gesehen – der Wand, schneidet es die Schräge heraus. Man erhält auf diese Weise sogar eine korrekte Grundrissdarstellung dazu.

![Wand abgeschrägt](../img/wand-schräg-1.png)

![Wand abgeschrägt: Korrekte Darstellung im Grundriss](../img/wand-schräg-2-grundriss.png)
    Korrekte Darstellung im Grundriss

Anschließend lassen sich problemlos – korrekte Schnittdarstellung inkl. – Geländer auf die Wand legen. Auch möglich ist die Verwendung von Profilen im Gurt oder Handlauf des Geländerwerkzeugs, um so z.B. einen Abschluss aus Formsteinen zu modellieren.

![Wand abgeschrägt mit Geländer](../img/wand-schräg-3-geländer.png)

![Abgeschrägte Wand mit Formsteinen](../img/wand-schräg-4-formstein.png)

![Abgeschrägte Wand mit Formsteinen, Profilemanager](../img/wand-schräg-5-profil.png)

## Bodentiefe Fenster
Die sicherste Variante für Bodentiefe Fenster, bei der auch die Wohnflächenberechnung stimmt, ist die Aktivierung der _"Heizkörpernische"_ im Fensterobjekt. Es gibt aber auch [noch andere Wege](https://hey-archicad.de/2019/11/22/bodentiefe-fenster/).

## Punktbereinigung
Im Normalfall möchte man seine Linien und Flächen gerne so clean wie möglich halten. Kolineare Punkte sind, sofern nicht ein bestimmter Grund dafür existiert, nicht erwünscht. Das manuelle Löschen von Punkten (Einen _Node_ auf einen anderen ziehen) ist recht mühsam.  
Es gibt jedoch einen Trick, um sich gleich einer ganze Reihe an Punkten zu entledigen. Das funktioniert sogar, wenn die Punkte nicht kolinear sind:

![Punktbereinigung](../img/punktbereinigung-1.png)

Wir ziehen uns einen Markierungsrahmen um die Punkte, die wir loswerden wollen. Anschließend verwenden den sonst eher sparsam eingesetzten Befehl <samp>Längenänderung</samp>, mit dem wir den Punkt im Beispiel ganz links auf den Eckpunkt (der nicht im Markierungsrahmen steckt!) rechts ziehen.

![Punktbereinigung](../img/punktbereinigung-2-howto.png)

#### Das Ergebnis
... kann sich sehen lassen:

![Punktbereinigung](../img/punktbereinigung-3-ergebnis.png)

Tipp: Der Markierungsrahmen hat auch eine polygonale Methode!
