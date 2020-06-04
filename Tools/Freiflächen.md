---
layout: default
title: Freiflächen
parent: tools
permalink: /tools/freiflaeche
---
# Freifläche

### Freiflächen nur mit Daten
Hat man keine Vermesserdaten zur Hand, oder benötigt eine Freifläche mit ganz bestimmten Höhen, so eignet sich die folgende Methode:

![Koordinaten](/img/freifläche-koordinaten.png)
    Nur eine handvoll Daten?

Mit dem Objekt "Koordinaten Bemaßung" zunächst die benötigten Punkte auslegen, die benötigten Höhen eingeben.
Man erstellt sich nun eine _Interaktive Auswertung_, um an die Koordinaten zu kommen. In den Schema-Einstellungen bei "<samp>Felder hinzufügen</samp>" auf das Dreeick und "<samp>Bibiliothekselementparameter</samp>".  
Wir wollen `CustomCoordX`, `CustomCoordY` und `CustomCoordZ` auswerten.

![Parameter](/img/freifläche-ia-zusätzliche-parameter.png)

<!-- Wer möchte, kann sich auch noch die Element ID dazu ausgeben. Tipp: Die lässt sich mit dem [ID Manager](XXXX) schnell anpassen! -->

Die Auswertung wird nun als "Tab Text" gespeichert, und kann postwendend mit "<samp>Ablage > Interoperabilität > Freifläche aus Vermesser-Daten erstellen</samp>" genutzt werden. Übrigens werden so importierte Freiflächen stets konvex. Die so entstehenden Artefakte sollten händisch wieder von der Freifläche (mittels PET-Palette) abgezogen werden.

#### Das Ergebnis
![Ergebnis des Freiflächenimports](/img/freifläche-nach-import.png)

Als Video hier verfügbar (mit zusätzlichem GDL-Scripting Exkurs):
<iframe width="736" height="414" src="https://www.youtube.com/embed/XXGyqwjdUu4" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

(_Dank an Lukas Oelmüller_)


### Höhenlinien
Die [so erstellte](#freiflaechen-nur-mit-daten) Freifläche, aber auch die meisten anderen, haben jedoch eine Schwäche: Die fehlende Höhenlinien. Die Triangulierung der Freifläche ist im 2D schlicht nutzlos (zumindest für eine ordentliche Plandarstellung).

Die eine Möglichkeit besteht darin, die Freifläche als Objekt zu speichern und von einem [anderem Objekt](https://www.archiradar.it/en/3d-objects/membership-objects/archicad/13-contour-maker.html) zu `CALL`en, aber wir wollen gerne etwas, das _live_ ist und Änderungen sofort reflektiert.

Stattdessen erstellen wir uns eine _Morphfläche_. Diese sollte größer sein, als die eigentliche Freifläche. Im 3D _multiplizieren_ wir die Morphfläche in der Z-Richtung, mit dem Abstand, den unsere Höhenlinien haben sollen, z.B. in Meterdistanz, oder wie hier mit 50cm Abstand:

![Morphflächen](/img/freifläche-höhenlinien-morphflächen-3d.png)

Nun kommt eine selten genutzte ***Solid-Element-Operation*** zum Einsatz: Die _Schnittmenge_. Dabei werden die Morphflächen als _Ziel_ (sic!) und die Freifläche als _Operator_ übernommen.
    
![Morphflächen SEO](/img/freifläche-höhenlinien-morp-nach-seo.png)

Und im 2D sieht es dann so aus:

![Höhenlinien und Freifläche](/img/freifläche-höhenlinien-fläche-morphs.png)

Die Morphflächen sind eingestellt als "Projiziert mit Untersicht". Die über der aktuellen Schnittebene liegenden Höhenlinien sind hier im Beispiel gestrichelt und in violett.

![Höhenlinien](/img/freifläche-höhenlinien-final.png)

Man bemerke, dass die Ebene der Freifläche inzwischen ausgeblendet wurde – die Freifläche muss im Grundriss nicht mehr auftauchen, und dennoch werden alle Änderungen an ihr in den Morph-Höhenlinien reflektiert.

![Schnittfläche](/img/freifläche-höhenlinien-mit-schnitt.png)

Auch eine akkurate Schnittfläche lässt sich so erstellen: Die Morphfläche wurde im aktuellen Geschoss auf Meterhöhe gehoben und bekam eine Deckschraffur zugewiesen.

Mit wenig Fantasie lassen sich noch ganz andere Verwendungen dieser Methode erdenken. Seien es nun Geschosshöhen im Städtebau, oder Meterrisse im 3D, etc...


### Morphersatz
Zugegeben: Morphs sind nicht das gerade das schönste Werkzeug in Archicad. Es hat seine [Berechtigung](#höhenlinien), aber für manche Anwendungsfälle ist es leichter, andere Werkzeuge zu verwenden. Die hohe Flexibilität Archicads ist einer der größten Vorteile gegenüber anderen CAD-Systemen.  
Für die Häuser einer städtebaulichen Umgebung ziehe ich es z.B. vor Freiflächen zu nehmen – Dachformen sind so ein Kinderspiel!
