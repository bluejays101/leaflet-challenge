# Leaflet-Part-1: Earthquake & Tectonic Plates Visualization

## Overview
This project visualizes “All Earthquakes (Past 7 Days)” from the USGS GeoJSON feed and overlays global tectonic-plate boundaries using Leaflet and D3. Users can toggle between two base maps (OpenStreetMap and HOT), inspect earthquake markers (sized by magnitude and colored by depth), and view an interactive legend.

## Features
- **Interactive Map**: Pan, zoom, and click markers for details.
- **Base Layers**: OpenStreetMap and Humanitarian OpenStreetMap Team (HOT).
- **Earthquake Markers**: Circle markers scaled by magnitude and colored by depth.
- **Tectonic Plates** (optional toggle): Orange line boundaries of tectonic plates.
- **Legend**: Displays depth intervals with matching colors.

## File Structure
```
Leaflet-Part-1/
├─ index.html
├─ static/
│  ├─ css/
│  │  └─ style.css
│  └─ js/
│     └─ logic.js
└─ README.md
```

- **index.html**  
  - Loads Leaflet, D3, custom CSS/JS.  
  - Contains `<div id="map"></div>` as the map container.

- **static/css/style.css**  
  - Ensures `#map` fills the viewport.  
  - Styles the legend box (`.info.legend`).

- **static/js/logic.js**  
  1. Defines `basemap` and optional `street` layers.  
  2. Initializes Leaflet map centered on [37.5, –120], zoom 5.  
  3. Creates `earthquakes` and `tectonic_plates` LayerGroups and a layer control.  
  4. Implements `getColor(depth)` and `getRadius(magnitude)` helper functions.  
  5. Fetches USGS `all_week.geojson`, plots earthquakes as circle markers, and binds popups.  
  6. Adds a bottom-right legend showing depth intervals.  
  7. (Optional) Fetches tectonic-plate boundaries and adds them as orange lines.

## Installation & Usage

1. **Clone the repository** and navigate into the folder:
   ```bash
   git clone <https://github.com/bluejays101/leaflet-challenge.git>
   cd Leaflet-Part-1
   ```

2. **Serve the files via a local HTTP server** (required for D3 to load GeoJSON). You can use either:

   - **Python 3 built-in server**:
     ```bash
     python3 -m http.server 8000
     ```
     Then open:  
     `http://127.0.0.1:8000/index.html`

   - **VS Code Live Server** (or similar)  
     - Start Live Server; by default, it may serve at `http://127.0.0.1:5500/`.  
     - Open:  
       `http://127.0.0.1:5500/index.html`  
     - If Live Server uses a different port, adjust accordingly.

3. **Interact with the map**:
   - Toggle base layers (OpenStreetMap / HOT) via the layer control.  
   - View earthquake markers: color indicates depth, size indicates magnitude. Click for location, magnitude, and depth.  
   - Reference the legend (bottom-right) to interpret depth colors.  
   - (Optional) Toggle “Tectonic Plates” to display plate boundaries.

## Dependencies

- [Leaflet 1.9.4](https://leafletjs.com/)  
- [D3.js v7](https://d3js.org/)  
- Internet connection for tile servers and GeoJSON feeds

## Data Sources

- **Earthquake data**: USGS GeoJSON Feed  
  `https://earthquake.usgs.gov/earthquakes/feed/v1.0/summary/all_week.geojson`

- **Tectonic-plate data**:  
  `https://raw.githubusercontent.com/fraxen/tectonicplates/master/GeoJSON/PB2002_boundaries.json`

- **Tile layers**:  
  - OpenStreetMap (OSM)  
  - Humanitarian OpenStreetMap Team (HOT)

## Attribution

- Map tiles © OpenStreetMap contributors and HOT  
- Earthquake data © USGS  
- Tectonic-plate data © Fraxen (GitHub)

---
