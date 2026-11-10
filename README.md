# World Ports Data: 3,800 ports, depths and facilities

[![Apify Actor](https://img.shields.io/badge/Apify-Actor-1f6feb)](https://apify.com/phonic_lily/world-ports-data) ![Licence](https://img.shields.io/badge/licence-Public_domain-blue) ![Records](https://img.shields.io/badge/records-3%2C804-green)

Search 3,804 world ports from the NGA World Port Index: coordinates, harbor size and type, channel/anchorage/cargo depths, tidal range, pilotage, tugs, repair and drydock capability. Embedded data, no scraping, pay per record.

## What you get
- **3,804 records**, each carrying its own `license` and `attribution` fields, ready to republish with the required credit.
- A **100-record free sample** in this repository: [`sample.jsonl`](sample.jsonl) and [`sample.csv`](sample.csv) (opens as a table on GitHub).
- The **full dataset** as a filterable API (JSON, CSV, Excel), no scraping, no login: [World Ports Data: 3,800 ports, depths and facilities on Apify](https://apify.com/phonic_lily/world-ports-data).

## One record
```json
{
  "port_id": "wpi-7950",
  "name": "Maurer",
  "country_name": "United States",
  "lat": 40.533333,
  "lon": -74.25,
  "harbor_size": "Very Small",
  "harbor_type": "River (Natural)",
  "chan_depth_m": 11.0,
  "cargo_depth_m": 11.0,
  "tidal_range_m": 1.5,
  "locode": null
}
```

## Quick start
Python:
```python
from apify_client import ApifyClient
client = ApifyClient('<YOUR_APIFY_TOKEN>')
run = client.actor('phonic_lily/world-ports-data').call(run_input={'maxResults': 10})
for item in client.dataset(run['defaultDatasetId']).iterate_items():
    print(item)
```
Or from the command line:
```bash
curl -X POST 'https://api.apify.com/v2/acts/phonic_lily~world-ports-data/run-sync-get-dataset-items?token=<YOUR_APIFY_TOKEN>' \
  -H 'Content-Type: application/json' -d '{"maxResults": 10}'
```
Pricing is pay-per-record on Apify (see the Actor page); the sample here is free.

## Fields
| Field | Description |
|---|---|
| `port_id` | Stable port identifier (wpi-<index number>). |
| `name` | Port name. |
| `country_name` | Country. |
| `lat` | Latitude, decimal degrees. |
| `lon` | Longitude, decimal degrees. |
| `harbor_size` | NGA harbor size class. |
| `harbor_type` | NGA harbor type. |
| `chan_depth_m` | Channel depth in metres, null if unknown. |
| `cargo_depth_m` | Cargo pier depth in metres, null if unknown. |
| `tidal_range_m` | Tidal range in metres, null if unknown. |
| `locode` | UN/LOCODE when known. |

## Data, licence and attribution
National Geospatial-Intelligence Agency World Port Index, a US Government work in the public domain. Null means the source gives no value; it is never 0.

**Licence:** Public domain (US Government work, NGA World Port Index)

**Attribution:** Source: National Geospatial-Intelligence Agency, World Port Index (public domain).

Snapshot date: 2026-11. Empty values are `null`, never 0.

## Cite this dataset
GitHub's *Cite this repository* button reads [`CITATION.cff`](CITATION.cff).

## Feedback
Found an error or want a field added? Open an issue in this repository.
