# 💧 AquaPredict — Groundwater Level Prediction · Pennar Basin

> A machine learning system that predicts seasonal groundwater depth across 74 observation wells in the Pennar Basin, India — built using Random Forest and 32 years of climate data.

🌐 **Live Demo → [aquapredict.github.io/groundwater-prediction](https://your-username.github.io/groundwater-prediction)**

---

## 📌 What This Project Does

Groundwater is invisible — yet critical for millions of people in semi-arid river basins like the Pennar Basin. This project answers one question:

> *Can seasonal climate data (rainfall, max temp, min temp) predict how deep groundwater sits below the surface?*

The answer is **yes** — and the best-performing site (Sangam-1) achieved a **KGE of 0.71**, well above the standard benchmark for hydrological models.

---

## 🎯 Key Results

| Metric | Best Site (Sangam-1) | Average (74 sites) |
|--------|---------------------|-------------------|
| KGE    | 0.7114              | -0.2376           |
| R²     | 0.4380              | —                 |
| RMSE   | 0.51 m              | 4.03 m            |
| MAE    | 0.43 m              | 3.30 m            |

- ✅ **74** observation wells across the Pennar Basin
- ✅ **27 out of 74** sites achieved positive KGE (model better than mean)
- ✅ **32 years** of seasonal data (1990–2022)
- ✅ **Sangam-1** = best performing site with KGE 0.71

---

## 🌐 Live Web App

An interactive website was built so **anyone — technical or not — can use the model**:

- 🏠 **Home** — plain-English explanation of the project
- ⚡ **Predictor** — choose a real site, set climate values, get a prediction with a plain-English explanation of what the depth means for water access
- 📊 **Results** — full dashboard with all 74 real sites, sortable metrics table, observed vs predicted chart

👉 **[Try it live here](https://your-username.github.io/groundwater-prediction)**

---

## 🧠 Model Details

| Parameter       | Value                  |
|----------------|------------------------|
| Algorithm       | Random Forest Regressor |
| Estimators      | 300 trees              |
| Train/Test split| 70% / 30%              |
| Random state    | 123                    |
| Target variable | GWL (mbgl)             |
| Benchmark       | LSTM Network           |
| Temporal res.   | Seasonal               |
| Spatial extent  | Pennar Basin, India    |

### Input Features
| Feature | Description | Importance |
|---------|-------------|------------|
| Seasonal Rainfall | Total mm per season | ~62% |
| Max Temperature (Tmax) | Peak °C per season | ~22% |
| Min Temperature (Tmin) | Lowest °C per season | ~16% |

### Why KGE over R²?
KGE (Kling-Gupta Efficiency) is used as the primary metric because it captures **correlation, bias, and variability** simultaneously. A model can have R² = 0.85 and still perform poorly in hydrology — KGE penalizes for that. Anything above 0.5 is considered strong for hydrological prediction.

---

## 📁 Project Structure

```
groundwater-prediction/
│
├── index.html                  # Complete interactive web app (self-contained)
│
└── (local files — not uploaded to GitHub)
    ├── Groundlevel_prediction.ipynb   # Main analysis notebook
    ├── Efficiency_Report.csv          # Per-site KGE, RMSE, MAE, R² metrics
    ├── Model_Performance_Summary.xlsx # Summary statistics
    ├── Actual_vs_Predicted_Python     # Scatter plots
    ├── Figure_3_1_Map                 # Basin map
    ├── Figure_4_21_KGE_Map            # Spatial KGE distribution
    ├── KGE_vs_RMSE_Graph              # Performance scatter
    ├── Pennar_Shapefile/              # Basin boundary shapefiles
    ├── Predictors/                    # Climate predictor data
    ├── Predictors_gwls/               # GWL predictor data
    └── stn_data/                      # Station observation data
```

---

## 🛠️ Built With

- **Python** — core analysis and modelling
- **scikit-learn** — Random Forest implementation
- **pandas / numpy** — data processing
- **matplotlib** — visualisation
- **HTML / CSS / JavaScript** — interactive web app (single file, no frameworks)

---

## 📊 Study Area

**Pennar Basin**, Andhra Pradesh & Karnataka, India
- Semi-arid river basin in southern India
- Groundwater is the primary water source for agriculture and domestic use
- 74 observation wells with seasonal records from 1990–2022
- Basin faces increasing water stress due to climate variability

---

## 🚀 How to Run Locally

### Web App
Just download `index.html` and open it in any browser — no server, no installation needed.

### Python Notebook
```bash
# Clone the repo
git clone https://github.com/your-username/groundwater-prediction.git

# Install dependencies
pip install pandas numpy scikit-learn matplotlib seaborn jupyter

# Open the notebook
jupyter notebook Groundlevel_prediction.ipynb
```

---

## 📈 Interpreting Results

| GWL Depth | Meaning |
|-----------|---------|
| < 3 mbgl  | 🟢 Shallow — excellent recharge, easy access |
| 3–6 mbgl  | 🔵 Normal — standard hand pumps can reach |
| 6–9 mbgl  | 🟡 Moderate — bore wells required |
| > 9 mbgl  | 🔴 Deep — critical zone, high water stress risk |

*mbgl = metres below ground level*

---

## 🤝 Connect

Built by **[Your Name]**

- 🔗 LinkedIn: [your-linkedin-url]
- 💻 GitHub: [your-github-url]

---

## 📄 License

This project is open source under the [MIT License](LICENSE).

---

*If you found this useful, please ⭐ star the repository!*
