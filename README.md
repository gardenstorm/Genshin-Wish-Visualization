# 🌠 Genshin Wish Visualization

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/gardenstorm/Genshin-Wish-Visualization/blob/main/Genshin_Wish_Visualization.ipynb)

> **Status: Work in Progress**

A personal data analysis and visualization project that explores over 5 years of Genshin Impact wish (gacha pull) history — from version 1.1 through the present. Inspired by [Paimon.moe](https://paimon.moe), this project goes further by building custom charts, statistics, and illustrated summaries directly in Python.

---

## 📂 Contents

| File | Description |
|---|---|
| `Genshin_Wish_Visualization.ipynb` | Main Jupyter notebook — all data processing and visualizations |

---

## 🗂️ Data Sources

The wish history comes from two sources that are merged together:

- **Personal spreadsheet** — manually recorded pulls from version 1.1 (pre-Paimon.moe era, before August 2021)
- **Paimon.moe export** — pull history from August 2021 onward

Both limited (character event) banner data and standard banner data are included.

---

## ✨ Features

### Data Processing
- Loads and cleans data from Excel files using reusable functions (`load_file`, `banner_col_changes`, `combine_data`)
- Merges personal and Paimon.moe datasets into unified limited-banner and standard-banner DataFrames
- Normalizes banner names using regex and a dictionary mapping (e.g. maps "Ballad in Goblets 2nd" → character name)
- Handles pity counter columns across two different recording conventions

### Statistics
- **Average & median pity** for 5-star pulls on limited and standard banners
- **5-star pull counts** — how many times each 5-star was obtained, with pity values
- **4-star character frequency** — most-pulled 4-star characters on each banner type
- **Weapon frequency** — 3-star, 4-star, and 5-star weapon pull counts by banner
- **50/50 win rate** — tracks guaranteed vs. won 50/50 outcomes on limited banners

### Visualizations
- Pity frequency **histograms** for limited and standard banners
- Horizontal **bar charts** for weapon and 4-star character frequencies
- **Stacked bar charts** comparing limited vs. standard banner pulls side by side
- **Pie chart** of standard banner 5-star type breakdown (characters vs. weapons)
- **Treemaps** of 4-star character pull counts (with Plotly Express)
- **Illustrated character grid** using character icon images fetched from the [Genshin.dev API](https://genshin.dev)
- **Pulls-over-time line chart** (in progress)

---

## 🛠️ Tools Used

| Category | Tools |
|---|---|
| **Notebook environment** | Google Colab |
| **Data prep** | Microsoft Excel, Google Sheets |
| **Languages** | Python |
| **Data libraries** | Pandas, NumPy |
| **Visualization** | Matplotlib, Plotly Express |
| **API** | [Genshin.dev](https://genshin.dev) (character icons) |
| **HTTP** | Requests, IPython.display |
| **AI assistance** | Google Gemini (built-in Colab), Claude |

### Planned / Coming Soon
- JavaScript
- Expanded Genshin.dev API usage

---

## 🚧 Known Limitations & Future Work

- Pity columns between the two data sources are recorded differently; currently only 5-star pity is analyzed. 4-star pity analysis will require normalizing this inconsistency.
- A few character names from the Genshin.dev API don't match exactly and require local image overrides.
- Pulls-over-time chart is still in progress.
- Treemap element-color coding (to see elemental distribution of pulled characters) is planned.

---

## 🚀 Running the Notebook

1. Click the **Open in Colab** badge at the top of this README.
2. Mount your Google Drive and place your wish history Excel file(s) at the expected paths (see `load_file` calls in the notebook).
3. Run cells in order.

> The notebook is designed for Google Colab and references Google Drive paths. Local execution would require adjusting file paths.
