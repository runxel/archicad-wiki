---
layout: default
title: Fortgeschrittene Einstellungen
permalink: /advanced/
nav_order: 180
---

# Spezielle Verzeichnisse
Mit der in 28.1 eingeführten Updateoption lädt Archicad automatisch Updates herunter, wie aus anderen Programmen bekannt.
Der Installer wird in folgendes Verzeichnis gespeichert:
- Mac: `~/Library/Caches/Graphisoft/ACUpdate/`
- Windows: `C:\Users\<UserProfile>\AppData\Local\GRAPHISOFT\ACUpdate`

# Archicad Startfenster
## Einträge editieren/reduzieren
Mit zunehmender Anzahl der Projekte im Startfenster wird es nicht nur unübersichtlich, sondern auch die Performance scheint zu leiden. Nun kann man selbstverständlich diese per X hinter dem Projekt dieses aus der Liste entfernen – nur wer will das schon bei vielen Dateien machen?  
Man kann die Liste komplett leeren, indem man die Datei "Recent Documents (Project).prf" löscht, wenn Archicad nicht läuft.  
Auf Windows liegt sie unter `C:\Users\<user>\AppData\Roaming\Graphisoft\Archicad <version>` 
und auf Mac unter `~/Library/Preferences/Graphisoft/Archicad <version>`.

# Registry
In der Registry (Windows) lassen sich einige Optionen einstellen, die in den normalen Einstellungen nicht zu finden, und oft auch undokumentiert sind. Dennoch kann es sinnvoll sein, hier etwas einzustellen – wenn man weiß, was man tut. Allerdings ist in jedem Fall zu beachten, dass die Einstellungen in der Registry _rein lokal_ sind, was vor allem im Teamwork ein beachtenswerter Faktor ist. Es müssten dann bei _jedem_ Rechner die _selben_ Einstellungen vorgenommen werden, um Konsistenz zu gewährleisten.  
Wie bei allen Registry-Manipulationen gilt: Auf eigene Gefahr und ohne Gewähr.

