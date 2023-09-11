---
layout: default
parent: Rendern in Archicad
title: Perspektive matchen
permalink: /rendern/perspektivmatch/
---
# Perspektive zu Bild matchen
Archicad kennt nur einen "<samp>Blickwinkel</samp>". (Korrekt wäre eigentlich der Begriff Öffnungswinkel.)

## Händisch
Zunächst müssen wir die **Sensorgröße** der Kamera herausfinden:
Z.B. ergibt sich für eine _Nikon D5000_, dass der verbaute Sensor ein _APS-C_ ist.
Anschließend lesen wir aus den EXIF Daten die im Bild genutzte **Brennweite** aus. Wichtig ist, dass wir das Bild **nicht** beschneiden, denn ansonsten funktioniert die Berechnung nicht. Beispielsweise erhalten wir den Wert 18 mm. 
Beides zusammen können wir in diesem [Onlinetool](https://www.vision-doctor.com/optik-berechnungen/oeffnungswinkel-berechnen.html) eingeben und erhalten den Öffnungsweinkel von hier 66.7°. Damit haben wir alle Voraussetzungen, um unser Gebäude händisch in die Perspektive einzufügen in Archicad.

## Automatisch
Zwar liefert Archicad mit "Perspektive einpassen" auch ein Tool mit, um die Perspektive im Viewport einzupassen; oftmals funktioniert das erfährungsgemäß jedoch nur semi-gut.  
Es gibt dafür ein gutes Erklärvideo – leider auf italienisch:  
<iframe width="640" height="360" src="https://www.youtube.com/embed/Xr9RmU2jlE4?si=EjeIhx-WJ0vQeBE-" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

Alternativ bietet sich [fSpy](https://fspy.io/) an.

