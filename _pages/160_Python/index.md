---
layout: default
permalink: /python/
title: Python + Archicad
has_children: true
nav_order: 160
---
# Python Verbindung

Von Version 24 an gibt es eine Verbindung zu Archicad, bei der man über ein JSON-Interface Archicad automatisieren und skripten kann (Das ist kein Ersatz für GDL und umgekehrt). Das ist theoretisch mit jeder beliebigen Sprache, die JSON verarbeiten kann und Netzwerktauglich ist, möglich.  

## Start
Zunächst muss [Python](https://www.python.org/) 3.7 oder höher auf dem Rechner installiert sein. Benötigt man mehrere Python Versionen nebeneinander auf seinem PC empfiehlt sich [Miniconda](https://docs.conda.io/en/latest/miniconda.html) – ein Paket- und Umgebungsmanager. (_Achtung_: Archicad findet aktuell keine virtuellen Umgebungen, wenn Anaconda/Miniconda zunächst mit einer Pythonversion > 3.7 installiert wurde. Dass bedeutet allerdings nur, dass die Python-Palette innerhalb Archicads nicht funktioniert. Ein Bugfix ist in Arbeit.)

<details markdown="1">
<summary>Begrifflichkeiten …</summary>

#### Paketmanager
Ein Paketmanger (_package mangager_) ist ein Werkzeug, mit dem Computerprogramme installiert, aktualisiert und entfernt werden können. In diesem Fall sind es Python-Pakete von Drittanbietern. Ein Python-Paket eines Drittanbieters ist jedes Stück Software, das nicht Teil der Python-Standardbibliothek ist.  
Der Standardpaketmanager ist `pip`, der schon lange vor conda existierte und der. Obwohl pip ein gutes Werkzeug ist, werden wir es nicht verwenden, da conda mehr Funktionen enthält und Abhängigkeiten besser auflöst.

#### Umgebungsmanager
Ein Umgebungsmanager (_environment manager_) ist ein Werkzeug, welches eine Umgebung (oft auch als _virtuelle Umgebung_ bezeichnet), also einen völlig separaten und isolierten Bereich Ihres Computers mit einer eigenen Installation von Python und eigenen Paketen von Drittanbietern, die unabhängig von jeder anderen Python-Installation auf Ihrem Rechner sind, erstellt.  
Das ist nötig, wenn man aus Kompatibilitsgründen mehrere verschiedene Versionen eines Pakets oder von Python selbst benötigt.

</details>

Da die Befehle, was Archicad für uns tun soll, über ein JSON-Interface gesendet werden, ließe sich theoretisch jede Sprache verwenden, die Netzwerkbotschaften senden kann. Graphisoft hat aber ein Python-Paket bereitgestellt, werlches die JSON-Ebene wegabstrahiert, sodass auch Anfänger schnell Erfolgserlebnisse erleben.

Dazu installieren wir das [Paket](https://pypi.org/project/archicad/) mittels `pip install archicad`.

Momentan ist die Python-Extension noch als experimentell eingestuft. Daher muss man sie in Archicad 24 in der Arbeitsumgebung unter <samp>Anwender Voreinstellungen > Weitere Optionen > Experimental-Funktionen</samp> erst aktivieren. Anschließend lässt sich über <samp>Fenster > Paletten</samp> die Python-Palette aufrufen.

Um die Skripte zu schreiben und zu bearbeiten, brauchen wir einen Editor. Das ist prinzipiell auch in Notepad möglich, angenehmer ist es aber mit einer IDE wie z.B. [Visual Studio Code](https://code.visualstudio.com/). In VSC lässt sich der Python-Code auch direkt ausführen – man benötigt also die Python-Palette nicht! Stattdessen reicht ein Klick auf das grüne Dreieck oben rechts, und man sieht den Output in der integrierten Konsole.


## Beispiele
Graphisoft hat auf seiner Webseite einige [Beispielskripte](https://graphisoft.com/downloads/python) inklusive Demo-Projekten zusammengetragen. Beides lässt sich nach dem Login mit der GraphisoftID kostenlos herunterladen.

## Details
Zum einen gibt es die allgemeine Dokumentation des [JSON Interfaces](https://archicadapi.graphisoft.com/JSONInterfaceDocumentation/#Introduction).

Ebenso findet sich eine Dokumentation für den [API Python Wrapper](https://archicadapi.graphisoft.com/archicadPythonPackage/archicad.html).
