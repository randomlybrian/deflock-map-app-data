# deflock-map-app camera data

Known license plate reader (ALPR) cameras in California, plus 20 km past its border, from OpenStreetMap. A job rebuilds these files once a day, and this repository only ever holds the current version and the one before it.

The files are made for the deflock-map-app navigation app, which routes drivers around these cameras. The camera locations are crowdsourced by OpenStreetMap volunteers, many through [DeFlock](https://deflock.me). This repository is not affiliated with DeFlock.

## Files

Start with `manifest.json`, which names the current version and its files:

```
https://raw.githubusercontent.com/randomlybrian/deflock-map-app-data/main/manifest.json
```

| File | Contents |
|---|---|
| `manifest.json` | Version, camera count, data date, license, and each file's path, size and SHA-256 |
| `<version>/cameras.sqlite.gz` | Gzip SQLite database with an R-tree index |
| `<version>/cameras.geojson.gz` | Gzip GeoJSON FeatureCollection of camera points |
| `<version>/california.geojson` | Simplified California border |

Each camera has its OpenStreetMap node id, location, facing directions in degrees (empty if unknown), manufacturer and operator. A version's files never change, and the version only changes when the camera data does.

## License

This data is derived from OpenStreetMap and is available under the [Open Database License (ODbL) 1.0](https://opendatacommons.org/licenses/odbl/1-0/). See [LICENSE.md](LICENSE.md). Credit it as "© OpenStreetMap contributors".

To add or fix a camera, edit OpenStreetMap, for example through [deflock.me](https://deflock.me). Changes show up here within a day.
