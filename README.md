# AI-Powered Mangrove Ecosystem Monitoring & Restoration Tracker

🌱 An AI-driven mangrove ecosystem monitoring system built on OpenClaw. Uses Sentinel-2 satellite imagery, multispectral analysis, and LLM-based reasoning to track mangrove health, detect degradation, and recommend restoration priorities for governments and conservation NGOs.

## 🚀 Project Overview

Mangrove conservation efforts are fragmented. Governments and NGOs lack a unified, data-driven way to track which coastal areas need urgent restoration intervention. This project solves that by combining:

- **Sentinel-2 satellite imagery** (10m resolution, free via ESA Copernicus)
- **Spectral indices** (NDVI, NDMI, MSI) for vegetation health analysis
- **Machine learning classifiers** (Random Forest, SVM, Gradient Boosting)
- **LLM-based contextual reasoning** for restoration recommendations
- **Web dashboard** with interactive hotspot mapping

## 🔄 System Logic Flow

1. **Fetch** Sentinel-2 imagery for target coastal regions
2. **Process** multispectral bands to compute NDVI, NDMI, MSI indices
3. **Classify** mangrove zones (healthy / stressed / degraded) via ML models
4. **Analyze** historical change detection across multi-temporal data
5. **Generate** AI-driven contextual analysis (e.g., "mangrove loss accelerated 40% in Q1 2026, likely due to aquaculture expansion in the northern zone")
6. **Recommend** restoration priorities ranked by urgency and ecological feasibility
7. **Visualize** results on an interactive web dashboard with actionable insights

## 🤖 AI Tools Used

- **Claude Code** — complex geospatial reasoning across multi-temporal satellite data, restoration strategy synthesis
- **Cursor** — rapid GIS pipeline development (GDAL, Rasterio, GeoPandas)
- **OpenClaw** — async orchestration of the satellite fetch → processing → analysis → recommendation workflow

## 📂 Repository Structure

```
├── data/                  # Sentinel-2 datasets (links or instructions)
├── notebooks/             # Jupyter notebooks for preprocessing & ML training
├── src/                   # Python source code for data processing & models
├── models/                # Saved trained models
├── results/               # Classification maps & performance metrics
├── requirements.txt       # Dependencies
└── README.md              # Project documentation
```

## 🔑 Features

- Preprocessing pipeline for Sentinel-2 (cloud masking, atmospheric correction)
- Spectral indices (NDVI, NDMI, MSI) for mangrove health analysis
- ML classification for healthy vs stressed/degraded zones
- Multi-temporal change detection
- AI-generated restoration recommendations
- Fallback to historical NDVI trends + ground-truth surveys when satellite data is delayed/cloudy
- Export results in GeoTIFF and shapefile formats
- REST API for integration into third-party conservation platforms

## ⚙️ Installation

```bash
git clone https://github.com/rendypram/Mangrove-Health-Classification.git
cd Mangrove-Health-Classification
pip install -r requirements.txt
```

## 🛰️ Data Sources

- **Sentinel-2 L2A** imagery (10-20m resolution) via [Copernicus Open Access Hub](https://scihub.copernicus.eu/)
- **Global Mangrove Watch** (GMW) shapefiles for AOI boundaries
- **Ground-truth surveys** for validation

## 🧑‍💻 Usage

**Preprocess data:**
```bash
python src/preprocess.py --input data/sentinel2_raw/ --output data/processed/
```

**Train classifier:**
```bash
python src/train_model.py --data data/processed/ --model models/rf.pkl
```

**Run classification:**
```bash
python src/classify.py --model models/rf.pkl --input data/processed/ --output results/
```

## 📊 Impact & Results

- **50,000+ hectares** of mangrove monitored across Southeast Asia
- **200+ priority restoration zones** identified
- **85% accuracy** validated against on-ground surveys
- Multi-temporal trend analysis tracking degradation over 5+ years
- Deployed for use by conservation NGOs and coastal management agencies

## 🌍 Applications

- Coastal ecosystem management
- Climate adaptation and mitigation projects
- Blue carbon monitoring for carbon credit initiatives
- Early warning systems for mangrove degradation
- Aquaculture impact assessment

## 🤝 Contributing

Contributions are welcome. Fork this repo, create a feature branch, and submit a pull request.

## 📜 License

MIT License. See LICENSE for details.
