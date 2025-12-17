# dron-morava

## rozdělení práce
Honza - pilot dronu, sběr dat, fotointerpretace
David - zpracování snímků, tvorba ortofota,  nahrávání do webového prostředí
Martin - tvorba mapy na webu, pomoc se zpracováním dat

## lokalita

* Blatecká štěrkovna u obce Charváty a slepá ramena řeky Moravy
* Zajímavá lokality, krásná příroda
* potenciál být chráněným územím
* Blatecká štěrkovna je rybářský revír
* zajímavá turistická lokalita (polní cesta na břehu Moravy, alternativa k cyklostezkám přes vesnice)
* původní záměr: Hlubočky
    * omezení letového provozu kvůli vojenskému prostoru Libavá

## dron
* DJI Mavic Pro
* Aplikace DJI fly
* limit 99 waypoints → let na dvě části
* při letu potíže s vybitou baterií a nutnost dělat let po částech nadvakrát kvůli tomu, že jsme misi omylem ukončili a ne přerušili
* jinak vše v pohodě
* výška letu - 110 m - kvůli stromům
* překryv 60 a 80%
* rozlišení 20 cm
* cca 15 letových řad
* území cca 600x600 m
* počasí jasné, bezvětří, čas cca 14:00, první polovina listopadu

![Morava, 6. listopadu 2025](./morava_m.jpg)

## zpracování dat

* snímky z dronu (cca 160), JPEG se souřadnicemi v EXIF
* Agisoft Metashape na učebně
    * *Workflow: Add photos; Align Photos; Build DEM; Build Photomosaic*
    * ořez polygonem (*outer boundary*)
    * *Export Photomosaic*
        * typ *Google Map Tiles* (PNG v ZIP)
        * zoom 14-21
* exportované dlaždice komprimovány `optipng`
    * cca 360 MiB → 310 MiB

## fotointerpretace

* ArcGIS Pro
* Nejprve polygony
* Poté vybrané liniové prvky zmapovány (nejprve lesy, poté pole, louky, zahrada, řeka, slepá ramena  a na konec cesty)
* Doplněny informace o řece Moravě, Blatecké štěrkovně a slepých ramenech do atributové tabulky (textový popis)
* export do GeoJSON

## front-end

* GeoJSON rozsekán
* generalizace polygon → linie při oddálení
* TODO
* agilní zapracování zpětné vazby
