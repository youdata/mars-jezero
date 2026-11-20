# 毅力号之路 · Perseverance's road

Jezero crater on Mars from orbit: CTX at 5 m a pixel for the whole crater, HiRISE at 25 cm for the rover's country; the rover's route drive by drive from NASA/JPL's mission map, its 28 rock and soil samples, IAU names, and a narrated tour from the landing site to the crater rim. Find any sample, crater or sol in the search box.

Live: https://youdata.github.io/mars-jezero/

The image pyramids are tile folders (`jezero-ctx/`, `jezero-hirise/`: `header.idx` + `{z}/{x}/{y}.png`), so any static host serves them. Its fonts are in `fonts/`, trimmed to the page's characters. The narrated video is not included.

Images: NASA/JPL-Caltech/University of Arizona. HiRISE (25 cm): USGS orthomosaic for Mars 2020 Terrain Relative Navigation, doi:10.5066/P9QJDP48; where it has no data, CTX (5 m): JPL Mars 2020 science-investigation orthomosaic. Route: NASA/JPL mission map. Samples: NASA, "Mars Rock Samples". Names: IAU / USGS Gazetteer.

## How it is made

From `infographic-examples/mars-jezero/build.mjs (then places added in the editor: mars-jezero.places.json)`, with rx (`~/rx-cli`):

```sh
rx export mars-jezero.places.json --out site --app /rx-graphic-editor/web/index.html --canvas --theme dark --lock-layers --tiles dir --plugin …/urlTileImage.js --plugin …/viewsPlugin.js --plugin …/placeSearchPlugin.js
rx publish site --to github:youdata/mars-jezero --yes
```
