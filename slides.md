---
title: OpenLayers - Neues und Nützliches
layout: fact
contextMenu: false
favicon: https://openlayers.org/theme/img/logo-light.svg
---

# OpenLayers

<center><img src="/ol.svg" height="300"/></center>

Neues und Nützliches

2025

---
layout: center
zoom: 1.5
---

# Interaktive Karten fürs Web

Mit JavaScript

```bash
npm create ol-app my-app
cd my-app
npm start
```
---
layout: center
zoom: 1.5
---

## Resultat (Code)

```javascript
import './style.css';
import Map from 'ol/Map';
import View from 'ol/View';
import TileLayer from 'ol/layer/Tile';
import OSM from 'ol/source/OSM';

const map = new Map({
  target: 'map',
  layers: [
    new TileLayer({source: new OSM()})
  ],
  view: new View({center: [0, 0], zoom: 2})
});
```

---
layout: center
zoom: 1.5
---

## Resultat (im Browser)

![Eine OpenLayers Applikation mit einer Weltkarte basierend auf den OpenStreetMap Daten](/first-app.png "Eine OpenLayers Applikation als Startpunkt für weitere Entwicklungen")

---
layout: center
zoom: 1.5
---

# Interoperabilität

Standards

GeoJSON, TopoJSON, OGC WMS WFS WMTS, OGC API Tiles Features, MVT, TileJSON, TMS, XYZ, STAC, GeoTIFF, IIIF, ArcGIS REST, …

---
layout: center
zoom: 1.5
---

SentinelHub inkl. Processing API

![Nutzung von SentinelHub inklusive Processing API](/sentinel-hub.png "Nutzung von SentinelHub inklusive Processing API")

---
layout: center
zoom: 1.5
---

# Interoperabilität

Libraries

Proj4js, ol-mapbox-style, ol-stac, PMTiles, GeoStyler, FlatGeobuf, Turf, JSTS, Terra Draw, …

---
layout: center
zoom: 1.5
---

STAC inkl. Reprojection, weniger als 5 Zeilen Code

![Nutzung von STAC innerhalb einer OpenLayers Applikation](/stac.png "Nutzung von STAC innerhalb einer OpenLayers Applikation")

---
layout: center
zoom: 1.5
---

# Styles

```js
(feature) => new Style({
  text: new Text({
    font: '13px Calibri,sans-serif',
    text: feature.get('name'),
    placement: 'line',
    fill: new Fill({
      color: 'black'
    }),
    stroke: new Stroke({
      color: 'white',
      width: 2
    })
  })
})
```

---
layout: center
zoom: 1.5
---

Vektor Tiles mit ol-mapbox-style, 1 Zeile Code

```js
apply('map', 'https://tiles.openfreemap.org/styles/liberty');
```

![Komplexe Karte aus einem Mapbox Style](/vectortile.png "Komplexe Karte aus einem Mapbox Style")

---
layout: center
zoom: 1.5
---

# Flat Styles

```js
{
  'text-font': '13px Calibri,sans-serif',
  'text-value': ['get', 'name'],
  'text-placement': 'line',
  'text-fill-color': 'black',
  'text-stroke-color': 'white',
  'text-stroke-width': 2
}

```

---
layout: center
zoom: 1.5
---

# Flat Styles

Auch für Raster 🚀

```js
const elevation = [
  '+',
  -10000,
  ['*', 0.1 * 255 * 256 * 256, ['band', 1]],
  ['*', 0.1 * 255 * 256, ['band', 2]],
  ['*', 0.1 * 255, ['band', 3]],
];
const style = {
  color: [
    'case',
    ['<=', elevation, 3],
    [139, 212, 255, 1],
    [0, 0, 0, 0],
  ],
}
```

---
layout: center
zoom: 1.5
---

Raster Style - Meeresspiegel +3 m

![Küstenline bei Merresspiegel +3 m](/raster-style.png "Küstenline bei Merresspiegel +3 m")

---
layout: center
zoom: 1.5
---

Raster ohne Style - Höhenmodell in R, G, B codiert

![Höhenmodell in PNG](/raster-no-style.png "Höhenmodell in PNG")


---
layout: center
zoom: 1.5
---

# Future: keine barrel files mehr

* "A barrel is a file that does nothing but re-export things from other files"
* bessere dev-experience
* kleinere builds
* Codemod: https://www.npmjs.com/package/@openlayers/codemod
---
layout: center
zoom: 1.5
---
