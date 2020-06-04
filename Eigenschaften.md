---
layout: default
title: Eigenschaften
permalink: /eigenschaften/
---
# Die Eigenschaften

So manches mal wünscht man sich z.B. in der Interaktiven Auswertung ein weiteres Geometrie-Kriterium. Oft gefragt ist, sich Räume über oder unter einer bestimmten Größe anzeigen zu lassen. [AsiaBim](https://asiabim.wordpress.com/2020/04/23/using-geometry-information-as-scheduling-criteria/) zeigt den Trick, einfach eine neue Eigenschaft anzulegen, in der die Größe über eine _Berechnung_ abgefragt wird.
Anschließend lässt sich die neue Eigenschaft als Kriterium verwenden, nicht nur in der IA, sondern auch für Suchen&Aktivieren, die Grafische Überschreibung, Etiketten...!

Ähnlich gelagert ist der Fall der Anzeige von [mehreren Raumflächen](https://asiabim.wordpress.com/2020/04/08/multiple-area-units-in-zones/) in einem Raumstempel. Standardmäßig orientiert sich dieser an der aktuellen Bemaßungseinstellung. Auch hier kommt eine Eigenschaft mit Berechnung zum Einsatz.



### Berechnungen
Die Eigenschaften in Archciad sind ein mächtiges Tool, und mit der Möglichkeit eigene Berechnungen einzubringen, wird es es noch besser.
Im Folgenden ein "Best Of", direkt für Copy&Paste geeignet.

<div class="code-example" markdown="1">

Der folgende Snippet verbindet drei Strings (S1–S3) mit jeweils einem Zeilenumbruch, sofern sie nicht leer sind. In dem Fall wird es übersprungen.

</div>
```
TEXTJOIN ( "
"; TRUE; S1; S2; S3 )
```


<div class="code-example" markdown="1">

Lukas Oelmüller hat einen klugen Weg gefunden, um sich Wände anzeigen zu lassen, die mit hoher Wahrscheinlichkeit von Hand gezeichnet worden sind (sprich eine nicht reguläre Länge besitzen). Der Vorteil ist die Möglichkeit der vielfältigen Nutzung, da sich Eigenschaften sowohl in einem Etikett verwenden lassen, als auch in einer Interaktiven Auswertung.

</div>
```
IF ( 
  STRTONUM ( ( 
    RIGHT ( 
      STR ( ( ( {Property:Wand/Länge der Referenzlinie} * 1000000000 ) / 1 m ); 3 );
    11 ) ) ) 
    = 0; "passt"; 
  CONCAT ( "unpräzise: "; STR ( ( {Property:Wand/Länge der Referenzlinie} / 1 m ); 3 ); 
           "|"; 
           SUBSTITUTE ( 
             SPLITRIGHT ( 
               STR ( ( ( {Property:Wand/Länge der Referenzlinie} * 1000000000 ) / 1 m ); 3 ); 
               ""; 6 ); 
           ","; "" ) 
  ) )
```