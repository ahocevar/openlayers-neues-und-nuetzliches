---
title: OpenLayers - Neues und Nützliches
layout: fact
contextMenu: false
favicon: https://openlayers.org/theme/img/logo-light.svg
---

# OpenLayers

<center><img src="./ol.svg" height="300"/></center>

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
import {Map, View} from 'ol';
import TileLayer from 'ol/layer/Tile';
import OSM from 'ol/source/OSM';

const map = new Map({
  target: 'map',
  layers: [
    new TileLayer({
      source: new OSM()
    })
  ],
  view: new View({
    center: [0, 0],
    zoom: 2
  })
});
```

---
layout: center
zoom: 1.5
---

## Resultat (im Browser)

![Eine OpenLayers Applikation mit einer Weltkarte basierend auf den OpenStreetMap Daten](./first-app.png "Eine OpenLayers Applikation als Startpunkt für weitere Entwicklungen")

---
layout: center
zoom: 1.5
---

# Interoperabilität

Standards

GeoJSON,TopoJSON, OGC WMS WFS WMTS, OGC API Tiles, MVT, TileJSON, STAC, GeoTIFF, IIIF, ArcGIS REST, …

---
layout: center
zoom: 1.5
---

SentinelHub inkl. Processing API

![Nutzung von SentinelHub inklusive Processing API](./sentinel-hub.png "Nutzung von SentinelHub inklusive Processing API")

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

![Nutzung von STAC innerhalb einer OpenLayers Applikation](./stac.png "Nutzung von STAC innerhalb einer OpenLayers Applikation")

---
layout: center
zoom: 1.5
---


# Flat styles

* <span style="text-decoration: darkgray line-through">`WebGLStyle`</span> => *`FlatStyle`*
* weniger `new Style(…)` … => *`FlatStyle`*
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
