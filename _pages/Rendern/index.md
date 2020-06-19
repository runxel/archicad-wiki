---
layout: default
title: Rendern in Archicad
permalink: /rendern/
has_children: true
---
# Rendern in Archicad

> Cinerender for the curious

Der in Archicad integrierte _Cinerenderer_ aus Cinema 4D (vom ebenfalls zum Nemetschek-Konzern gehörenden Maxon) ist eine mächtige Geschichte, die aber auf den zweiten Blick, nachdem man auf die "Erweiterten Optionen" geschaut hat, ganz schön einschüchternd sein kann.





---

An dieser Stelle sei noch eine Hommage an Dwight Atkinson ausgesprochen, der aus der alten Lightworks Engine wahre Wunder hervorgezaubert hat, und sein Wissen [teilte](https://books.google.de/books/about/LightWorks_in_ArchiCAD.html?id=PlcNPQAACAAJ&redir_esc=y).

---

Natürlich gibt es auf dem Markt noch zahlreiche weitere Renderer, wie Lumion, Twinmotion, Maxwell, Octane, ... usw. Für manche davon gibt es dedizierte Plugins, für andere muss das 3D Modell erst exportiert werden.



## Was nicht geht
Der integrierte Cinerenderer hat einige Einschränkungen gegenüber der "Vollversion" in Cinema4D:
- nicht rendernde Oberflächen  
  (wird z.B für lichtschluckende Oberflächen verwendet, die Bereiche künstlich verschatten sollen)
- fehlende Channels  
  (z.B. ZBuffer, Material-ID)
- axonometrische 3D-Ansichten (Monometrische Axonometrien und Axonometrien mit verzerrten Achsen)


## Troubleshooting

• Die Rendervorschau sieht anders aus, als das fertige Rendering?!?
Das liegt daran, dass die Vorschau nicht alle aktuellen Einstellungen übernimmt, sondern vereinfachte Einstellungen einsetzt. Unter anderem[<sub>Quelle</sub>](https://archicad-talk.graphisoft.com/viewtopic.php?t=47865)
- Optionen > Allgemeine Optionen > Spiegelung nur von Boden/Himmel → An –– diese Einstellung sorgt dafür, dass nur der Himmel reflektiert wird, nicht die Umgebung
- Optionen > Allgemeine Optionen > Schwellwert → 20% –– dadurch werden nur Materialien mit hohen Werten bei Reflexion und Helligkeit Licht reflektieren




<!-- http://blog.maxwellrender.com/tips/maxwell-render-dos-and-donts/
http://blog.maxwellrender.com/tips/6-beginners-tips-for-an-easy-workflow-in-maxwell-render-by-matteo-tibaldo/ -->
