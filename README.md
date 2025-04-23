# EY France 2025 – Urban Heat Island Modeling

## 🧠 Project Overview

Two complementary approaches were developed for UHI estimation:

- **Score-Oriented Approach** – Optimized for leaderboard performance (R² = 0.9815)
- **Universal Robust-Oriented Approach** – Designed for generalization and real-world applicability (R² = 0.9778)

Both use multi-source geospatial and environmental data.

## 📦 Setup

```bash
git clone https://github.com/MohamedHridou/EY_2025_Team_HaraWeCan_Model_Inference.git
cd EY_2025_Team_HaraWeCan_Model_Inference

conda create -n ey_france_2025 python=3.11 -y
conda activate ey_france_2025

pip install -r requirements.txt
```

## ▶️ Inference Instructions

### Approach 1: Score-Oriented
- Open:  
  `approach_1_Score_Oriented_Approach/Model development - inference.ipynb`  
- Run all cells.

### Approach 2: Universal Robust-Oriented
- Open:  
  `approach_2_Universal_Robust_Oriented_Approach/model_inference.ipynb`  
- Run all cells.

## 📚 Data Sources

- **Src1**: Weather Data (Challenge organizer)
- **Src2**: Sentinel-1/2, Landsat (ESA/NASA)
- **Src3**: Building Footprints (NYC Open Data)
- **Src4**: ERA5-Land Weather (ECMWF)
- **Src5**: Elevation Data (NASA SRTM, Open-Elevation API)
- **Src6**: Road Data (NYS GIS)

## 📐 Modeling Notes

### Score-Oriented
- Data: Src1–Src5
- Methods: Feature engineering + XGBoost
- Focus: Radiation, temperature/wind interactions
- No lat/lon used

### Universal Robust-Oriented
- Components: RNN (GRU/LSTM), CNN, Neural Similarity Metrics
- Inputs: Satellite TS, daily weather, 3D building maps
- Logic: Learn environmental structure + contrast vs. rural refs
- Joint training of all components

## 🔬 Reference
Valentino Sangiorgio et al. (2020), *Scientific Reports*, doi: [10.1038/s41598-020-75018-4](https://doi.org/10.1038/s41598-020-75018-4)
