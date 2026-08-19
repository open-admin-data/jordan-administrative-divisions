# Jordan Administrative Divisions / الأردن



## Overview

| Item | Details |
|------|---------|
| Governorate | 12 |
| Municipality | 110 |
| Locality | 741 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-08-19 |
| Website | [openadmindata.org/jo](https://openadmindata.org/jo/) |
| API | [openadmindata.org/api/jo](https://openadmindata.org/api/jo/) |
| National Anthem | [🎵 Listen & Download Jordan National Anthem MP3](https://onlygames.me/national-anthems/jo/) |

## Browse by Governorate

| # | Governorate | Municipalitys | Localitys | Link |
|---|----|----|----|------|
| 1 | عمّان (Amman) | 11 | 138 | [Browse](divisions/amman/) |
| 2 | البلقاء (Balqa) | 10 | 76 | [Browse](divisions/balqa/) |
| 3 | الزرقاء (Zarqa) | 8 | 60 | [Browse](divisions/zarqa/) |
| 4 | مادبا (Madaba) | 4 | 73 | [Browse](divisions/madaba/) |
| 5 | إربد (Irbid) | 19 | 136 | [Browse](divisions/irbid/) |
| 6 | المفرق (Mafraq) | 19 | 145 | [Browse](divisions/mafraq/) |
| 7 | جرش (Jarash) | 6 | 0 | [Browse](divisions/jarash/) |
| 8 | عجلون (Ajlun) | 5 | 0 | [Browse](divisions/ajlun/) |
| 9 | الكرك (Karak) | 10 | 87 | [Browse](divisions/karak/) |
| 10 | الطفيلة (Tafela) | 4 | 0 | [Browse](divisions/tafela/) |
| 11 | معان (Ma&#34;an) | 8 | 0 | [Browse](divisions/maan/) |
| 12 | العقبة (Aqaba) | 6 | 26 | [Browse](divisions/aqaba/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-governorate.json](data/all-governorate.json) | JSON | All 12 governorate records |
| [all-municipality.json](data/all-municipality.json) | JSON | All 110 municipality records |
| [all-locality.json](data/all-locality.json) | JSON | All 741 locality records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-2 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-governorate.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['municipality']} municipalitys")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-governorate.json", "utf-8"));
console.log(`Total: ${data.length} governorates`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=governorate, 2=municipality, 3=locality |
| `level_name` | object | Level label (local + English) |
| `name.local` | string | Name in local script |
| `name.en` | string | English name |
| `name.slug` | string | URL-safe slug |
| `parent` | object/null | Parent division reference |
| `ancestors` | array | Full ancestor chain |
| `children_count` | object | Count of children per level |
| `zip_codes` | array | Postal codes (where available) |
| `geo.lat` | string | Latitude (WGS84) |
| `geo.lon` | string | Longitude (WGS84) |

Full schema: [data/schema.json](data/schema.json)

## Hierarchy Browse

```
divisions/{governorate-slug}/
divisions/{governorate-slug}/{municipality-slug}/
```

Localitys are listed inline in each municipality's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-governorate links
- [Per-governorate data](docs/llms-full/) — Full data by governorate

## Citation

```
Jordan Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/jordan-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [Open Admin Data](https://openadmindata.org) — Browse, search and explore administrative divisions for every country
- [open-admin-data](https://github.com/open-admin-data) — GitHub organization with all country repos
- [ListBase](https://www.listbase.org) — Structured reference data for every country
