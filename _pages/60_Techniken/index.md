---
layout: default
permalink: /techniken/
title: Modelltechniken
nav_order: 60
has_children: true
has_toc: false
---
# Techniken in Archicad

Ein großer Vorteil von Archicad ist die Flexibilität der Mittel: Lässt sich ein Problem nicht auf herkömmliche Weise lösen, kann es helfen das Problem von einem anderen Winkel aus zu sehen. Grundsätzlich ist man zwar an bestimmte Parameter gebunden (z.B. kann eine Wand zwar schräggestellt werden, aber nicht liegen; das wäre dann ja eine Decke), aber es führen mehrere Wege nach Rom.

Im Folgenden stelle ich einige der klassischen Techniken vor, die nicht alle unbedingt im Handbuch stehen, aber zum Handwerkszeug gehören sollten.

Grundlage zum Thema ['Verschneidung'](https://helpcenter.graphisoft.de/handbuecher/handbucher-zu-archicad-23/hilfe-zu-archicad-23/elemente-des-virtuellen-geb-udes/konstruktions-elemente/element-verschneidungen/spezifische-elementverschneidungen-und-verbindungen/).

<br>

### Achsen-Management
Ein sicherer Umgang mit den blauen Referenzachsen ist unerlässlich, denn sie sind der Schlüssel zur korrekter Darstellung, wie z.B. Wandverschneidungen. Durch geschicktes Verschieben oder Manipulieren der Achsen unter Zuhilfenahme der [Anschlussreihenfolge](/tools/wand/#anschlussreihenfolge) sind viele eher triviale Probleme bereits lösbar.  
Große Hilfe ist dabei der Befehl "<samp>Wand-Referenzlinie ändern</samp>".  


### Extrusionrichtung ändern
Eine klassische Technik, um Stellen zu modellieren, die sonst nicht so leicht nachzubauen wären. Dabei dreht man die Extrusionsrichtung (meistens) lotrecht zur eigentlichen, "logischen" Richtung.
Beispiel: Das Endstück eines Balken soll besonders geformt sein, auf GDL verzichtet werden. Lösung: Im Profilmanager die Längsansicht zeichnen und dann quer zum Balken platzieren. Eine andere Möglichkeit wäre der Einsatz [schneidender Luft](#schneidende-luft).

![Extrusionsrichtung ändern um Balkenteile zu modellieren](../img/techniken-extrusionsrichtung-ändern.png)

### Stützen zur Verschneidung
Diese Technik ist nach dem "Erfinder" [James Murray](https://www.onland.info/archives/2010/07/fixing_wall_corners_with_columns.php) auch als "Classical Murray" bekannt. Das ist vor allem nützlich, wenn man komplexe Wandverschneidungen auflösen muss. Dabei wird am Schnittpunkt eine wandhohe Stütze mit einem Profil platziert. Vorteil ist dabei die tadellose Darstellung in 2D und 3D.  
Archicad hat in den letzten Versionen einige Verbesserungen bei den Wandverschneidungen erfahren, sodass diese Technik zum Glück mittlweile seltener nötig ist, weil T/Y- und K-Verbindungen OOTB korrekt verschneiden.

### Schneidende Luft
Seit Archicad 17 gibt es die neuen Baustoffe, welche sich automatisch miteinander auf Grundlage einer Priorität verschneiden.
Dieses System lässt sich ausnutzen, in dem man sich einen Baustoff erstellt, der im 3D nicht sichtbar ist (eben z.B. Luft), und eine sehr hohe Verschneidungspriorität besitzt. 
So lassen sich in der überwiegenden Anzahl aller Fälle der Einsatz von SEO vermeiden.

![Schneidende Luft zum Modellieren](../img/techniken-schneidende-luft.png)
    Ähnliche Technik wie oben, nur wird diesmal nicht hinzugefügt, sondern weggenommen.

Siehe auch [Jared Banks](http://www.shoegnome.com/2015/12/17/control-joints-strong-air-archicad/)

Tipp: Es muss nicht immer gleich eine dieser hier vorgestllten Methoden sein! So manches lässt sich in den Werkzeugen selbst lösen, wie z.B. mit einem verjüngten Segment im Träger-Tool (ab Archicad 23):

![Verjüngtes Segment Trägerwerkzeug](../img/techniken-tools-eigen.png)

### Profile
Profile gehören nicht erst seit den Modifikatoren zum versatilsten, was Archicad zu bieten hat. Ein extensiver Einsatz ist empfehlenswert!  
Ein paar Anmerkungen:
- Im Profilmanager ist der Ursprungspunkt wesentlich, denn er markiert die Lage der Referenzlinie. Verinfacht gesagt ist für Wände **außen** _links_ (siehe [Handbuch](https://helpcenter.graphisoft.de/handbuecher/handbucher-zu-archicad-22/hilfe-zu-archicad-22/elemente-des-virtuellen-geb-udes/konstruktions-elemente/komplexe-profile/profilursprung-im-profil-manager/) oder [auch](https://www.youtube.com/watch?v=Rowz4fWECo4))  
- Es kann sinnvoll sein, Luft in Profilen mitzumodellieren, siehe auch [schneidende Luft](#Schneidende-Luft)


### SEO
_Solid Element Operation_  
Achtung! Bauteile, die in einer SEO eingesetzt werden, nehmen trotzdem weiterhin an der prioritätsbasierten Baustoffverschneidung teil! Das kann ungewollte Auswirkungen haben, zumal da die SEO-Körper nicht gelöscht werden dürfen (SEO ist _immer_ live und non-destruktiv). Es ist daher unbedingt empfehlenswert
- einen SEO-Baustoff anzulegen, mit einer sehr geringen Priorität, und
- alle SEO-Körper, die rein dem Abzug dienen, und sonst nicht sichtbar sein sollen, auf eine eigene Ebene mit der Verschneidungszahl `0` zu legen, um so auch eine Verschneidung der SEO-Körper untereinander zu verhindern.
