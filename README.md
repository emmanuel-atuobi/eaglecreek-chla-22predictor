# Eagle Creek Chlorophyll — 22-Predictor Model

Interactive map of model-predicted chlorophyll-a for Eagle Creek Reservoir, Indiana: 107 accepted Landsat acquisitions from 1984–2024.

This is the **22-predictor XGBoost edition**. The original thesis viewer remains at https://emmanuel-atuobi.github.io/eaglecreek-chla/ .

## Contents

- `index.html`: interactive Leaflet viewer.
- `frames.json`: dates, map bounds, classes and native-grid statistics.
- `frames/`: 107 value-encoded PNGs, decoded by the viewer; they are not ordinary colour maps.

Values are predictions in µg/L, not field measurements. The basemap is contemporary and is not matched to each historical acquisition. Long-term results can be affected by sensor transitions; agreement between model versions does not resolve that uncertainty.

Model SHA256: `82ca415c6b586be1119fefc35a7591ef50613a7efb587fede4a7733b5aed0ca4`.

The exact 107 thesis dates and valid-pixel counts were preserved. Statistics are calculated on the original 30 m UTM grid; nearest-neighbour reprojection is for display only. Encoded values have 0.01 µg/L resolution. Class boundaries and viewer design follow the original visualization.

## Preview locally

```bash
python -m http.server 8000 --bind 127.0.0.1
```

Open http://127.0.0.1:8000 . Internet access is needed for Leaflet and basemap tiles.

## Publishing and updates

GitHub Pages serves the root of the `main` branch. Commit and push changes to this repository to update this edition; the old viewer is in a different repository.
