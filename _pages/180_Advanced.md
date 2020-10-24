---
layout: default
title: Fortgeschrittene Einstellungen
permalink: /advanced/
nav_order: 180
---

# Registry
In der Registry lassen sich einige Optionen einstellen, die in den normalen Einstellungen nicht zu finden, und oft auch undokumentiert sind. Dennoch kann es sinnvoll sein, hier etwas einzustellen – wenn man weiß, was man tut. Allerdings ist in jedem Fall zu beachten, dass die Einstellungen in der Registry _rein lokal_ sind.


<div class="code-example" markdown="1">

Im <samp>Multiplizieren</samp> Dialog ist standardmäßig die sehr selten gebrauchte Option <samp>"Pfad auswählen"</samp> angehakt. Das ist recht nervig. Daher sollte man dem Schlüssel `Pick Path` auf `0` setzen. Damit wird diese Option deaktiviert.

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
HKEY_CURRENT_USER\Software\GRAPHISOFT\ARCHICAD\ARCHICAD <XXXX>\Dialog Manager Custom Data
```
