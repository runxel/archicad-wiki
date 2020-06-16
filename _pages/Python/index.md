---
layout: default
permalink: /python/
title: Python + Archicad
# has_children: true
---
# Python Verbindung

Von Version 24 an gibt es eine Verbindung zu Archicad, bei der man über ein JSON-Interface Archicad automatisieren und skripten kann (Das ist kein Ersatz für GDL und umgekehrt). Das ist theoretisch mit jeder beliebigen Sprache, die JSON verarbeiten kann und Netzwerktauglich ist, möglich.  
Graphisoft liefert jedoch eine offizielle [Python API](https://archicadapi.graphisoft.com/JSONInterfaceDocumentation/#Introduction) aus, die einem einiges abnimmt. 
Das ganze funktioniert entweder über die mitgelieferte Python-Palette, oder aber, da die Kommunikation über HTTP läuft, von extern angeschoben.
Einzige Voraussetzung ist ein installiertes Python 3.7 oder höher.