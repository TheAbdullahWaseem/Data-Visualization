# Data Visualization with Matplotlib & Seaborn

**Six notebooks on turning raw data into charts that people can actually read.**

![Python](https://img.shields.io/badge/Python-3.9%2B-3776AB?logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-11557C)
![Seaborn](https://img.shields.io/badge/Seaborn-Statistical%20Visualization-4C72B0)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas&logoColor=white)

---

## Overview

A chart is an argument. It tells the reader where to look, what to compare, and what to conclude, and a poorly built one can mislead as easily as a good one can clarify.

This repository is my structured, hands-on study of Python data visualization. It starts with how Matplotlib builds a figure and ends with statistical plotting in Seaborn. Every notebook is written to explain *why* a choice was made, not just to show the call that produces the picture: why a box plot suits one question and a histogram another, why a figure needs deliberate spacing, why default styling is only a starting point.

The material supports my work toward data analysis and machine learning, where looking at the data properly is the step that most often decides whether the later steps go well.

---

## Notebooks

The notebooks are numbered in the order I recommend reading them. Each one builds on the one before.

| # | Notebook | What it covers |
|---|---|---|
| 01 | [Matplotlib Foundations](01_Matplotlib_Foundations.ipynb) | How a figure is put together, the plotting workflow, and the core concepts everything else depends on |
| 02 | [Essential Plot Types](02_Matplotlib_Essential_Plot_Types.ipynb) | Line plots, bar charts, scatter plots, histograms, and choosing a suitable chart for the question |
| 03 | [Customization and Professional Styling](03_Matplotlib_Customization_and_Professional_Styling.ipynb) | Titles, labels, legends, colors, annotations, ticks, grids, and improving chart readability |
| 04 | [Subplots and Layouts](04_Matplotlib_Subplots_and_Layouts.ipynb) | Building multiple charts in one figure, arranging layouts, and comparing visualizations |
| 05 | [Seaborn Fundamentals](05_Seaborn_Fundamentals.ipynb) | Statistical visualization, distributions, categorical comparisons, and relationships between variables |
| 06 | [Advanced Seaborn](06_Advanced_Seaborn.ipynb) | Correlation heatmaps, deeper comparisons, and combining Seaborn with Matplotlib for more control |

---

## What You'll Find Inside

### Matplotlib

Matplotlib provides the foundation for building and customizing charts. These notebooks cover:

- Figure and Axes objects and the object-oriented plotting approach
- Line plots, bar charts, scatter plots, and histograms
- Titles, axis labels, legends, tick formatting, and annotations
- Colors, markers, line styles, and grid customization
- Figure dimensions, margins, spacing, and layout adjustments
- Subplots for comparing multiple charts within one figure
- Improving chart clarity and presentation through deliberate styling

### Seaborn

Seaborn builds on Matplotlib and makes statistical visualization more convenient. The notebooks cover:

- Distribution analysis using histograms and KDE plots
- Box plots for comparing distributions across categories
- Categorical comparisons and group-level patterns
- Relationships between numerical variables
- Correlation heatmaps for exploring relationships among multiple variables
- Combining Seaborn's statistical plotting functions with Matplotlib customization

---

## Choosing the Right Chart

The goal is not simply to produce a chart. It is to select a visualization that helps answer the question being asked.

| Analytical question | Suitable visualization |
|---|---|
| How is a numerical variable distributed? | Histogram, KDE plot, or box plot |
| How do values compare across categories? | Bar plot or box plot |
| How are two numerical variables related? | Scatter plot |
| How does a value change over time? | Line plot |
| Which numerical variables move together? | Correlation heatmap |
| How do several patterns compare side by side? | Subplots |

The right choice depends on the data, the analytical question, and the message the chart needs to communicate.

---

## Principles I Follow

**1. Start with the question.**  
Choose a chart because it answers a specific question, not simply because it looks interesting.

**2. Make the chart understandable.**  
Titles, labels, units, and legends should help the reader interpret the visualization without unnecessary guesswork.

**3. Remove distractions.**  
Decorative elements should not compete with the information being presented.

**4. Use color intentionally.**  
Color should distinguish meaningful groups or draw attention to important information rather than add decoration without purpose.

**5. Keep comparisons honest.**  
Scales, labels, and chart choices should represent the data fairly and avoid misleading the reader.

---

## Practical Examples

### 1. Matplotlib: Monthly Sales Trend

This example shows how to build a line chart, label it clearly, and annotate an important observation.

```python
import matplotlib.pyplot as plt

months = ["Jan", "Feb", "Mar", "Apr", "May", "Jun"]
sales = [12000, 14500, 13200, 16800, 19100, 21500]

fig, ax = plt.subplots(figsize=(10, 5))

ax.plot(
    months,
    sales,
    marker="o",
    linewidth=2,
    color="steelblue",
    label="Monthly Sales"
)

ax.annotate(
    "Highest sales",
    xy=("Jun", 21500),
    xytext=("Apr", 22000),
    arrowprops={"arrowstyle": "->"}
)

ax.set_title("Monthly Sales Trend", fontsize=14)
ax.set_xlabel("Month")
ax.set_ylabel("Sales")
ax.legend()
ax.grid(axis="y", alpha=0.3)

fig.tight_layout()
plt.show()
```

### 2. Seaborn: Comparing Bills Across Days

A box plot helps compare the distribution of restaurant bills across different days and smoking groups.

```python
import matplotlib.pyplot as plt
import seaborn as sns

tips = sns.load_dataset("tips")

fig, ax = plt.subplots(figsize=(9, 5))

sns.boxplot(
    data=tips,
    x="day",
    y="total_bill",
    hue="smoker",
    ax=ax
)

ax.set_title("Restaurant Bills by Day and Smoking Status")
ax.set_xlabel("Day")
ax.set_ylabel("Total Bill")

fig.tight_layout()
plt.show()
```

These examples illustrate the general workflow. The notebooks provide the step-by-step learning material and additional practice.

---

## Getting Started

### Requirements

- Python
- Jupyter Notebook or JupyterLab
- NumPy
- Pandas
- Matplotlib
- Seaborn

### Installation

Clone the repository:

```bash
git clone https://github.com/TheAbdullahWaseem/Data-Visualization.git
cd Data-Visualization
```

Create and activate a virtual environment if you want to keep the project dependencies separate.

**Windows:**

```bash
python -m venv .venv
.venv\Scripts\activate
```

**macOS/Linux:**

```bash
python3 -m venv .venv
source .venv/bin/activate
```

Install the required libraries:

```bash
pip install jupyter numpy pandas matplotlib seaborn
```

Start Jupyter Notebook:

```bash
jupyter notebook
```

Open a notebook and run its cells in sequence.

**Note:** Seaborn's built-in example datasets, such as `tips`, may require an internet connection the first time they are downloaded.

---

## Repository Structure

```text
Data-Visualization/
│
├── 01_Matplotlib_Foundations.ipynb
├── 02_Matplotlib_Essential_Plot_Types.ipynb
├── 03_Matplotlib_Customization_and_Professional_Styling.ipynb
├── 04_Matplotlib_Subplots_and_Layouts.ipynb
├── 05_Seaborn_Fundamentals.ipynb
├── 06_Advanced_Seaborn.ipynb
├── .gitignore
└── README.md
```

The repository is organized to progress from Matplotlib fundamentals to chart customization, layout design, and statistical visualization with Seaborn.

---

## Where This Is Heading

This repository is part of my broader preparation for a career in data analysis and machine learning. I have been building my foundations in Python, NumPy, Pandas, and SQL, and I am developing the ability to move from data preparation to analysis and clear visual communication.

The next step is to apply these skills to real-world datasets and portfolio projects, where visualizations can help reveal patterns, investigate questions, and communicate findings. I also intend to explore interactive visualization as my project work develops.

---

## About the Author

**Abdullah Waseem**  
Computer Science Graduate | Aspiring Data Analyst, Data Scientist, and Machine Learning Engineer

I use these repositories to document my learning, practice independently, and build a portfolio grounded in practical work.

- **GitHub:** [TheAbdullahWaseem](https://github.com/TheAbdullahWaseem)
- **Repository:** [Data-Visualization](https://github.com/TheAbdullahWaseem/Data-Visualization)

Suggestions and constructive feedback are welcome.

---

*Learning the tools is the beginning. Learning when and why to use them is what makes the difference.*
