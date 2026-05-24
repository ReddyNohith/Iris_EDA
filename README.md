

#  Iris Dataset — Exploratory Data Analysis


> A beginner-friendly data science project that digs into the famous UCI Iris
> dataset — one of the most well-known datasets in machine learning. The goal
> is to understand the data before building any model: find patterns, check for
> problems, and summarise what the numbers actually mean.

##  Live Report

👉 [View the interactive EDA report here](https://ReddyNohith.github.io/Iris_EDA/iris_profile_report.html)

---

##  What is EDA?

**Exploratory Data Analysis (EDA)** is the first step in any data science project.
Before training a model, we need to understand what the data looks like:

- Are there any missing values or errors?
- What is the range and spread of each feature?
- Do any features look similar or correlated?
- Can we already spot differences between groups just by looking?

Think of it like reading a book's summary before diving in — it saves a lot of
confusion later.

---

##  About the Dataset

The Iris dataset contains measurements of **150 iris flowers** across **3 species**:

| Species | Samples | Easy to identify? |
|---|---|---|
| Setosa | 50 | ✅ Yes — very distinct |
| Versicolor | 50 | ⚠️ Somewhat |
| Virginica | 50 | ⚠️ Somewhat |

Each flower has 4 measurements (in cm):
- Sepal length & sepal width
- Petal length & petal width

---

##  Key Findings (Plain English)

1. **The data is perfectly clean** — no missing values, no errors. Nothing to fix.

2. **Petal size is the secret weapon** — petal length and petal width are the
   best features for telling species apart. Sepal size? Not so useful.

3. **Setosa stands alone** — if petal length is less than 2.5 cm, it's setosa.
   Every single time. A simple rule works perfectly.

4. **Petal length and width almost say the same thing** — they're 96% correlated.
   You could drop one and lose almost no information.

5. **Versicolor and Virginica overlap** — these two are harder to separate. Petal
   width above 1.7 cm is the best single clue for Virginica.

6. **Balanced dataset** — 50 flowers per species means no group is
   over/under-represented. Great for fair model training later.

---

##  What's in this Repo

```
iris-eda/
├── iris_eda_notebook.ipynb    ← Step-by-step analysis with charts
├── iris_profile_report.html   ← Auto-generated full report (open in browser)
├── iris.csv                   ← The dataset
├── requirements.txt           ← Libraries needed to run this
└── README.md                  ← You are here
```

---

## 🚀 Run it Yourself

**1. Clone the repo**
```bash
git clone https://github.com//.git
cd 
```

**2. Install dependencies**
```bash
pip install -r requirements.txt
```

**3. Open the notebook**
```bash
jupyter notebook iris_eda_notebook.ipynb
```

**4. Regenerate the HTML report (optional)**
```python
from data_profiling import ProfileReport
import pandas as pd

df = pd.read_csv("iris.csv")
profile = ProfileReport(df, title="Iris EDA Report", explorative=True)
profile.to_file("iris_profile_report.html")
```

---

##  Requirements

```
pandas>=2.0
numpy>=1.24
matplotlib>=3.7
seaborn>=0.12
scikit-learn>=1.3
fg-data-profiling>=4.0
jupyter
```

---

## 📈 Visualisations Included

- Class distribution bar chart
- Box-plots per feature (split by species)
- KDE density curves
- Pair-plot (every feature vs every other)
- Pearson correlation heatmap

---

##  Credits

- [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/iris) — original dataset
- [ydata-profiling](https://github.com/ydataai/ydata-profiling) — automated profiling
- [scikit-learn](https://scikit-learn.org/) — dataset loader

---

##  License

MIT License — free to use, modify, and share.
