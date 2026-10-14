&#x20;<div align="center">



\# Data Visualization with Matplotlib \& Seaborn



\*\*Six notebooks on turning raw data into charts that people can actually read.\*\*



!\[Python](https://img.shields.io/badge/Python-3.9%2B-3776AB?logo=python\&logoColor=white)

!\[Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter\&logoColor=white)

!\[Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-11557C)

!\[Seaborn](https://img.shields.io/badge/Seaborn-Statistical%20Visualization-4C72B0)

!\[Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas\&logoColor=white)



</div>



\---



\## Overview



A chart is an argument. It tells the reader where to look, what to compare, and what to conclude, and a poorly built one can mislead as easily as a good one can clarify.



This repository is my structured, hands-on study of Python data visualization. It starts with how Matplotlib builds a figure and ends with statistical plotting in Seaborn. Every notebook is written to explain \*why\* a choice was made, not just to show the call that produces the picture: why a box plot suits one question and a histogram another, why a figure needs deliberate spacing, why default styling is only a starting point.



The material supports my work toward data analysis and machine learning, where looking at the data properly is the step that most often decides whether the later steps go well.



\---



\## Notebooks



The notebooks are numbered in the order I recommend reading them. Each one builds on the one before.



| # | Notebook | What it covers |

|---|---|---|

| 01 | \[Matplotlib Foundations](01\_Matplotlib\_Foundations.ipynb) | How a figure is put together, the plotting workflow, and the core concepts everything else depends on |

| 02 | \[Essential Plot Types](02\_Matplotlib\_Essential\_Plot\_Types.ipynb) | The common chart types, what each one is good at, and when to reach for it |

| 03 | \[Customization \& Professional Styling](03\_Matplotlib\_Customization\_and\_Professional\_Styling.ipynb) | Colors, labels, axes, legends, annotations, and the finishing work that makes a chart presentable |

| 04 | \[Subplots \& Layouts](04\_Matplotlib\_Subplots\_and\_Layouts.ipynb) | Multi-panel figures, grid arrangements, spacing, and side-by-side comparison |

| 05 | \[Seaborn Fundamentals](05\_Seaborn\_Fundamentals.ipynb) | Statistical plots and a faster workflow for exploring data |

| 06 | \[Advanced Seaborn](06\_Advanced\_Seaborn.ipynb) | Statistical visualization and richer views of relationships and group comparisons |



\---



\## What You'll Find Inside



\### Matplotlib: control over every detail



Matplotlib is the foundation most Python plotting libraries are built on. Learning it properly means understanding the object model (figures and axes) rather than relying on shortcuts, because that is what lets you fix a chart when the defaults get in the way.



\- The figure and axes objects, and why the object-oriented interface scales better than `plt.plot()` alone

\- Line, bar, scatter, histogram, and other core chart types

\- Titles, axis labels, tick formatting, legends, colors, and annotations

\- Figure size, margins, and spacing

\- Multi-plot layouts for side-by-side comparison



\### Seaborn: statistical plots with less boilerplate



Seaborn sits on top of Matplotlib and integrates well with Pandas DataFrames, which makes exploratory analysis quicker.



\- Distributions: histograms, KDE plots, and box plots

\- Categorical comparisons across groups

\- Relationships between numeric variables

\- Correlation structure through heatmaps

\- Combining Seaborn's high-level plots with Matplotlib's fine-grained customization



\---



\## Choosing the Right Chart



Picking the chart comes before writing any code. This is the quick reference I work from:



| Question | Good choices | Watch out for |

|---|---|---|

| How is a variable distributed? | Histogram, KDE, box plot | Bin width can change the story; try more than one |

| How do categories compare? | Bar plot, box plot | Bars hide spread; show distributions when they matter |

| How do two numeric variables relate? | Scatter plot | Overplotting on large datasets; reduce point opacity |

| How does a value change over time? | Line plot | Uneven time gaps and truncated axes |

| Which variables move together? | Correlation heatmap | Correlation does not imply causation |

| Several comparisons at once? | Subplots | Keep scales consistent so panels stay comparable |



These are starting points, not rules. The right answer depends on the data and on what the reader needs to take away.



\---



\## Principles I Follow



These are the habits the notebooks try to build.



1\. \*\*Start with the question.\*\* Decide what the chart should answer before choosing its type.

2\. \*\*Label everything a stranger would need.\*\* Title, axis labels, units, and a legend only where it earns its space.

3\. \*\*Remove what does not help.\*\* Heavy gridlines, redundant borders, and decorative color distract from the data.

4\. \*\*Use color on purpose.\*\* Highlight what matters, keep palettes readable, and do not rely on color alone.

5\. \*\*Keep comparisons honest.\*\* Consistent scales, sensible axis ranges, and no tricks of proportion.



\---



\## Example



Even a simple chart improves when it is built deliberately. Here the peak is called out directly, so the reader does not have to hunt for it.



```python

import matplotlib.pyplot as plt



months = \["Jan", "Feb", "Mar", "Apr", "May", "Jun"]

sales = \[12000, 14500, 13200, 16800, 19100, 21500]



fig, ax = plt.subplots(figsize=(9, 5))



ax.plot(months, sales, marker="o", linewidth=2, color="#1f77b4")



\# Call out the peak instead of leaving the reader to find it

ax.annotate(

&#x20;   "Peak: 21,500",

&#x20;   xy=(5, 21500),

&#x20;   xytext=(3.4, 20800),

&#x20;   arrowprops=dict(arrowstyle="->", color="gray"),

)



ax.set\_title("Monthly Sales, January to June", loc="left", fontweight="bold")

ax.set\_xlabel("Month")

ax.set\_ylabel("Sales (units)")



ax.grid(axis="y", alpha=0.3)



fig.tight\_layout()

plt.show()

```



The same idea carries over to Seaborn, where a few lines give a grouped statistical comparison:



```python

import matplotlib.pyplot as plt

import seaborn as sns



sns.set\_theme(style="whitegrid")

tips = sns.load\_dataset("tips")



fig, ax = plt.subplots(figsize=(9, 5))



sns.boxplot(data=tips, x="day", y="total\_bill", hue="smoker", ax=ax)



ax.set\_title("Bill Amount by Day and Smoking Status", loc="left", fontweight="bold")

ax.set\_xlabel("Day")

ax.set\_ylabel("Total bill ($)")



fig.tight\_layout()

plt.show()

```



\---



\## Getting Started



\*\*1. Clone the repository\*\*



```bash

git clone https://github.com/TheAbdullahWaseem/Data-Visualization.git

cd Data-Visualization

```



\*\*2. Create an isolated environment\*\* (recommended)



```bash

python -m venv venv



\# macOS / Linux

source venv/bin/activate



\# Windows

venv\\Scripts\\activate

```



\*\*3. Install the dependencies\*\*



```bash

pip install jupyter numpy pandas matplotlib seaborn

```



\*\*4. Launch Jupyter and open a notebook\*\*



```bash

jupyter notebook

```



Run each notebook from top to bottom. If a notebook needs a dataset or an extra package, it says so at the start. Note that `sns.load\_dataset()` downloads its sample data, so those cells need an internet connection the first time.



\---



\## Repository Structure



```text

Data-Visualization/

├── .gitignore

├── 01\_Matplotlib\_Foundations.ipynb

├── 02\_Matplotlib\_Essential\_Plot\_Types.ipynb

├── 03\_Matplotlib\_Customization\_and\_Professional\_Styling.ipynb

├── 04\_Matplotlib\_Subplots\_and\_Layouts.ipynb

├── 05\_Seaborn\_Fundamentals.ipynb

├── 06\_Advanced\_Seaborn.ipynb

└── README.md

```



\---



\## Where This Is Heading



Visualization is one piece of a larger toolkit that also includes Python, NumPy, Pandas, SQL, and Power BI. Data gets retrieved and cleaned with some of those tools, and with these libraries it gets explored and explained.



Next, I plan to apply these techniques to larger, messier, real-world datasets and to build full analyses where every chart has to justify its place. I also want to explore interactive visualization as a follow-up.



\---



\## About the Author



I'm \*\*Abdullah Waseem\*\*, a Computer Science graduate building a career in data analysis and machine learning. I learn by working through fundamentals carefully and then applying them in projects, and this repository is a record of that process.



\- GitHub: \[@TheAbdullahWaseem](https://github.com/TheAbdullahWaseem)



Feedback and suggestions are welcome. If you spot an error or have a better way to approach something, please open an issue.



\---



<div align="center">



If this repository helped you, consider giving it a star.



</div>

