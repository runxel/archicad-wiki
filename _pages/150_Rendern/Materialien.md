---
layout: default
parent: Rendern in Archicad
title: Render Materialien
permalink: /rendern/materialien/
---
# Materialien
Render Materialien machen viel aus. Ein sorgsamer Umgang kann das Renderergebnis dramatisch verbessern.

Das [Archicad 23 Handbuch](https://helpcenter.graphisoft.de/handbuecher/handbucher-zu-archicad-23/hilfe-zu-archicad-23/die-benutzeroberfl-che/dialogfenster/oberfl-chenmaterialien/#CSH_1336) dazu.


---

## Materialerstellung
Die Materialerstellung ist der erste Schritt. Ohne gute Materialien sieht das beste Rendering leblos, und im schlimmsten Fall einfach schlecht und unprofessionell aus.

Wer sich mit Cinema4D bereits etwas auskennt, wird sich zum einen in der Materialerstellung von Archicad zurechtfinden, allerdings auch an der einen oder anderen Stelle wundern.

Auffällig ist vor allem, dass Graphisoft sich leider dazu entschlossen hat, nahezu alle Begriffe zu übersetzen. Das verläuft nicht ohne Schmerz, da einerseits die englischen Begriffe feststehend sind – sie sollten wie die meisten anderen digtal-technischen Bezeichnungen nicht eingedeutscht werden. Man verwässert die Terminologie und macht die Kommunikation über das Thema schwierig bis unmöglich. Zudem kann man als deutscher Nutzer nicht "mal eben so" googeln, wenn man an einer Stelle nicht weiterkommt.

Aus diesem Grund erarbeite ich auch eine Übersetzungstabelle, die hoffentlich das Verständnis, sowie das eigenständige Nachschlagen erleichtert.

---

Wenn man in _Cinema4D_ ein neues Material erstellt, hat man eine ganze Palette an Möglichkeiten:
- Neues PBR Material
- Neues Material
- Neuer Shader
- Neues Übermaterial (englisch: _Uber Material_)
- Neues Node Material

Davon fehlt in Archicad jede Spur; man hat keinerlei Auswahlmöglichkeit.
Denn: **Alle** Materialen sind PBR basiert. _PBR_ steht für `Physically Based Rendering`.

Wer eine umfassende und überaus qualitative Quelle sucht, dem sei "The PBR Guide" von Wes McDermott (_Allegorithmic_) ans Herz gelegt. Online zu finden mit [Teil 1](https://academy.substance3d.com/courses/the-pbr-guide-part-1) und [Teil 2](https://academy.substance3d.com/courses/the-pbr-guide-part-2). Dort gibt es auch das als Buch erhätliche PDF.

---

Aus Cinema4D bekannt sind diese Channel in der Materialerstellung:
- Diffusion
- Luminanz
- Transparenz
- Reflexion
- Umgebung
- Nebel
- Bump
- Normal
- Alpha
- Glühen
- Displacement

In Archicad finden sich dann noch zwei weiterer Items:
"Gras" und "Leuchten".
_Gras_ ist ein integrierter Shader für Gras (naheliegend, oder?), kann aber auch für Fell, Teppiche u.ä. verwendet werden.
_Leuchten_ entspricht dem "Illuminance" Tab in Cinema.

----

## Rule of the Power of Two
Man sollte versuchen Bilder als Texturen zu verwenden, deren jeweilige Seitenlängen in Pixeln auf einer Zweierpotenz[<sup>1</sup>](https://gamedev.stackexchange.com/questions/26187/why-are-textures-always-square-powers-of-two-what-if-they-arent) basieren. Das hat den einfachen Grund, dass der Computer intern ohnehin so arbeiten muss. Bilder, die in seiner Abmessung nicht einer Zweierpotenz entsprechen, werden auf die nächste höhere Potenz (siehe unten) gepaddet.  
Daher werden moderne Programme und Hardware alles klaglos schlucken, was man ihnen hinwirft. Aus Performancesicht aber eher ungünstig[<sup>2</sup>](https://www.katsbits.com/tutorials/textures/make-better-textures-correct-size-and-power-of-two.php).

#### Mögliche Abmessungen:
`2^10` = 1024 px  
`2^11` = 2048 px  
`2^12` = 4096 px  

---

## Welche Materialien brauche ich?
Vielleicht ist es dem einen oder anderen schon aufgefallen, dass man bei den professionellen Texturanbietern (die einem das ganze Paket und nicht nur _eine_ gebackene Textur geben) mittlerweile seinen 'Workflow'[<sub>3</sub>](https://help.poliigon.com/en/articles/1712659-the-differences-between-metalness-and-specular-workflows) wählen kann:  
- **Specular** (auch _Glossiness_ genannt) und
- **Metalness** (auch _Roughness_ genannt)

Der _Metalness_ Workflow ist dabei vor allem unter den Real-Time Renderern wie Unreal, Unity, usw. verbreitet. Zwar bieten mittlerweile auch einige der herkömmlichen Renderer Metalness an, Cinema4D jedoch **nicht**. Da ohnehin jeder Renderer mit _Specular_ Maps zurecht kommt, ist man damit stets auf der sicheren Seite. 

---

## Anbieter

- [Poliigon](https://www.poliigon.com/)  
  Kleines Set an kostenlosen Texturpaketen. Ansonsten entweder auf Abo-Basis oder mit Prepaid Credits. Die Texturen sind ausnahmlos qualitativ hochwertig, da sie aus 3D Scans stammen.
  Hat auch HDRIs und 3D Objekte im Angebot.
- [Textures.com](https://www.textures.com/) (ehemals cgtextures.com)  
  Einer der bekanntesten Anbieter mit einer sehr breiten Palette an Texturen, allerdings oft nur Albedo Maps. Mittlerweile finden sich auch etliche 3D Scans in deren Bibliothek.  
  Mit einem kostenlosen Account hat man 15 Credits täglich frei, allerdings ist die Auflösung beschränkt.
- [Arroway](https://www.arroway-textures.ch) bietet eine Vielzahl von Texturen an, die vor allem in Bundles verkauft werden. Dazu gibt es fertige Maxwell Render Materialien. Sehr hilfreich sind die _Reference Guides_, in denen man alle Texturen ausgerendert sieht und schnell gewünschte Materialien findet.  
  Eine weitere Besonderheit sind Photoshop Templates, mit denen man schnell die _Diffuse_ Farben ändern kann.  
  Etwas unscheinbar bietet Arroway aber auch kostenlose Texturen an: Als "low-res sample" ganz unten auf einer Materialseite. Die Maps sind mit 2000px gar nicht einmal so klein, allerdings fehlen dafür manchmal ein/zwei Maps (z.B. Bump) im Download.
- Kostenlose Seiten wie [Lost+Taken](https://lostandtaken.com/) können für Einzelfälle genügen, die Qualität schwankt aber stark und zusätzliche Maps gibt es so gut wie nie.
- Wer es dagegen sehr ernst meint, sollte sich [Quixel](https://quixel.com/) mit ihrer Megascans Bibliothek ansehen. In Qualität und Umfang unerreicht und der Quasi-Goldstandard.
- Bringt man viel Zeit und Muße mit, so lassen sich mitunter bei [DeviantArt](https://www.deviantart.com/deviations/visual-art/resource/digital-art) wahre Schätze heben. Eine Suche nach "<samp>tree cutout</samp>" liefert z.B. ganz überraschend auch Hochwertiges zutage.
