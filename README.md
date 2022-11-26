## Lebanon Traffic Dataset

This is a data package of automotive velocities on the roads of Lebanon, crowd-sourced using [Tari'ak (طريقك) mobile app](http://tari2ak.com) from a total of 17,274 smartphones. The set contains 6,006,041 data points that span from March 20, 2014 to October 17, 2019.

## Instructions

The easiest way to import this package is using one of the existing [Data Package Libraries](https://frictionlessdata.io/universe/).

You can also manually ingest the package resources, which is composed from 2 files:

- **`data/streets.geojson`**: list of street features referenced in `data/velocities.csv` described in [`GeoJSON`](https://geojson.org/).
- **`data/velocities.csv`**: location and velocity data of devices in automotive transport, confined to the country of Lebanon.

| Field                 | Type     | Description                                                                                                                                                                                                                                                                                                                                                                                                       |
|-----------------------|----------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Date                  | `date`     | Date of when the data point was collected. Date values are reported in `Asia/Beirut` timezone. Values range between `2015-03-20` and `2019-10-17`.                                                                                                                                                                                                                                                               |
| Time                  | `time`     | Time of when the data point was collected. Time values are reported in `Asia/Beirut` timezone. Values range between `00:00:00` and `23:59:59`.                                                                                                                                                                                                                                                                   |
| Coordinate (Lon, Lat) | `geopoint` | Coordinate of where the data point was collected. Coordinates are represented as `(longitude,latitude)`, and NOT `(latitude,longitude)`. Latitude values range between `-90` and `90`. Longitude values range between `-180` and `180`.                                                                                                                                                                          |
| Course                | `number`   | The direction in which the device was traveling when the data point was collected, measured in degrees starting at due north and continue clockwise around the compass. Thus, north is 0 degrees, east is 90 degrees, south is 180 degrees, and so on. Course values may not be available on all devices. A negative value indicates that the course information is invalid. Values range between `0` and `360`. |
| Velocity              | `number`   | The velocity the device was traveling at when the data point was collected, measured in meters/second NOT kilometers/hour. Values are positive.                                                                                                                                                                                                                                                                  |
| Street ID             | `string`   | The unique identifier for the street using its OpenStreetMap (OSM) ID. Streets are map-matched from OSM with a simple linear algebra algorithm using the device's coordinate and course.                                                                                                                                                                                                                          |

## License

This data package is licensed under ODC Open Database License (ODbL v1.0) which means you can use it freely for your personal or commercial projects as long as you attribute its source to tari2ak.com and keep your data open.

The full license is described in [`LICENSE.md`](LICENSE.md).
