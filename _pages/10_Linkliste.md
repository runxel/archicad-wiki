---
layout: default
title: Linkliste
permalink: /links
nav_order: 10
---
# Linkliste

Ein Sammelort für Links, mehr oder weniger sortiert. Muss nicht immer zwangsläufig direkt mit Archicad zusammenhängen.

---

## Offizielle Archicad Webseiten
- [Helpcenter Int'l](https://helpcenter.graphisoft.com/)
- [Helpcenter DE](https://helpcenter.graphisoft.de/)
- [Deutsches Archicad-Forum](https://forum.graphisoft.de/)
- [Internationales Forum](https://archicad-talk.graphisoft.com/)

## Die wichtigsten Blogs
- [Shoegnome](http://www.shoegnome.com/writing/)
- [On Land](https://onland.info)
- [WWA BIM](https://wwabim.wordpress.com/)
- [Asiabim](https://asiabim.wordpress.com/)

- [Graphisoft US blog](https://blog.graphisoftus.com/blog)
- [Bim6<sup>x</sup>](https://bim6x.com/blog)
- [ArchicadUser](https://www.archicaduser.de/)
- [Archicadstuff](http://archicadstuff.blogspot.com/)
- [nb Bim](https://nbbim.wordpress.com/blog-posts/)
- [Hey Archicad](https://hey-archicad.de/)

---

## Infos
- [DIN Formate](https://www.din-formate.de/)
- [Papersizes.io](https://papersizes.io/)

## Texturen
Siehe dazu [hier](/rendern/materialien/#anbieter)

## Stockbilder
- [Unsplash](https://unsplash.com/)
- [Pexels](https://www.pexels.com/)
- [freeimages](https://de.freeimages.com/)
- [Pixabay](https://pixabay.com/)


## Archicad Objekte (GDL)
- [BIMcomponents](https://bimcomponents.com/)
- [ArchiBase](https://archibase.co/)
- [ArchiUp](https://archiup.com/en/) – Echte Produkte, aber teils nicht als `.gsm`
- [Modlar](https://www.modlar.com/) – Bringt auch News und einen Podcast
- [Caroma](https://specify.caroma.com.au/bim-library-landing/archicad) – Speziell fürs Bad
- [Martele](https://www.martela.com/downloads/3d-objects-and-material-libraries)
- [ArchiRadar](https://www.archiradar.it/en/3d-objects/free-objects/viewcategory/1-archicad.html) <sup>teils $$$</sup>
- [Bim&Co](https://www.bimandco.com/en/bim-objects)
- [NBS Library](https://www.nationalbimlibrary.com/en/archicad/) – vor allem interessant für Anwender aus UK/Kanada/Australien
- [Éptár](https://www.eptar.hu/solutions_downloads?lang=en) <sup>$$$</sup>
- [OpenGDL](http://www.opengdl.org/Default.aspx?tabid=979)
- [Skoldinovs Objekte](http://www.skoldinov.spb.ru/obj.php?lang=en)
- [Runxels Objekte](https://runxel.xyz/archicad-objects/)
- [MEPContent](https://www.mepcontent.com/de/) – HKLSE Inhalte von Herstellern. Leider keine `.gsm`, aber `.rfa` und IFCs
- [McMaster-Carr](https://www.mcmaster.com/) – Schrauben, Befestigungen, uvm.


## Staffage
- [vector_vault](https://vectorvault.webflow.io/)
- [Pimp My Drawing](https://pimpmydrawing.com/)
- [Escalatina](https://escalalatina.com/)
- [NonScandinavia](http://www.nonscandinavia.com/)
- [Kaleidoscope](https://kaleidoscope-arch.tumblr.com/)
- [BLK IMG](https://black-img.com/Cut-outs)

## 3D Objekte
Oft auftauchende Frage: Wo bekomme ich 3D Modelle her?

- [Archive3D](https://archive3d.net/?category=28)
- [Turbosquid](https://www.turbosquid.com/)
- [CG Trader](https://www.cgtrader.com/)
- Fahrzeuge auf [hum3d](https://hum3d.com/3d-models/vehicles/)
- Geheimtipp: [SketchUp Warehouse](https://3dwarehouse.sketchup.com/)
- [Ivy Generator](http://graphics.uni-konstanz.de/~luft/ivy_generator)
- [Arcat](https://www.arcat.com/bim/bim_objects.shtml) – "Big Red Book"; leider nur noch Revit Families und DWG


## Geoinformationen
Zum einen gibt es natürlich die Bereitstellung von Geoinformationen (Karten, Daten, Luftbilder, etc.) durch die Landesvermessungsämter:
- [Berlins Fis-Broker](https://www.stadtentwicklung.berlin.de/geoinformation/fis-broker/)
- [BrandenburgViewer](https://bb-viewer.geobasis-bb.de/)
- [Baden-Württemberg](https://udo.lubw.baden-wuerttemberg.de/public/)
- [Bayern](https://geoportal.bayern.de/geoportalbayern/)
- etc.

Zum anderen kann man sich auch die Daten des [OpenStreetMap Projekts](https://www.openstreetmap.org/) holen. Dazu gibt es verschiedene Möglichkeiten (bei den meisten benötigt man einen kostenlosen OSM Account):
- [HOT](https://export.hotosm.org/en/v3/)
- [OSMaxx](https://osmaxx.hsr.ch/)
- Fertige OSM-Extrakte: [Geofabrik](http://download.geofabrik.de/)

<details markdown="1">
<summary>Details zum OSM Export …</summary>

Bei Tools, wie dem vom HOT (_"Humanitarian OpenStreetMap Team"_) angebotenen Dienst, lassen sich eigene Abzüge der OSM-Datenbank von beliebigen Gebieten der Welt erstellen. Wähle ein Gebiet aus, anschließend ein [Dateiformat](/datei-io/) (empfehlenswert ist SHP oder GeoPackage). Nach einigen Minuten ist der individuelle Export fertig zum Download.

In [QGis](https://qgis.org/) wählen wir "<samp>Neues Projekt</samp>", und anschließend "<samp>Layer > Layer hinzufügen > Vektorlayer hinzufügen</samp>" (für Shapefiles; für GeoPackage den entsprechenden Unterpunkt). In dem Dialog den Ablageort der `.shp` eingeben.  
Nach dem Import kann es passieren, dass die importierte Geometrie verzogen aussieht und/oder falsche Maße besitzt. Das hängt mit der Projektionsmethode zusammen. Normalerweise sollte eine dazugehörige `.prj` Datei von QGis automatisch gelesen werden, das klappt aber bisweilen nicht, da der Inhalt von Projektionsdateien nicht standardisiert ist und im Grunde jeder was anderes reinschreibt.  
Unten rechts in QGIS befindet sich ein Button mit einer stilisierten Weltkugel – dahinter verbirgt sich ein Dialog, in dem das Koordinatenbezugssystem (KBS) eingestellt werden kann. Ist unklar, welches das richtige KBS ist, kann man die `.prj` Datei in einem Texteditor öffnen und nachschauen, welche Projektion anzuwenden ist.

Zum Schluss die Datei als DXF aus QGis exportieren und in Archicad verwenden.

</details>

### Weitere Kartendienste
- [CadMapper](https://cadmapper.com)
- [Höhenkarten](http://terrain.party/)
- Live Satellitenbilder: [Mapbox](https://labs.mapbox.com/bites/00145/#7/52.214/10.195)
- [Relief Karten](https://maps-for-free.com)
- Schnell eigene Karten erstellen: [mapchart](https://mapchart.net/)
- Fertige Schwarzplane für ganze Städte (um 10€) gibt's bei [Schwarzplan.eu](https://schwarzplan.eu/).
- [Alle Gebäude der Niederlande](http://code.waag.org/buildings/#52.5379,4.9988,8)
- [Historische Karten](https://www.ieg-maps.uni-mainz.de/), vektorbasiert

Überblick über alle [EPSG Codes](https://www.spatialreference.org/).


## Sonstiges
- Wie klebe ich etwas am besten zusammen?: [This to That](http://thistothat.com/)
- [Scan2Cad](https://www.scan2cad.com/) – Alte, eingescannte Pläne schnell umwandeln; selbst Vector->Vector ist möglich
