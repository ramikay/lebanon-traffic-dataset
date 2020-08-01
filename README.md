## Hello

This is a data package of automotive velocities on the roads of Lebanon, crowd-sourced using Tari'ak (طريقك) mobile app from a total of 17,274 smartphones. The data contains 6,007,042 points that span from March 20, 2014 to October 19, 2019.

For more information about the project visit [tari2ak.com](http://tari2ak.com).

## Instructions

The easiest way to investigate this package is using one of the existing [Data Package Tools](http://frictionlessdata.io/tooling/data-package-tools).

You can also manually ingest the package resources, which is composed from 2 files:

1. **`data/velocities.csv`**: location and velocity data of devices in automotive transport, confined to the country of Lebanon.

| Field                 | Type     | Range                                        | Description                                                                                                                                                                                                                                                                                                                                                                  |   |
|-----------------------|----------|----------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---|
| Date                  | date     | min: 2015-03-20 max: 2019-10-19              | Date of when the data point was collected. Date values are reported in `Asia/Beirut` timezone.                                                                                                                                                                                                                                                                               |   |
| Time                  | time     | min: 00:00:00 max: 23:59:59                  | Time of when the data point was collected. Time values are reported in `Asia/Beirut` timezone.                                                                                                                                                                                                                                                                               |   |
| Coordinate (Lon, Lat) | geopoint | latitudes (-90, 90) longitudes (-180 to 180) | Coordinate of where the data point was collected. Coordinates are represented as `(longitude,latitude)`, and NOT `(latitude,longitude)`.                                                                                                                                                                                                                                     |   |
| Course                | number   | min: 0 max: 360                              | The direction in which the device was traveling when the data point was collected, measured in degrees starting at due north and continue clockwise around the compass. Thus, north is 0 degrees, east is 90 degrees, south is 180 degrees, and so on. Course values may not be available on all devices. A negative value indicates that the course information is invalid. |   |
| Velocity              | number   | min: 0                                       | The velocity the device was traveling at when the data point was collected, measured in meters/second NOT kilometers/hour.                                                                                                                                                                                                                                                   |   |
| Street ID             | string   |                                              | The unique identifier for the street using its OpenStreetMap (OSM) ID. Streets are map-matched from OSM with a simple linear algebra algorithm using the device's coordinate and course.                                                                                                                                                                                     |   |

2. **`data/streets.geojson`**: list of street features referenced in `data/velocities.csv` described in [`GeoJSON`](https://geojson.org/).

## License

This data package is licensed under ODC Open Database License (ODbL v1.0) which means you can use it freely for your personal or commercial projects as long as you attribute its source to tari2ak.com and keep your data open.

The full license is described in [`LICENSE.md`](LICENSE.md).