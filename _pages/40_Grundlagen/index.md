---
layout: default
title: Grundlagen
permalink: /basis/
nav_order: 40
has_children: true
---
# Grundlagen

Old, but [Gold](http://web.archive.org/web/20140704092311/http://www.aecbytes.com/tipsandtricks/2011/issue56-archicad.html)! Eric Bobrow zeigt uns 7 die Schlüsselstrategien, um das meiste aus Archicad herauszuholen.  
<small>(Als historische Referenz ist die ["Tips and Tricks"](http://web.archive.org/web/20130820044938/http://aecbytes.com/tipsandtricks.html) Reihe von AECbytes generell interessant.)</small>


## Darstellung in Archicad

**Was** dargestellt wird, regelt die _**Ebenenkombination**_.  
**Wie viel** gezeigt wird, legt man in der _**Strukturdarstellung**_ fest.  
**Wann** (Zeitstrahl) etwas dargestellt wird, regelt der _**Umbaufilter**_, der die einzige Sichtbarkeitssteuerung neben den Ebenen in AC darstellt.  
**Wie** (Detaillevel) es dargestellt wird, regelt die _**Modelldarstellung**_. (MVO betrifft auch das _Was_, indem die Sichtbarkeit von "ebenenlosen" Elementen, wie Subelemente und Öffnungen geregelt wird.)  
**Wie** (Aussehen) die Elemente erscheinen, regeln _**Stiftset**_ und _**Grafische Überschreibung**_, welche genau das macht, was der Name suggeriert.  
**Wo** (horizontal) geschnitten wird, regelt die _**Grundriss-Schnittebene**_.  

_Was_ und _Wann_ betreffen auch die Verschneidungen von Modellelementen.

<br>

Zeichnungen sollten über die [Ebenen](https://onland.info/archives/2005/03/layer_theory.php) gemanaged werden und Daten über Klassifikation + Element IDs; Änderungen an dem Einen sollten keine Auswirkungen auf das andere haben.

> Accuracy is first. Completeness is second. Beauty is Third.  

[Quelle](https://onland.info/archives/2006/03/beauty_is_third.php) 


## Projektlage
In der Projektlage wird eingetragen, wo der globale Archicad-Nullpunkt sich in der echten Welt befindet. So können Breiten- und Längengrad, und die Nordrichung eingetragen werden. Auch die Höhenlage in Bezug zum Meeresspiegel* kann hier eingetragen werden. Damit ist das Delta des Archicad-Nullpunkts zum Meeresspiegel gemeint. Beispielsweise bedeutet ein Wert von `-1.0`, dass der AC-Nullpunkt einen Meter unter der Normalnullreferenz liegt. Betrachtet man es andersherum, kann es hier schnell zu einem Vorzeichenfehler kommen.  
Siehe auch [Do's and Dont's](dos-donts/#nullpunkt)  
*Zum Thema Meerespiegel: Natürlich ist die Bezeichnung nicht korrekt, aber es versteht so jeder, was gemeint ist. Tatsächlich ist seit 2016 die _Höhe über Normalhöhennull (NHN) im DHHN2016_ ausschlaggebend. Mehr [Infos](https://fernkorn-vermessung.de/blog/2020/10/22/hohe-uber-nn-nhn-wenn-ein-buchstabe-fur-verwirrung-sorgt/).


## Verschneidung
In Archicad gilt als Grundvoraussetzung für Verschneidungen (oder Verbindungen), dass die Konstruktions-Elemente im Raum zusammentreffen müssen. Alle Konstruktions-Elemente werden in allen Sichten bereinigt, sofern sie sich durchdringen. Im Fall von kollidierenden Schalen, Morphs und Dächern müssen diese außerdem mit den Befehlen des Verbindungsmenüs [verschmolzen](https://help.graphisoft.com/AC/23/GER/_AC23_Help/040_ElementsVB/040_ElementsVB-107.htm#XREF_29201_Merge_Elements) oder [getrimmt](https://help.graphisoft.com/AC/23/GER/_AC23_Help/040_ElementsVB/040_ElementsVB-100.htm#XREF_73985_Trim_Elements_with) werden.

Die resultierende Verschneidung hängt von den _Baustoff-Prioritäten_ der Elemente ab. Das Element bzw. die Schicht mit dem Baustoff der höheren Priorität schneidet das Element mit der niedrigeren Priorität. Dies passiert bei den folgenden Elementen: Wand, Träger, Stütze, Decke, Dach, Schale, Morph.

### Automatische Verschneidungen in Archicad

<table>
<thead>
  <tr>
    <th class="header"></th>
    <th class="header">Wand<br></th>
    <th class="header">Unterzug</th>
    <th class="header">Stütze</th>
    <th class="header">Decke</th>
    <th class="header">Dach</th>
    <th class="header">Schale</th>
    <th class="header">Morph</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="header right">Wand<br></td>
    <td class="center green">Kollision + Ref.-Linie</td>
    <td class="center green">Kollision</td>
    <td class="center green">Kollision oder Umwicklung</td>
    <td class="center green">Kollision</td>
    <td class="center blue">Verbinden</td>
    <td class="center blue">Verbinden</td>
    <td class="center blue">Verbinden</td>
  </tr>
  <tr>
    <td class="header right">Unterzug</td>
    <td class=""></td>
    <td class="center green">Kollision oder Ref.-Linie</td>
    <td class="center green">Kollision</td>
    <td class="center green">Kollision</td>
    <td class="center blue">Verbinden<br></td>
    <td class="center blue">Verbinden</td>
    <td class="center blue">Verbinden</td>
  </tr>
  <tr>
    <td class="header right">Stütze</td>
    <td class=""></td>
    <td class=""></td>
    <td class="center red">SEO</td>
    <td class="center green">Kollision</td>
    <td class="center blue">Verbinden</td>
    <td class="center blue">Verbinden</td>
    <td class="center blue">Verbinden</td>
  </tr>
  <tr>
    <td class="header right">Decke</td>
    <td class=""></td>
    <td class=""></td>
    <td class=""></td>
    <td class="center red">SEO<br></td>
    <td class="center blue">Verbinden</td>
    <td class="center blue">Verbinden</td>
    <td class="center blue">Verbinden</td>
  </tr>
  <tr>
    <td class="header right">Dach</td>
    <td class=""></td>
    <td class=""></td>
    <td class=""></td>
    <td class=""></td>
    <td class="center blue">Verbinden</td>
    <td class="center blue">Verbinden</td>
    <td class="center blue">Verbinden</td>
  </tr>
  <tr>
    <td class="header right">Schale</td>
    <td class=""></td>
    <td class=""></td>
    <td class=""></td>
    <td class=""></td>
    <td class=""></td>
    <td class="center blue">Verbinden</td>
    <td class="center blue">Verbinden</td>
  </tr>
  <tr>
    <td class="header right">Morph</td>
    <td class=""></td>
    <td class=""></td>
    <td class=""></td>
    <td class=""></td>
    <td class=""></td>
    <td class=""></td>
    <td class="center blue">Verbinden</td>
  </tr>
</tbody>
</table>

- Grün: Automatische Verschneidung nach Baustoff-Priorität auf Schichtniveau
- Blau: Verschneidung nach Baustoff-Prioriät auf Schichtniveau, erfordert aber Verschmelzen/Anpassen
- Rot: Nur auf Elementebene mittels Solid Elements Operations

Anmerkung: Die symbolische Grundriss-Darstellung "überschreibt" eine echte 3D-Projektion. Ansonsten ist die Darstellung aber in allen Sichten korrekt und übereinstimmend.  
_Ebenen-Verschneidungsgruppen_ bieten eine zusätzliche Möglichkeit der Steuerung. Elemente, deren Ebenen unterschiedliche Verschneidungsnummern haben, verschneiden sich nie. Sonderfall: Elemente in der Ebene mit der Verschneidungsgruppennummer `0` (null) verschneiden nicht einmal untereinander.


## Auswählen
Wenn man ein Werkzeug ausgewählt hat, lassen sich trotzdem Elemente selektieren, indem man die <kbd>⇑ Umschalt</kbd>-Taste drückt. Dabei erhalten die Elemente des aktuellen Werkzeugtyps vorrang vor anderen, selbst wenn sie sich in der Darstellungsreihenfolge dahinter befinden.


## Favoriten
Gute Favoriten anzulegen ist eine Kunst, aber hilfreich! Solange man alleine arbeitet, ist das Unterfangen ohnehin unproblematisch, im Teamwork wird es schwieriger (Oft verwendet nur der Ersteller selbst die Favoriten). Bibliothekselemente behalten immer ihre Grundeinstellung – dort hilft nur der Favorit.  
Die _Grundeinstellung aller Werkzeuge_ ist die letzte Einstellung vor dem Sichern. Folgender Workflow hat sich etabliert: alle Werkzeuge einmal in ihrer gewünschten "Vorlagengrundeinstellung" platzieren, anschließend mit der Pipette einmal alles aufnehmen. Alle Elemente löschen und als `.tpl` anlegen.


## Troubleshooting

["The solution is probably easy but not obvious."](https://blog.graphisoftus.com/tips-and-tricks/easy-but-not-obvious)

- Schlechte Performance im 3D – Das kann, neben anderen Gründen wie riesigen Texturen oder unsachgemäßer Anwendung von SEO, an einer einer übermäßigen Anzahl an Polygonen liegen. Siehe dazu [AsiaBIM](https://asiabim.wordpress.com/2020/06/05/polygon-reduction-in-archicad/)
- Die Nachricht `Die Festplatte ist voll. Archicad muss jetzt geschlossen werden`:
    1. Klicken Sie nicht auf "OK", denn dann schließt sich Archicad sofort.
    1. Gehen Sie im Explorer zu `C:/Users/<username>/GRAPHISOFT/Autosave-<Archicad version>` / im Finder zu `/Users/<username> /Library/Application Support/GRAPHISOFT/AutoSave-<Archicad version>`
    1. Kopieren Sie den Inhalt an eine andere Stelle.
    1. Es müsste ein Unterordner namens `@ODB_Database_<nummer>` existieren. In diesem Ordner liegt eine Datei mit der Endung `.fbd`.
    1. Ändern Sie die Endung zu `.pln`.
    1. Öffnen Sie eine neue Archicad-Instanz, allerdings _nicht_ mit Doppelklick auf die eben "erstellte" Datei. Stattdessen wählen Sie diese zum `Öffnen & Reparieren` aus. Archicad sollte nun den letzten Schritt des Autosaves für Sie wiederhergestellt haben.
- Wiederherstellen von abgestürzten Dateien:
  - [AsiaBIM](https://asiabim.wordpress.com/2016/10/04/data-safety-file-recovery-and-troubleshooting/)
  - [GS Guideline](https://community.graphisoft.com/t5/Project-Management-articles/File-Damage-or-Corruption-Troubleshooting-Guide/ta-p/304096)

## Sonstiges
- Der [intelligente Cursor](https://helpcenter.graphisoft.com/user-guide/88455/) in all seinen Facetten erklärt. 
