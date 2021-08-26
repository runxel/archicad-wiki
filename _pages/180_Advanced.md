---
layout: default
title: Fortgeschrittene Einstellungen
permalink: /advanced/
nav_order: 180
---

# Registry
In der Registry (Windows) lassen sich einige Optionen einstellen, die in den normalen Einstellungen nicht zu finden, und oft auch undokumentiert sind. Dennoch kann es sinnvoll sein, hier etwas einzustellen – wenn man weiß, was man tut. Allerdings ist in jedem Fall zu beachten, dass die Einstellungen in der Registry _rein lokal_ sind, was vor allem im Teamwork ein beachtenswerter Faktor ist. Es müssten dann bei _jedem_ Rechner die _selben_ Einstellungen vorgenommen werden, um Konsistenz zu gewährleisten.  
Wie bei allen Registry-Manipulationen gilt: Auf eigene Gefahr und ohne Gewähr.

_Auf dem Mac unterwegs?_  
Auch dort kann man Werte ändern. Statt einer zentralen Aufbewahrung setzt Apple jedoch auf die unübersichtlichen `.plist`s. Im konkreten Fall schaut man in die Datei **`/Library/Preferences/com.graphisoft.AC [version].0.0 XXX v1.plist`**. [Siehe auch.](https://helpcenter.graphisoft.com/knowledgebase/25471)


<div class="code-example" markdown="1">

Im <samp>Multiplizieren</samp> Dialog ist standardmäßig die sehr selten gebrauchte Option <samp>"Pfad auswählen"</samp> angehakt. Das ist recht nervig. Daher sollte man dem Schlüssel `Pick Path` auf `0` setzen. Damit wird diese Option standardmäßig deaktiviert.

</div>
```
HKEY_CURRENT_USER\Software\GRAPHISOFT\ARCHICAD\ARCHICAD <version>\ACUserInterface\MultiplyDialog
```


<div class="code-example" markdown="1">

Der Schlüssel `Better GDL Tube Triangulation` ändert, wie die Längsflächen zwischen Knotenpunkten in zwei Teile trianguliert werden.  
(_Undokumentiert und experimentell. Keine Kompatibilität gewährleistet_) [<sup>Quelle</sup>](https://archicad-talk.graphisoft.com/viewtopic.php?p=317746#p317746) 
</div>
```
HKEY_CURRENT_USER\Software\GRAPHISOFT\ARCHICAD\ARCHICAD <version>\GSModeler
```


<div class="code-example" markdown="1">

Eine der bekanntesten Problematiken von Schalen (Shells) in Archicad ist die festeingestelle Bogenauflösung. Dadurch passiert es, dass zwei miteinander verschnittene Schalen (z.B. eines Kreuzganggewölbe) keinen Scheitelpunkt aufweisen, sondern eine platte Stelle bilden, dessen Rechteck sich auch penetrant im Grundriss abbildet. Es gibt aber eine Art Abhilfe:  
Über folgende Schlüssel kann auf die Bogenauflösung zugegriffen werden:
- `ShellMaxSegmentationNumber` [default: 36]
- `ShellMinSegmentationNumber` [default: 36]
- `ShellSegmentationTolerMM` [default: 100]
Ich persönlich habe die Werte für die Segmentierung auf `144` geändert, also vervierfacht. Die Toleranz änderte ich auf `16`, das scheint aber weniger Einfluss zu haben. Ich konnte dabei keinen Unterschied feststellen. Die Segmentierung sollte in jedem Fall behutsam angepasst werden, denn damit erhöht man auch die Polygonanzahl. [<sup>Quelle 1</sup>](https://archicad-talk.graphisoft.com/viewtopic.php?t=44270#p222497) [<sup>Quelle 2</sup>](https://archicad-talk.graphisoft.com/viewtopic.php?f=20&t=38490)
</div>
```
HKEY_CURRENT_USER\Software\GRAPHISOFT\ARCHICAD\ARCHICAD <version>\GSModeler
```


<div class="code-example" markdown="1">

Archicad führt ab und an "Aufräumarbeiten" durch. Dabei kann es passieren, dass User-gesetzte Anmerkungen in Auswertungen verschwinden. Um dieses Verhalten zu deaktiveren, sollte `CleanupUnusedAnnotations` auf 0 gesetzt werden. Zu verkraftender Nachteil sind leicht größere Dateien.  
Nur für AC 24 Update 4 und Archicad 25 Update 2.  
[<sup>Quelle</sup>](https://archicad-talk.graphisoft.com/viewtopic.php?f=26&t=62958#p332074)
</div>
```
\HKEY_CURRENT_USER\Software\GRAPHISOFT\ARCHICAD\ARCHICAD <version>\Schedule
```


<div class="code-example" markdown="1">

Archicad legt automatisch temporäre Dateien nach dem Muster `PointCloudTempFi_dddddddddd` an, sobald man mit Punktwolken arbeitet. Das soll die Bearbeitungsgeschwindigkeit erhöhen. Hat man sehr viel (32, besser 64+ GB) RAM zur Verfügung lässt sich das vollständige Laden von Punktwolken in den RAM folgendermaßen erzwingen: Den Schlüssel `FilemappingEnabled` auf `0` setzen. [<sup>Quelle</sup>](https://archicad-talk.graphisoft.com/viewtopic.php?f=13&t=70341)
</div>
```
HKEY_CURRENT_USER\SOFTWARE\Graphisoft\ARCHICAD\ARCHICAD <version>\PointCloud
```


<div class="code-example" markdown="1">

Die PhotoRendering-Palette hat die unangenehme Eigenschaft, manchmal zu "verschwinden" – dabei ist sie eigentlich nur außerhalb des Bildschirms. Ein Neustart des PCs kann zwar helfen, aber der folgende Weg hilft sicher:  
Zunächst testet man, ob durch das löschen der Preferences-Datei `C:\Users\<name>\AppData\Roaming\GRAPHISOFT\ARCHICAD-64 <XXXX>\ARCHICAD Basic.prf` das Problem verschwindet.

Ergibt das noch keine Abhilfe, so löscht man den Schlüssel `RenderingSettingsPaletteRect` in
</div>
```
HKEY_CURRENT_USER\Software\GRAPHISOFT\ARCHICAD\ARCHICAD <version>\Dialog Manager Custom Data
```
