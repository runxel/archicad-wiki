---
layout: default
parent: Rendern in Archicad
title: Tipps & Tricks
permalink: /rendern/tips
---
# Tipps & Tricks zum Rendern in Archicad

## Größe

<div class="code-example" markdown="1">

Um die nötige Größe eines Renderings in Pixeln zu bestimmen, rechnet man:  
(`2,54` sind ein Zoll in cm; als gewünschte DPI empfiehlt sich für Print `220-300`)

</div>
```
Format in Zentimetern / 2,54 * DPI
```

## Speichern
Folgendes gibt es beim Speichern zu beachten: Um auch den _Alphakanal_ zu erhalten, wählen wir als Format `.tif` und klicken dann auf "Optionen". Dort wählt man dann "Farbe mit Alpha-Kanal" oder "Hohe Farbgenauigkeit mit Alphakanal" aus. <small>(Nur echt mit unterschiedlicher Schreibweise!)</small>  
"Hohe Farbgenauigkeit" speichert das Bild mit 32-bit Farbtiefe.
