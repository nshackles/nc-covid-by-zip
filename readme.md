
# NC COVID-19 zip code data

This is a running repository for data captured daily by reporters from WRAL News via the [N.C. Department of Health and Human Services' zip code-level map](https://www.ncdhhs.gov/divisions/public-health/covid19/covid-19-nc-case-count#zip-code-map) of COVID-19 cases and deaths.

## Methodology

For now, this process is being completed manually, but the next steps will be to automate the process.

We're using [py esri dump](https://github.com/openaddresses/pyesridump) to capture the raw data from the [map layer published daily](https://nc.maps.arcgis.com/home/item.html?id=52f127a0767149ec984e91fcc06b06cb#overview) via the State of North Carolina's ArcGIS account. [The rest endpoint is here](https://services.arcgis.com/iFBq2AW9XO0jYYF7/arcgis/rest/services/Covid19byZIPnew/FeatureServer/0). (Note: Although DHHS first published its zip code map April 30, the agency started using this new layer on May 4. The endpoint for this map may change again).

**Usage**

    esri2geojson https://services.arcgis.com/iFBq2AW9XO0jYYF7/arcgis/rest/services/Covid19byZIPnew/FeatureServer/0 nc_zipDATE.geojson
After the geoJSON file is captured, we can upload it to [MapShaper](https://mapshaper.org/) to reduce the file size to 10 percent to speed up load times and download as a simplified geojson file.

We're also using [QGIS software](https://qgis.org/en/site/) to export the file in CSV format.

Once DHHS publishes the new file around 11 a.m., we can process the data and update [our own map](https://www.wral.com/coronavirus/nc-coronavirus-cases-maps-graphs-live-updates/19010016/) accordingly.

## Data
Below are the time-series files starting with the first date of capture on May 1. We'll eventually start combining these into a single file to show growth over time.
 - May 1 | [CSV file](time_series_data/csv/nc_zip0501.csv) (geojson files not captured)
 - May 2 | [full geoJSON file](time_series_data/full_geojson/nc_zip0502.geojson) | [reduced geoJSON file](time_series_data/reduced_geojson/nc_zip0502.json) | [CSV file](time_series_data/csv/nc_zip0502.csv)
 - May 3 | [full geoJSON file](time_series_data/full_geojson/nc_zip0503.geojson) | [reduced geoJSON file](time_series_data/reduced_geojson/nc_zip0503.json) | [CSV file](time_series_data/csv/nc_zip0503.csv)
 - May 4 | [full geoJSON file](time_series_data/full_geojson/nc_zip0504.geojson) | [reduced geoJSON file](time_series_data/reduced_geojson/nc_zip0504.json) | [CSV file](time_series_data/csv/nc_zip0504.csv)
 - May 5 | [full geoJSON file](time_series_data/full_geojson/nc_zip0505.geojson) | [reduced geoJSON file](time_series_data/reduced_geojson/nc_zip0505.json) | [CSV file](time_series_data/csv/nc_zip0505.csv)
 - May 6 | [full geoJSON file](time_series_data/full_geojson/nc_zip0506.geojson) | [reduced geoJSON file](time_series_data/reduced_geojson/nc_zip0506.json) | [CSV file](time_series_data/csv/nc_zip0506.csv)