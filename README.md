Urban Vulnerability Pipeline
=============================

This project identifies and visualizes urban vulnerabilities by integrating geospatial and socioeconomic data. The pipeline combines:

- **OpenStreetMap (OSM)** infrastructure layers (buildings, roads, services)
- **Sentinel-2 NDVI** satellite imagery
- **WorldPop** demographic estimates

The final output includes composite vulnerability scores across a 2×2 km grid, supporting applications in disaster preparedness, equitable development, and urban planning.

> ⚠️ Note: While the repo code uses the term “Urban Risk Pipeline,” the official project name is **Urban Vulnerability Pipeline**.

## 📁 Repository Structure

This pipeline is organized into modular notebooks and data folders:

### 📓 Notebooks

| Notebook | Description |
|----------|-------------|
| `01_load_and_explore_osm_data.ipynb` | Loads and explores raw OSM layers (buildings, roads, services) |
| `02_process_ndvi_satellite_data.ipynb` | Loads Sentinel-2 NDVI raster, creates a 2×2 km grid, computes zonal NDVI stats |
| `03_add_population_from_worldpop.ipynb` | Adds WorldPop population estimates to each grid cell |
| `04_kawempe_grid_features_ml.ipynb` | Combines all features, scales them, computes vulnerability scores, and visualizes the results |

---

### 📂 Data Folders

| Folder | Contents |
|--------|----------|
| `data/raw/` | Original input files (OSM GeoJSONs, NDVI raster, WorldPop raster) |
| `data/processed/` | Intermediate outputs (e.g., `urban_grid.geojson`, `urban_grid_with_population.geojson`) |
| `visualizations/` | Saved map visualizations for NDVI, infrastructure, and vulnerability classifications |

---

## 📊 Outputs

- **NDVI Distribution Maps**
- **Infrastructure Heatmaps**
- **Hidden Vulnerability Score** — highlights high-pop, low-infra areas
- **Rescue Priority Score** — identifies high-density, well-built areas for disaster response

---

## 🚀 Future Directions

- Add time-series vulnerability tracking
- Integrate flood risk layers or other climate hazards
- Package pipeline as a command-line tool or web app for local governments and NGOs
