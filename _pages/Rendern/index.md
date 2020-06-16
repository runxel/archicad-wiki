---
layout: default
# parent: Modelltechniken
title: Rendern in Archicad
permalink: /rendern/
has_children: true
---
# Rendern

http://blog.maxwellrender.com/tips/maxwell-render-dos-and-donts/
http://blog.maxwellrender.com/tips/6-beginners-tips-for-an-easy-workflow-in-maxwell-render-by-matteo-tibaldo/




## Licht
Neben _Lichtern_ können in Cinema 4D auch Materialien emmissive sein, also _leuchten_.
Ein Trick für Außenrenderings mit zu dunkel wahrgenommenen Innenräumen ist, den Deckenunterseiten für das Rendering ein leuchtendes Material zu geben.
	� Niemals leuchtende Materialien auf runde/komplexe Objekte pappen
	Bei der Dreiecksvermaschung entstehen dadurch hunderte Fl�chen, damit verl�ngert sich die Renderzeit erheblich

	� EXRs/HDRIs sorgen f�r gutes Licht und sind einfach in der Anwendung

## Größe

<div class="code-example" markdown="1">

Um die nötige Größe eines Renderings in Pixeln zu bestimmen, rechnet man:  
(`2,54` sind ein Zoll in cm; als gewünschte DPI empfiehlt sich für Print `220-300`)

</div>
```
Format in Zentimetern / 2,54 * DPI
```