_Auf dem Mac unterwegs?_  
Auch dort kann man Werte ändern. Statt einer zentralen Aufbewahrung setzt Apple jedoch auf die unübersichtlichen `.plist`s. Zwar liegt die Datei auffindbar unter `~/Library/Preferences/com.graphisoft.AC [version].0.0 XXX v1.plist` ([siehe auch](https://community.graphisoft.com/t5/Installation-update/Altering-ARCHICAD-behavior-Registry-or-Preferences/ta-p/304121).), allerdings sollte man tunlichst diese nicht öffnen und abspeichern. Stattdessen verwendet man den [PrefsEditor](https://apps.tempel.org/PrefsEditor/), um die `.plist`s zu bearbeiten.


<div class="code-example" markdown="1">

Leider bietet Archicad erstmal keine Möglichkeit an, um die (maximal) 4 hinterlegten, zuletzt genutzten Orientierungswinkel der Zeichenfläche zu löschen. Es gibt jedoch eine Methode, die einen Button dafür zu Tage fördert; gut versteckt im "Special Menü". Um daran zu kommen muss der gleichlautende Eintrag in der Registry auf `1` sein.  
In der Arbeitsumgebung taucht dann ganz zum Schluss der Ordner "60 Indiv." auf, mit dem Befehl "Liste Zuletzt verwendet löschen".

</div>
```
HKEY_CURRENT_USER\Software\GRAPHISOFT\ARCHICAD\ARCHICAD <version>\Special Menu
```


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

Ich persönlich habe die Werte für die Segmentierung auf `144` geändert, also vervierfacht. Die Toleranz änderte ich auf `16`, das scheint aber keinen Einfluss zu haben (bzw. ich vermute, dass dieser Wert inaktiv ist, wenn Max und Min Segmentation gleich sind). Die Segmentierung sollte in jedem Fall behutsam angepasst werden, denn damit erhöht man auch die Polygonanzahl. [<sup>Quelle 1</sup>](https://archicad-talk.graphisoft.com/viewtopic.php?t=44270#p222497) [<sup>Quelle 2</sup>](https://archicad-talk.graphisoft.com/viewtopic.php?f=20&t=38490)
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

Die nervigen, mit Archicad 27 eingeführten Online-Templates sollte man in einer Bürostruktur lieber ausblenden. Das ist jedoch gar nicht so einfach. Es finden sich einige passende Einträge: vier TimeOuts und zwei URLs.  
Eine `0` (Null) oder kleine Zahlen als TimeOut bringen noch nicht das gewünschte Ergebnis. Nur den `httpRequest` alleine zu ändern, auch nicht. Weitergehend sollte nämlich der Eintrag `serviceAddress` auf eine ungültige Adresse geändert werden, z.B. `https://update.graphisoft.com/support/archicad/downloads/templates_deaktiviert_.json` – nicht jedoch auf einen leeren String!
</div>
```
HKEY_CURRENT_USER\SOFTWARE\Graphisoft\ARCHICAD\ARCHICAD <version>\Online Hosted Templates
```


<div class="code-example" markdown="1">

Vom letzten Beispiel ausgehend kann auch die Bürovorlage dem User als "zuletzt genutzt" untergejubelt werden. In `Recent templates` folgende Einstellungen:  
- `Use Latest Project Settings` -> dword:00000000
- `Tmpl Number` -> `0`
- `Last selected template` -> "pfad/zum/NAS/mit/Template.tpl"

Den Templatesordner ansich kann man in den Einstellungen von Archicad ändern, aber auch in der Registry global einmal setzen. Unter `Special Folder Locations`:  
`Templates Folder` -> "pfad/zum/NAS-Ordner/"
</div>
```
HKEY_CURRENT_USER\SOFTWARE\Graphisoft\ARCHICAD\ARCHICAD <version>\Recent templates
HKEY_CURRENT_USER\SOFTWARE\Graphisoft\ARCHICAD\ARCHICAD <version>\Special Folder Locations
```


<div class="code-example" markdown="1">

Die PhotoRendering-Palette hat die unangenehme Eigenschaft, manchmal zu "verschwinden" – dabei ist sie eigentlich nur außerhalb des Bildschirms. Ein Neustart des PCs kann zwar helfen, aber der folgende Weg hilft sicher:  
Zunächst testet man, ob durch das löschen der Preferences-Datei `C:\Users\<name>\AppData\Roaming\GRAPHISOFT\ARCHICAD-64 <XXXX>\ARCHICAD Basic.prf` das Problem verschwindet.

Ergibt das noch keine Abhilfe, so löscht man den Schlüssel `RenderingSettingsPaletteRect` in
</div>
```
HKEY_CURRENT_USER\Software\GRAPHISOFT\ARCHICAD\ARCHICAD <version>\Dialog Manager Custom Data
```


<div class="code-example" markdown="1">

Um Hotlinks separat upzudaten setzt man den Schlüssel `Hotlink Module Update` auf `1`. Dadurch erscheint im Hotlink Manager ein neuer Button.  
[<sup>Quelle</sup>](https://community.graphisoft.com/t5/Project-data-BIM/Teamwork-Performance-of-multiple-self-referencing-Hotlinks/m-p/571019#M9667)
</div>
```
HKEY_CURRENT_USER\Software\GRAPHISOFT\ARCHICAD\ARCHICAD <version>\Hotlink
```


<div class="code-example" markdown="1">

Zur Umgehung des Problems einer endlosen Druckerverbindungssuche unter Windows den folgenden Schlüssel von `0` auf `4` setzen.
[<sup>Quelle</sup>](https://community.graphisoft.com/t5/Installation-update/Please-wait-for-printer-connection-or-cancel-connection/m-p/602067/highlight/true#M36996)
</div>
```
HKEY_CURRENT_USER\SOFTWARE\GRAPHISOFT\Archicad\Archicad <version>\PrintPlot\Discard Print Settings
```


<div class="code-example" markdown="1">

Um den Winkel der "Schnellrotationsfunktion" (Quickrotate; in Version 29 neu eingeführt) zu ändern, kann man den folgenden Schlüssel (Stringwert) ändern.  
Standardmäßig ist dieser auf 90° eingestellt.
</div>
```
HKEY_CURRENT_USER\SOFTWARE\GRAPHISOFT\Archicad\Archicad <version>\QuickRotate\QuickRotateAngle
```


# Extending Archicad
Es ist möglich seine eigene Dokumentation (z.B. ein BIM-Playbook) und eigene Links zu Hilfen in Archicad unterbringen. Dazu muss im Archicad-Installationsordner ein neuer Unterordner erstellt werden: Für PDFs `Dokumentation2` und für Links zu Onlineinhalten `WWW-Links2`. (Achtung, diese Namen sind lokalisiert. In der Int'l/US Version heißen die Ordner "Documentation2" und "WWWLinks2".)  
Anschließend muss in den Arbeitsumgebungseinstellungen noch der entsprechende Menüeintrag erzeugt werden. Dieser heißt `PDF2`, bzw. `URL2` respektive.  
[[Quelle](https://community.graphisoft.com/t5/Setup-License-forum/Error-WWWLinks2-amp-Help2/)]
