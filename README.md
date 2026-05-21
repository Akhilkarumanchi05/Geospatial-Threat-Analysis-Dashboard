# Geospatial Threat Analysis Dashboard

A large-scale geospatial analytics system that processes millions of global incident records, detects crime and protest hotspots through spatial clustering, and surfaces them on interactive maps used by security teams for risk assessment.

---

## Overview

Security and risk teams need to make sense of enormous, constantly-updating streams of global incident data. This project ingests 10M+ records, identifies geographic hotspots using density-based clustering, and presents them through interactive maps — turning raw event feeds into actionable situational awareness.

## Approach

**Data ingestion at scale**
- Processed **10M+ global incident records** using **GeoPandas** and **H3 hexagonal spatial indexing** for efficient location-based aggregation.
- Integrated **real-time data feeds** — **GDELT** (global events) and **OpenStreetMap** — through API pipelines.

**Spatial clustering**
- Applied **DBSCAN** (density-based clustering) to detect crime and protest hotspots, reaching **~90% precision** in hotspot identification.
- DBSCAN is well-suited here because it finds arbitrarily-shaped dense regions without needing a preset number of clusters.

**Performance engineering**
- Optimized **PostGIS** spatial queries for a **~5× speedup** in geospatial analytics, making interactive exploration practical at scale.

**Visualization**
- Built interactive **Plotly** maps that security teams adopted for ongoing risk assessment.

## Results

| Metric | Value |
|---|---|
| Records processed | 10M+ |
| Hotspot detection precision | ~90% |
| Query speedup (PostGIS optimization) | ~5× |

## Tech Stack

`Python` · `GeoPandas` · `H3 spatial indexing` · `DBSCAN (scikit-learn)` · `PostGIS` · `Plotly` · `GDELT API` · `OpenStreetMap API`

## Architecture

```
GDELT + OpenStreetMap feeds (API) → GeoPandas + H3 indexing
        → DBSCAN hotspot clustering → PostGIS (optimized spatial queries)
        → Interactive Plotly maps → Security team risk assessment
```

## Future Work

- Add temporal clustering to track how hotspots evolve over time.
- Layer in predictive modeling to forecast emerging risk areas.
- Stream processing for true real-time updates rather than batch refresh.

> **Note:** The original dashboards were built in Tableau / Power BI and are being reconstructed. This repository documents the data pipeline, methodology, and results.

---

*Built by [Akhil Karumanchi](https://github.com/Akhilkarumanchi05) · [LinkedIn](https://www.linkedin.com/in/akhil-karumanchi-56440922a/)*
