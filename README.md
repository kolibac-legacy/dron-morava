# dron-morava

## lokalita

* Blatecká štěrkovna
    * zajímavá turistická lokalita (polní cesta na břehu Moravy, alternativa k cyklostezkám přes vesnice)
* původní záměr: Hlubočky
    * omezení letového provozu kvůli vojenskému prostoru Libavá

## sběr dat

* TODO
* limit 99 waypoints → let na dvě části
* zapomenutá microSDHC karta ve dronu :-]

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

* TODO
* export do GeoJSON

## front-end

* GeoJSON rozsekán
* generalizace polygon → linie při oddálení
* TODO

![Morava, 6. listopadu 2025](./morava_m.jpg)
