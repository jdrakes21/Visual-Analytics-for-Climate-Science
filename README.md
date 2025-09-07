# ❄️ Iceberg D-15A Drift Visualization (2020–2025)

> **UMBC iHARP REU Project – Visual Analytics for Climate Science**

---

## 📌 Overview

This project is part of the **iHARP REU** program at UMBC, with a focus on **Geospatial Reasoning and Visual Analytics for Environmental Research**. The specific goal is to **track the drift path of iceberg D-15A** from July 2020 to July 2025 using remote sensing data and map-based visualizations. This effort integrates environmental data, human-centered design, and interactive analytics to explore how visualization and interactivity can aid scientific reasoning.

---

## ❓ Key Research Questions

- **How do AI-calculated calving events vary over time and space?**
- **How can we effectively communicate uncertainty in segmentation?**
- **What UI elements help scientists interrogate model outputs?**
- **How does interactivity aid scientific reasoning in environmental research?**

---

## 🧊 Scientific Significance

Tracking iceberg drift contributes to:

- 📈 **Climate models**: Understanding melt patterns and ice loss trends  
- 🚢 **Shipping/navigation safety**: Reducing risks from iceberg paths  
- 🌊 **Ocean circulation**: Modeling ocean current responses to calving  
- 🐟 **Ecosystem monitoring**: Observing impacts on marine habitats  
- 🤖 **Automation**: Providing baselines for future model-driven detection pipelines  

---

## 🧪 Implementation

### ✅ Data Used

- `AntarcticIcebergs_20200717.csv` – Start point (July 2020)  
- `AntarcticIcebergs_20250718.csv` – End point (July 2025)  
- `D15A.png` – Optional satellite image overlay (Sentinel 2, not embedded in final output)

### 🗺️ Core Features

- Polar stereographic projection using `Cartopy`  
- Drift path visualized with start (🟢) and end (🔴) points  
- Straight-line trajectory indicating total movement  
- (Optional) Background texture for satellite image alignment  

```python
# Example snippet
df_start = pd.read_csv("AntarcticIcebergs_20200717.csv")
df_end = pd.read_csv("AntarcticIcebergs_20250718.csv")

start_lat = df_start['Latitude'][0]
start_lon = df_start['Longitude'][0]
end_lat = df_end['Latitude'][0]
end_lon = df_end['Longitude'][0]
```

---

## 📊 Visualization Output

A static drift map rendered via Matplotlib and Cartopy:

- **Projection**: South Polar Stereographic
- **Annotations**: Start point, end point, straight-line drift
- **Map Features**: Coastlines, gridlines

📷 _Example Output (Insert image or screenshot link):_

![Drift Output Preview]((https://github.com/jdrakes21/Visual-Analytics-for-Climate-Science/blob/main/Iceberg%20drift%20path.png))

---

## 🧪 Visualization Attempts

| Platform       | Result      | Notes |
|----------------|-------------|-------|
| **Panel**      | ⚠️ Incomplete | Rendered matplotlib figure but Panel layout failed in Colab |
| **Streamlit**  | ⚠️ Blocked   | Ngrok required token, public dashboard not reachable |
| **Jupyter Notebook** | ✅ Success | Static visual shows drift map effectively |
| **Ngrok**      | ❌ Failed    | Ngrok auth token required, tunnel not established in Colab |

---

## 📘 Research Context

This work is part of a broader exploration of **how interactive tools can support scientific discovery** in polar science. Visualization plays a key role in:

- Identifying patterns in remote sensing data  
- Communicating uncertainty  
- Supporting exploratory data analysis  
- Enhancing accessibility of environmental data  

---

## 🔮 Future Directions

- Add intermediate coordinates (2021–2024) for curved drift path  
- Overlay additional layers (e.g., sea surface temperature, velocity vectors)  
- Animate the iceberg drift over time  
- Transition to a full dashboard in **JupyterLab + Voilà** or **Streamlit (local)**  
- Evaluate usability of visual UI components with domain experts  

---

## 🔍 Synthesis of Results

- The **drift path** shows a significant migration of D-15A from near the Antarctic Peninsula toward the South Atlantic, consistent with patterns seen in satellite imagery of iceberg decay and dispersal.
- While only using the **start and end coordinates**, the visualization reveals:
  - The **potential role of ocean currents** (e.g., Antarctic Circumpolar Current)
  - How **polar projection choice** improves geospatial reasoning over raw latitude-longitude maps
- The project also highlighted the need for **UI components** that allow scientists to:
  - Toggle between multiple projections
  - Overlay temperature or current data
  - Annotate uncertainty in location or mass

---

## 🤔 What I Learned

- 🛰️ **Working with geospatial data** requires careful projection choices to avoid misleading interpretations—especially in polar regions.
- 🧭 **Visual design decisions** (e.g., color for start/end, labeled legends) are critical in making data understandable to scientific and public audiences.
- ⚙️ **Scientific dashboards** must consider how to balance clarity with complexity. While the goal was to build an interactive Panel/Streamlit dashboard, infrastructure limitations (e.g., Colab not supporting full dashboards without ngrok auth) forced a fallback to static plots. This still conveyed essential insights.

---

## 🖼️ Acknowledgments

- Satellite imagery: Sentinel Hub (2020)  
- Data source: NASA ITS-LIVE  
- Program: NSF iHARP REU at UMBC  
- Mentors and collaborators: Dr. Dawn Williams (UMBC), iHARP project leads  

---
