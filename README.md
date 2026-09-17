# Video Game Sales Analysis

**Data Analytics — Individual Project**
Prashanth Pinniboyina | Student ID: 49834918
University of Europe for Applied Sciences

---

## Overview

This project analyzes historical video game sales data to understand how regional
preferences differ, how the market has evolved across console generations, whether
critical acclaim translates into commercial success, and which publishers consistently
produce hit titles.

## Problem Statement

The video game industry spans many regions, platforms, and publishers, each with
different consumer preferences and commercial dynamics. Publishers and developers
often lack a clear, data-driven view of how regional tastes differ, how the market has
evolved across console generations, whether critical acclaim actually translates into
sales, and which publishers reliably produce hits versus those with occasional
breakout success.

This project uses historical sales and review data to answer these questions with
quantitative evidence — insights that can inform regional marketing strategy, platform
investment, and publisher performance evaluation.

## Business Questions

1. Which genres and platforms dominate by region (NA vs. EU vs. Japan)?
2. How have sales trends shifted over console generations?
3. Do critic scores correlate with sales?
4. Which publishers have the most consistent hit rate?

## Dataset

**Source:** [Video Games Sales Dataset — Updated / Extra Feat (Kaggle)](https://www.kaggle.com/datasets/ibriiee/video-games-sales-dataset-2022-updated-extra-feat)

**Key fields:** Name, Platform, Year, Genre, Publisher, NA_Sales, EU_Sales, JP_Sales,
Other_Sales, Global_Sales, Critic_Score, User_Score

**Format:** CSV

> The dataset is not committed to this repository. Download it from the link above and
> place the CSV in the project root before running the notebook.

## Methodology

| Step | Description |
|------|-------------|
| 1. Data Collection | Obtain the dataset from Kaggle in CSV format |
| 2. Data Cleaning | Handle missing Critic/User scores, remove duplicates, standardize labels |
| 3. Transformation | Map platforms to console generations; compute normalized regional shares |
| 4. Exploratory Analysis | Aggregate, group, and correlate to answer each business question |
| 5. Visualization | Grouped bars, heatmaps, scatter plots, and time-series charts |
| 6. Interpretation | Draw conclusions and document assumptions and limitations |

## Tech Stack

- Python 3
- pandas — data cleaning and aggregation
- NumPy — numerical operations
- Matplotlib / Seaborn — visualization
- Jupyter Notebook — analysis environment

## Setup

```bash
# Clone the repository
git clone https://github.com/PrashanthPinniboyina/49834918_DS-120B.git
cd 49834918_DS-120B

# Install dependencies
pip install pandas numpy matplotlib seaborn jupyter

# Launch the notebook
jupyter notebook
```

Then download the dataset from Kaggle, place the CSV in the project root, and update
the `DATA_PATH` variable in the notebook if your file name differs.

## Repository Structure

```
.
├── README.md
├── Video_Game_Sales_Analysis.ipynb    # Main analysis notebook
├── Video_Game_Sales_Analysis.pptx     # Final presentation
├── Project_Proposal.pdf               # Project proposal document
└── images/                            # Exported charts
```

## Key Findings

**1. Regional preferences differ sharply**
Role-Playing games account for ~27% of Japan's sales versus only ~7–8% in NA and EU.
Action leads in NA (19.9%) and EU (21.3%) but trails in Japan (12.4%). Shooters are
popular in the West (~13–14%) but marginal in Japan (3.0%). Sports sales share is
remarkably consistent across all three regions (~15.4%).

**2. Sales peaked in the late 2000s**
Global sales peaked in 2008 at approximately 672M units. Generation 7 (2006–2012)
dominates all other eras with over 3,000M units across the top six genres. The sharp
post-2011 decline reflects the industry's shift toward digital distribution and mobile
gaming, which retail-sales datasets like this one underrepresent.

**3. Critic scores are a weak predictor of sales**
The correlation between Critic_Score and Global_Sales is only **r = 0.25**. Most games
cluster near zero sales regardless of score. Franchise strength, marketing, and platform
reach appear to matter considerably more than critical reception alone.

**4. Nintendo leads on volume-adjusted consistency**
Using a "hit" threshold of the top 25% of games by Global_Sales and a minimum of 10
releases per publisher, Nintendo achieves a 0.65 hit rate across ~700 releases —
combining high volume with high consistency. Electronic Arts maintains a 0.51 hit rate
across the largest catalog (~1,340 releases). Most publishers fall below a 0.2 hit rate,
showing that genuine hits are rare industry-wide.

## Limitations

- The dataset tracks physical/retail sales and underrepresents digital and mobile sales,
  particularly after 2011.
- Critic and user scores are missing for a substantial portion of titles; those rows are
  excluded from the correlation analysis rather than imputed.
- The platform-to-generation mapping is a manual grouping and treats PC as a separate
  category since it spans all eras.
- Publishers with very few releases can show misleadingly high hit rates, which is why a
  minimum release threshold is applied.

## Deliverables

- `Video_Game_Sales_Analysis.ipynb` — full analysis with code and visualizations
- `Video_Game_Sales_Analysis.pptx` — presentation deck
- `Project_Proposal.pdf` — original project proposal

## Author

**Prashanth Pinniboyina**
Student ID: 49834918
University of Europe for Applied Sciences
